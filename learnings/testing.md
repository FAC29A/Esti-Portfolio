# Testing Portfolio

## Learning Objectives:

### 1. Check that passing a given input into our tests returns the expected output

Ensuring that functions or modules produce the anticipated output when given specific inputs is fundamental for verifying the correctness of the code. This learning objective focuses on writing tests that systematically validate the behavior of the code under various scenarios.

### 2. Write tests to mimic the behavior of a user performing different actions

Creating tests that simulate user interactions is crucial for validating the application's responsiveness. This objective emphasizes the importance of testing user-centric functionalities to ensure that the application behaves as expected during different user actions, enhancing reliability and user experience.

### 3. Write testable, modular functions

To facilitate effective testing, functions should be designed to be modular and easily testable in isolation. This objective underscores the significance of developing functions that perform specific tasks, allowing for independent testing. Modular functions contribute to code maintainability and a more robust testing process.

### 4. Write functions that add, remove, or modify DOM nodes

Interacting with the Document Object Model (DOM) is a common task in web development. This objective focuses on writing functions that manipulate DOM elements by adding, removing, or modifying them. Testing these functions ensures that the user interface responds appropriately to dynamic changes, improving the overall user experience.

### 5. Apply event listeners to HTML form elements

Attaching event listeners to HTML form elements is essential for enabling user interactions. This objective involves testing to ensure that event listeners respond correctly to user actions, such as button clicks or form submissions. Successful testing enhances the interactivity of the application.

### 6. Use scope to control what variables are accessible inside functions and blocks

Understanding and effectively managing scope is critical for maintaining clean and readable code. This learning objective emphasizes controlling the visibility and accessibility of variables within functions and code blocks. Proper scope management helps prevent unintended variable conflicts and enhances the reliability of the code.

### 7. Use CSS grid to create complex layouts

CSS Grid is a powerful layout system for creating intricate and responsive web layouts. This objective focuses on mastering the use of CSS Grid to design complex page structures. Testing may involve verifying that layouts adapt correctly to different screen sizes and devices.

### 8. Use CSS grid to make layouts that adapt to the viewport size

Building on the previous objective, this one specifically concentrates on creating layouts that dynamically adapt to varying viewport sizes. CSS Grid provides a robust toolset for responsive design, and testing ensures that the layout adjusts appropriately, providing a consistent and user-friendly experience across different devices.

## JavaScript Code:

```javascript
function equal(actual, expected, message) {
  if (actual === expected) {
    const defaultMessage = `Expected ${expected} and received ${actual}`;
    console.info("Pass: " + (message || defaultMessage));
  } else {
    const defaultMessage = `Expected ${expected} but received ${actual} instead`;
    console.error("Fail: " + (message || defaultMessage));
  }
}

function notEqual(actual, expected, message) {
  if (actual !== expected) {
    const defaultMessage = `${expected} is different to ${actual}`;
    console.info("Pass: " + (message || defaultMessage));
  } else {
    const defaultMessage = `${expected} is the same as ${actual}`;
    console.error("Fail: " + (message || defaultMessage));
  }
}

function test(name, testFunction) {
  console.group(name);
  testFunction();
  console.groupEnd(name);
}
```

