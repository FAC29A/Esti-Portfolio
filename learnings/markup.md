<div align="center">
 

 <br ></div>

 # Introduction

In this README, we'll cover various aspects of our web development project - Sky & Fly Agency. We've incorporated modern web development techniques and best practices to create an accessible, responsive, and user-friendly website.


## 1. Structure a site using semantic HTML to aid accessibility

In my Sky & Fly agency website project, I employed semantic HTML elements to create a well-structured and accessible website. Here are some of the key elements I used:

- `<header>`: Used for the top section of each page, which typically includes the website's logo, main navigation menu, and introductory content.

- `<nav>`: Employed to define the website's navigation menu, providing easy access to different sections.

- `<section>`: Used to group content thematically within each page, improving readability and organization.

- `<footer>`: Placed at the bottom of each page to include metadata, copyright information, contact details, and related links.

- `<main>`: Wrapped the main content of each page within a `<main>` element to signify its importance.

#### snippet of my HTML code that demonstrates the use of some of the semantic HTML elements mentioned:

 ```html
<header class="header">
      <div class="header-container">
        <div id="header-branding">
          <a href="index.html#home" class="branding-link">
            <img src="images/logo.jpeg" alt="agency logo"
          /></a>
        </div>
        <div id="header-nav-container">
          <nav id="header-nav">
            <ul id="header-nav-menu">
              <li class="menu-item">
                <a href="#home" class="active" class="nav-link">Home</a>
              </li>
              <li class="menu-item">
                <a href="#about" class="nav-link">About</a>
              </li>
              <li class="menu-item">
                <a href="#team" class="nav-link">Team</a>
              </li>
              <li class="menu-item">
                <a href="#fleet" class="nav-link">Fleet</a>
              </li>
              <li class="menu-item">
                <a href="#contact" class="nav-link">Contact</a>
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </header>
```

By utilizing these semantic elements, I enhanced the website's structure, accessibility, and search engine optimization (SEO), ensuring a better user experience for all visitors.



## 2. Ensure a web page is readable for screen readers

In our web development project, we paid special attention to making our web pages readable for screen readers and ensuring an inclusive browsing experience for all users, including those with visual impairments. One of the techniques we used to enhance screen reader accessibility is the tabindex attribute.

### Tabindex Attribute
The tabindex attribute allows us to control the order in which elements receive keyboard focus when a user navigates a web page using the "Tab" key. By strategically applying the tabindex attribute, we can ensure that screen readers and keyboard users can navigate and interact with our content in a logical and meaningful way.

For example:

```html
<div class="card" tabindex="0">
    <!-- Content of the card -->
</div>
```
In the above code snippet, we've added a tabindex attribute to a `<div>` element with the class "card." This allows users to focus on the "card" element when navigating the page using the keyboard. The tabindex="0" value means that the element will receive keyboard focus in the order it appears in the HTML source code.

By using tabindex appropriately and ensuring that the focus order follows a logical flow, we make it easier for screen reader users to understand and interact with our web pages, providing a more accessible and inclusive user experience.


## 3. Ensure our UI has sufficient colour contrast so that everyone can perceive it comfortably

In our web development project, we prioritized ensuring that our user interface (UI) maintains sufficient color contrast to ensure a comfortable and inclusive browsing experience for all users. We chose light colors as part of our design strategy to create a visually pleasing and accessible user interface.

## Using Light Colors
<div align="center">
 
