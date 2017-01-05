---
layout: slide-deck

title: "Tables & forms"

slides:
  - type: super-big-text
    content: |
      **Tables & forms**

  - content: |
      ## Tables

      *Column/row data information—like Excel or Numbers*

      <table>

        <thead>
          <tr>
            <th scope="col">Name</th>
            <th scope="col">Period</th>
            <th scope="col">Discovery</th>
          </tr>
        </thead>

        <tbody>
          <tr>
            <th scope="row">Stegosaurus</th>
            <td>Late Jurassic</td>
            <td>1877</td>
          </tr>
          <tr>
            <th scope="row">Apatosaurus</th>
            <td>Jurassic Period</td>
            <td>1877</td>
          </tr>
        </tbody>

        <tfoot>
          <tr>
            <th scope="row">Total</th>
            <td colspan="2">2 dinosaurs</td>
          </tr>
        </tfoot>

      </table>

  - content: |
      ## Building tables

      1. Define a row
      ![](define-row.svg)

      2. Split the row into chunks (cells)
      ![](split-to-cells.svg)

  - content: |
      ## Every row must have the same number of cells.

      Cells can be merged to make larger cells—but must still add up.

  - type: code
    html: |
      <table>                 <!-- Everything goes inside this element -->
        <caption>             <!-- For accessibility: a short description, like `alt` -->

        <thead>               <!-- Groups the “header” rows: column labels, etc. -->
        <tbody>               <!-- Groups the “main body” rows: actual data -->
        <tfoot>               <!-- Groups the “footer” rows: totals, etc. -->

          <tr>                <!-- Defines a row of data in the table -->

            <th>              <!-- Defines a column/row heading -->
            <td>              <!-- Defines a piece of data in the table -->

            <th scope="col">  <!-- `scope` defines the heading’s direction -->
            <td rowspan="3">  <!-- `rowspan` merges a cell vertically, across rows -->
            <td colspan="2">  <!-- `colspan` merges a cell horizontally, across cells -->

  - type: interactive
    html: |
      <table>
        <thead>
          <tr>
            <th scope="col">Resource</th>
            <th scope="col">Cost</th>
            <th scope="col">Available</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <th>Wood</th>
            <td>2 moneys</td>
            <td>4</td>
          </tr>
          <tr>
            <th>Wheat</th>
            <td>1 money</td>
            <td>6</td>
          </tr>
        </tbody>
      </table>
    css_hidden: |
      table {
        font-size: .875rem;
        border-collapse: collapse;
      }
      th, td {
        padding: .2em;
        text-align: left;
        border-bottom: 2px solid #e2e2e2;
      }
      tbody th {
        font-weight: normal;
        font-style: italic
      }

  - content: |
      ## Forms

      *Collection user information*

      - HTML by itself cannot do anything with the data.
      - Most often a server is needed to process the information—and a server language: PHP, Ruby, Python, Javascript, etc.
      - But Javascript can do quite a bit of processing in the browser.

  - content: |
      ## Do not use forms unless absolutely necessary

      Forms are a usability hurdle—especially on mobile.

      Contact forms are stupid—they do nothing more than a simple email address.

      *Use only if collecting very specific information.*

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
          <input id="username">
        </div>
        <div>
          <label for="password">Password</label>
          <input type="password" id="password">
        </div>
        <div>
          <button type="submit">Sign In</button>
        </div>
      </form>

  - content: |
      ## Videos & tutorials

      - [Tables ➔](/topics/tables/)
      - [Forms ➔](/topics/forms/)
      - [Tables cheat sheet ➔](/topics/tables-cheat-sheet/)
      - [Forms cheat sheet ➔](/topics/forms-cheat-sheet/)

---
