---
layout: slide-deck
title: "Tables"
desc: "A quick introduction to HTML table syntax and styling."

slides:
  - type: super-big-text
    content: |
      **Tables**

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
      ## Every row must have the same number of cells

      Cells can be merged to make larger cells—but must still add up

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
      ## Videos & tutorials

      - [Tables ➔](/topics/tables/)
      - [Tables cheat sheet ➔](/topics/tables-cheat-sheet/)

---