![image](https://github.com/Estishi87/Esti-Portfolio/assets/125391502/5be7e097-9900-4ec2-b613-9ae110775b5c)
 <br ></div>

We deliberately selected a color palette that incorporates light colors to enhance the readability and usability of our website. Light colors not only contribute to an aesthetically pleasing design but also help improve the overall user experience, especially for individuals with visual impairments.

By opting for light colors, we achieve the following benefits:

1. **Improved Legibility**: Light backgrounds with dark text or content elements contribute to better legibility and readability, making it easier for users to consume information.

2. **Enhanced Accessibility**: Light color combinations often result in higher contrast ratios, which are critical for users with low vision or color blindness. This ensures that text and content stand out clearly against the background.

3. **Reduced Eye Strain**: Light color schemes are generally less likely to cause eye strain and fatigue during extended periods of reading or browsing.

### Prioritizing User Comfort

Our design approach underscores the importance of user comfort and accessibility. By using light colors, we aim to provide a comfortable and enjoyable viewing experience for all users, regardless of their visual abilities. This commitment to color contrast aligns with our goal of making our website accessible to as many people as possible.

In summary, our choice of light colors is a deliberate decision to enhance color contrast, legibility, and overall accessibility. We believe that everyone should be able to perceive and engage with our website comfortably, and our color scheme plays a vital role in achieving that goal.


## 4. Use various tools to check that our website meets accessibility criteria

In our web development project, ensuring accessibility is a priority. We have employed various tools and techniques to check that our website meets accessibility criteria, providing an inclusive experience for all users, including those with disabilities.

### Tabindex Attribute (As Mentioned in Point 2)

As previously mentioned, we used the `tabindex` attribute strategically to control the order in which elements receive keyboard focus, ensuring a logical and meaningful navigation experience for screen reader users and keyboard users.

### Evaluation with Online Tools

To further ensure accessibility, we utilized online tools to evaluate our website's compliance with accessibility standards. One of the tools we relied on is [Easy Agile's Accessibility Checker](https://blog.easyagile.com/how-to-write-good-user-stories-in-agile-software-development-d4b25356b604).

### Meeting Acceptance Criteria

In addition to using tools, we also considered specific acceptance criteria to ensure accessibility throughout the project. Here are some examples of the acceptance criteria we addressed:

1. **Navigation Menu**: The navigation menu is designed and tested to be fully navigable and usable with keyboard controls and screen readers.

2. **'About Us' Section**: We ensured that the 'About Us' section contains descriptive and meaningful content to enhance comprehension.

3. **Contact Form**: The contact form is designed with accessible labels, and form fields are marked appropriately for screen readers.

4. **Form Submission**: Users cannot submit the form without completing all mandatory fields, including name, company name, and email address. This ensures that important information is not omitted.

5. **User Interaction**: Information from the form is not submitted until the user clicks a button, providing control and context to users.

By addressing these acceptance criteria and utilizing accessibility evaluation tools, we are committed to making our website accessible to all users, regardless of their abilities. Our goal is to provide an inclusive and user-friendly experience for everyone who visits our site.


## 5. Use CSS media queries to ensure our content is always presented effectively on screens of different sizes

In our web development project for Sky & Fly Agency, we have placed a strong emphasis on creating a responsive and adaptable design that works effectively on screens of different sizes. This ensures a consistent and user-friendly experience across various devices.

### Sizing Objects with Media Queries

During the development process, we initially employed traditional CSS media queries to adjust the layout and styling of our web content for different screen sizes. These media queries allowed us to set specific rules for different breakpoints, optimizing the user experience on a variety of devices.

### Leveraging `calc()` with Media Queries

```css
.heading-container h1 span {
  color: #5de4c7;
  font-size: calc(4.3vw + 10px);
}
```

As we continued to refine our design, we discovered that using the `calc()` function in conjunction with media queries significantly streamlined the process of creating responsive layouts. This approach allowed us to calculate element sizes based on dynamic factors, reducing the need for complex and repetitive media query definitions.

### Smartphone Optimization
<div align="center">
 
![image](https://github.com/Estishi87/Esti-Portfolio/assets/125391502/457cf915-8a11-41ab-8b43-ebf86272bd06)
 <br ></div>


Recognizing the increasing importance of mobile users, the majority of our media queries were specifically designed to enhance the website's usability on smartphones. This involved adjusting font sizes, content placement, and other design elements to provide an excellent experience for users on smaller screens.

Our commitment to responsive design and continuous improvement has ensured that our website is accessible and visually appealing across a wide range of devices, delivering a seamless browsing experience to all visitors.

## 6. Demonstrate a mobile-first approach to building a website

In the development of our website for Sky & Fly Agency, we have adhered to a mobile-first approach, prioritizing the mobile user experience and progressively enhancing it for larger screens. This strategy ensures that our website is accessible and user-friendly on a wide range of devices.

### Mobile-First Design Philosophy

Our mobile-first approach involves designing and building the website with mobile devices as the primary target. This means that we have created a layout and user interface that is optimized for smaller screens. All design decisions, such as typography, layout, and content placement, were initially tailored to provide the best experience for mobile users.

### Ensuring Visibility with Z-Index

```
.header {
  position: fixed;
  width: 100%;
  background: #ffffff;
  z-index: 3;
}
```

To enhance the mobile user experience, we have utilized Z-index properties to carefully manage the stacking order of elements on the page. This ensures that essential content remains visible and easily accessible, even on smaller screens. Z-index has been instrumental in preventing elements from overlapping and causing usability issues for mobile users.

### Proper Sizing for All Devices

In addition to Z-index, we have made sure that all elements on our website are appropriately sized for the user's device. This includes fonts, images, buttons, and interactive elements. We have created a consistent and visually pleasing experience by ensuring that elements are proportional and user-friendly on all screens.

Our commitment to a mobile-first approach reflects our dedication to providing an exceptional browsing experience for mobile users and progressively enhancing that experience for larger screens. This ensures that all visitors, regardless of their device, can access our content comfortably and intuitively.

## 7. Use CSS variables to apply repeated colours to HTML elements

In our web development project for Sky & Fly Agency, we have maintained a design philosophy where each page of the website has a unique and distinct appearance. As a result, we have not extensively used CSS variables for applying repeated colors to HTML elements.

### Emphasizing Unique Page Designs

Our approach involved giving individual pages a distinct visual identity to create a diverse and engaging user experience. Each page features a unique color palette, typography, and styling to convey its specific purpose and content. This approach ensures that the website offers a fresh and captivating look across various sections.

### Tailoring Colors to Page Context

To create a cohesive design within each page, we have manually tailored and specified the color choices that best suit the context and theme of that particular section. This level of customization ensures that the color scheme aligns perfectly with the content and overall design intentions of each page.

<div align="center">
 
![image](https://github.com/Estishi87/Esti-Portfolio/assets/125391502/f60df8a4-ef89-43cb-a8e0-976b673be27c)

 <br ></div>


While CSS variables are a powerful tool for applying consistent colors to HTML elements, our decision to forgo them in favor of tailored color choices has allowed us to provide a visually stimulating and dynamic experience for visitors across different sections of our website.

This approach reflects our commitment to creating an engaging and immersive user experience, ensuring that each part of our website is a captivating journey in itself.

## 8. Use CSS Flexbox to style children in a single-direction layout (ie a row or a column)
In our web development project for Sky & Fly Agency, CSS Flexbox has played a pivotal role in creating flexible and responsive layouts, particularly for arranging elements in a single-direction format, such as rows or columns.

### Embracing Flexbox for Layout

We have adopted a primarily flexbox-based layout approach, which provides an elegant solution for structuring and styling elements within sections of our website. Flexbox allows us to effectively sort and align objects, ensuring a visually appealing and harmonious presentation of content.

### Example of Flexbox Usage

An illustrative example of our use of flexbox can be seen in the following code snippet:

```css
.content-container {
  display: flex;
}
```


In this snippet, the content-container class is set to a flex display. This simple implementation allows us to arrange child elements within the container in a single direction, facilitating flexible layouts that automatically adjust to different screen sizes.

Our extensive use of flexbox throughout our website ensures that content is presented seamlessly and effectively, maintaining a balanced and visually pleasing appearance regardless of the device being used.

## 9. Use CSS Grid to style children in two-direction layout

In our web development project for Sky & Fly Agency, we have harnessed the power of CSS Grid to create captivating two-direction layouts that enhance the presentation of our content.

### Utilizing Grid for the Team Section

<div align="center">
 
![image](https://github.com/Estishi87/Esti-Portfolio/assets/125391502/1e24cca4-a86e-401d-8e4d-5fe41c3e755e)
 <br ></div>

One notable application of CSS Grid is in our team section, where it has allowed us to present all six team members perfectly and elegantly on a single page. This strategic use of CSS Grid provides an organized and visually appealing layout that showcases our team effectively.

### Example of Grid Usage

The following code snippet exemplifies our use of CSS Grid:

```css
.card-container {
  margin-top: 1rem;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  align-items: center;
  gap: 1.7rem;
  padding-left: 10%;
  padding-right: 10%;
}
```

In this snippet, the card-container class is styled as a grid layout with three equal-width columns, creating an aesthetically pleasing arrangement for our team members' cards. The defined gap and padding attributes further contribute to a harmonious and structured presentation.

CSS Grid has enabled us to create engaging and visually coherent layouts that align with our design principles. Its implementation in our team section exemplifies our commitment to providing a user-friendly and aesthetically pleasing browsing experience.

## 10. Ensure our Git commit history tells a coherent story

![image](https://github.com/Estishi87/Esti-Portfolio/assets/125391502/8cccc6f6-b933-492a-a720-5d61c2b022fd)



In the development of our website for Sky & Fly Agency, we have placed a strong emphasis on keeping our Git commit history coherent and meaningful. A well-maintained commit history is essential for understanding the evolution of our project and collaborating effectively.

### Committing Small Changes Regularly

Throughout the development process, we have adopted a practice of committing small, incremental changes regularly. This approach allows us to break down our work into manageable pieces and ensures that each commit focuses on a specific task or improvement.

### Providing Explanatory Commit Messages

For each commit, we have made it a standard practice to provide a clear and concise explanation of the changes made. These commit messages serve as a communication tool, making it easier for other team members and our future selves to understand the purpose and context of each change.

By maintaining a coherent Git commit history with detailed commit messages, we ensure that the evolution of our project is well-documented and easy to follow. This approach enhances collaboration, facilitates issue tracking, and supports the ongoing development and maintenance of our website.

## 11. Use the appropriate input types in HTML forms for gathering different types of information

In our web development project for Sky & Fly Agency, we have carefully chosen and implemented the appropriate input types in HTML forms to gather different types of information from users. This ensures that user interactions are both intuitive and efficient.

### Contact Form Example

An illustrative example can be found in our contact form, where we have employed various input types to capture specific information:

```html
<fieldset>
  <div class="contact-row">
    <div class="contact-input-1" data-id="full-name">
      <label for="name"> Your Name</label>
      <input id="name" placeholder="Aviation Lover" type="text" name="name" required="required">
    </div>
    <div class="contact-input-1" data-id="email">
      <label for "email"> Email Address</label>
      <input id="email" placeholder="Enter your email" type="email" name="_replyto" required="required">
    </div>
  </div>
  <div class="contact-row">
    <div class="contact-input-2" data-id="message">
      <label for="message"> Your Message</label>
      <textarea placeholder="Hi, I'm passionate about your company and would like to..." id="message" name="message"
        required="required" rows="7"></textarea>
    </div>
  </div>
  <button class="send-button" type="submit" id="send-button" onclick="sendMail()">
    SUBMIT ✈
  </button>
</fieldset>
```

In this code snippet, we've used type="text" for capturing the user's name, type="email" for collecting email addresses, and textarea for longer text entries. Each input type is chosen to match the type of information we are gathering, ensuring a user-friendly and effective data collection process.

Our commitment to using the appropriate input types reflects our dedication to providing a seamless and user-centric experience, making it easy for visitors to provide the information we need.