```javascript
//First test group: Modal open and close

test("Opening and closing the modal", () => {
    const modal = document.getElementById("modal");
    const openModalBtn = document.getElementById("open-modal-btn");
    // Click the open button to open the modal
    openModalBtn.click();
    equal(modal.style.display, "block", "Modal should be open");
    const closeModalBtn = document.getElementById("close-modal");
    // Click the open button to close the modal
    closeModalBtn.click();
    equal(modal.style.display, "none", "Modal should be closed");
});

// Secod test group: Create a task elements finctionality
test("Create task element with name, description, and priority", () => {
    const taskName = "Test Task";
    const taskDescription = "This is a test task";
    const priority = "High";

    const taskElement = createTaskElement(taskName, taskDescription, priority);

    // Check the structure and content of the task element
    equal(taskElement.classList.contains("task-content"), true, "Task element has the 'task-content' class");
    equal(taskElement.innerHTML.includes("<h3>Test Task</h3>"), true, "Task name is present");
    equal(taskElement.innerHTML.includes("<p>This is a test task</p>"), true, "Description is present");
    equal(taskElement.querySelector('.highlight-text').textContent, 'High', "Priority is present");

});


test("Create task element with name and priority only", () => {
    const taskName = "Test Task";
    const priority = "High";
    const taskElement = createTaskElement(taskName, "", priority);
    // Check the structure and content of the task element
    equal(taskElement.classList.contains("task-content"), true, "Task element has the 'task-content' class");
    equal(taskElement.innerHTML.includes("<h3>Test Task</h3>"), true, "Task name is present");
    notEqual(taskElement.innerHTML.includes("<p>Description:"), true, "Description is not present");
    equal(taskElement.querySelector('.highlight-text').textContent, 'High', "Priority is present");
});

//Third test group: Add task finctionality
test("Add task with an empty name", () => {
    // Mocking the input values
    taskNameInput.value = "";
    taskDescriptionTextarea.value = "This is a test task";
    prioritySelect.value = "Medium";

    // Running the addTask function
    addTask();

    // Checking if no task has been added to the task list
    const taskList = document.getElementById("to-do");
    const taskElements = taskList.getElementsByClassName("task-content");

    equal(taskElements.length, 0, "No task added with an empty name");
});

test("Add task with a whitespace-only name", () => {
    // Mocking the input values
    taskNameInput.value = "   ";
    taskDescriptionTextarea.value = "This is a test task";
    prioritySelect.value = "Low";

    // Running the addTask function
    addTask();

    // Checking if no task has been added to the task list
    const taskList = document.getElementById("to-do");
    const taskElements = taskList.getElementsByClassName("task-content");

    equal(taskElements.length, 0, "No task added with a whitespace-only name");
});


test("Add task with a valid name and priority", () => {
    // Mocking the input values
    taskNameInput.value = "Test Task";
    taskDescriptionTextarea.value = "This is a test task";
    prioritySelect.value = "Important";

    // Running the addTask function
    addTask();

    // Checking if the task has been added to the task list
    const taskList = document.getElementById("to-do");
    const taskElements = taskList.getElementsByClassName("task-content");

    equal(taskElements.length, 1, "Task has been added to the task list");
    // Remove created task
    Array.from(taskElements).forEach((element) => element.remove());
});


//Forth test group: Drag and drop functionality
test("onDragStart should set dataTransfer correctly", () => {
    // Create a dynamic task element
    const taskElement = document.createElement("div");
    taskElement.id = "task-1";

    const event = {
        target: taskElement,
        dataTransfer: {
            setData: function (type, value) {
                equal(type, "text/plain", 'DataTransfer type should be "text/plain"');
                equal(value, "task-1", "DataTransfer value should be set correctly");
            },
        },
    };

    onDragStart(event);
});

test("onDrop should move the task to the appropriate section", () => {
    // Create dynamic task elements
    const draggableElement = document.createElement("div");
    draggableElement.id = "task-2";

    const dropzone = document.createElement("div");
    dropzone.id = "section-2";

    // Simulate the dynamic task creation by adding them to the document
    document.body.appendChild(draggableElement);
    document.body.appendChild(dropzone);

    const event = {
        dataTransfer: {
            getData: function (type) {
                equal(type, "text", 'DataTransfer type should be "text"');
                return "task-2";
            },
        },
        target: dropzone,
    };

    onDrop(event);

    equal(
        draggableElement.parentElement,
        dropzone,
        "Task should be moved to the appropriate section"
    );
});

//Fifth test group: Delete functionality

test('onDrop should delete the task if dropped into the "delete" bin', () => {
    // Create a dynamic task element
    const draggableElement = document.createElement("div");
    draggableElement.id = "task-3";

    const deleteBin = document.createElement("div");
    deleteBin.id = "delete";

    // Simulate the dynamic task creation by adding them to the document
    document.body.appendChild(draggableElement);
    document.body.appendChild(deleteBin);

    const event = {
        dataTransfer: {
            getData: function (type) {
                equal(type, "text", 'DataTransfer type should be "text"');
                return "task-3";
            },
        },
        target: deleteBin,
        preventDefault: function () {}, // Mock preventDefault function
    };

    onDrop(event);

    // Additional check: Make sure the task element was removed
    equal(document.getElementById("task-3"), null, 'Task should have been removed');

    // Additional check: Make sure draggableElement is not in the document body anymore
    equal(document.body.contains(draggableElement), false, 'Task should not be in the document body');
});
```
