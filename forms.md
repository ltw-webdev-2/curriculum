---
layout: slide-deck
title: "Forms"
desc: "An introduction to use HTML form elements to collect information from users."

slides:

  - type: super-big-text
    content: |
      **Forms**

  - content: |
      ## Forms

      *Collecting user information*

      - HTML by itself cannot do anything with the data
      - Most often a server is needed to process the information—and a server language: PHP, Ruby, Python, JavaScript, etc.
      - But JavaScript can do quite a bit of processing in the browser

  - content: |
      ## Do not use forms unless absolutely necessary

      Forms are a usability hurdle—especially on mobile

      Contact forms are stupid—they do nothing more than what a simple email address does

      *Use forms only if collecting very specific information*

  - type: code
    html: |
      <form method="POST" action="…">   <!-- Surrounds every form element -->

        <label for="…">                 <!-- The text label for a control — ALWAYS REQUIRED -->
        <input type="…" id="…">         <!-- An input control, lots of different types -->

        <select id="…">                 <!-- A dropdown menu box -->
          <option>                      <!-- An entry inside the <select> -->

        <textarea id="…">               <!-- A large, multi-line text field -->

        <button type="submit">          <!-- Submission button — sends data, does not link to other pages -->

        <fieldset>                      <!-- To group fields together, like address fields -->
          <legend>                      <!-- A label for the group of fields -->

  - type: code
    html: |
      <input type="text" id="…">        <!-- Generic text; `type="text"` is optional -->
      <input type="number" id="…">      <!-- A number, integer or float -->
      <input type="url" id="…">         <!-- A valid URL -->
      <input type="color" id="…">       <!-- A colour; often presents a colour picker -->
      <input type="date" id="…">        <!-- A date; often presents a calendar -->
      <input type="time" id="…">        <!-- A time; often presents a time picker -->
      <input type="email" id="…">       <!-- A valid email address -->
      <input type="password" id="…">    <!-- The typed characters are hidden by bullets -->
      <input type="tel" id="…">         <!-- For collecting a telephone number -->

      <input type="checkbox" id="…">    <!-- The checkmark input -->
      <input type="radio" id="…">       <!-- Those circular inputs where you can only select one -->
      <input type="range" id="…">       <!-- A number slider -->

  - type: interactive
    html: |
      <form method="POST" action="/authenticate">
        <div>
          <label for="username">Username</label>
          <input id="username" required>
        </div>
        <div>
          <label for="password">Password</label>
          <input type="password" id="password" required>
        </div>
        <div>
          <button type="submit">Sign In</button>
        </div>
      </form>
    html_lines:
      - num: 1
        text: |
          All form fields must be wrapped in the `<form>` tag.
      - num: "3-4"
        text: |
          Notice how the `for` attribute of the `<label>` matches the `id` attribute of the `<input>`

          **Form fields must always have a matching label.**
      - num: 8
        text: |
          We can force users to fill out specific fields by adding the `required` attribute onto the form field.
      - num: 11
        text: |
          We use the `<button>` tag to create action buttons within a form. They should have the `type="submit"` attribute which causes the form to send its information.

  - content: |
      ## Videos & tutorials

      - [Forms ➔](/topics/forms/)
      - [Forms cheat sheet ➔](/topics/forms-cheat-sheet/)

---
