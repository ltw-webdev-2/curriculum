---
layout: lesson
title: "Data table"
desc: "Create a chart of data using HTML table elements."

markbot_submit: true
hide_show_for_marks: true

extra_tutorials:
  - title: "Tables slide deck"
    url: "/courses/web-dev-2/tables/"
  - title: "Tables"
    url: tables
  - title: "Tables cheat sheet"
    url: tables-cheat-sheet
    highlight: true

goal:
  image: goal.png
  before: |
    We’re going to walk through taking some information and converting it into a data chart using HTML table elements & tags.
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

fork:
  url: "https://github.com/acgd-webdev-2/data-table/fork"

steps:
  - title: "Project setup"
    before: |
      To save some time with this lesson I’ve set up some basic files and put some basic content into the HTML that we’ll work from.
    folders:
      - label: "data-table"
        type: folder
      - label: "css"
        type: folder
        indent: 1
      - label: "main.css"
        indent: 2
      - label: "modules.css"
        indent: 2
      - label: "type.css"
        indent: 2
      - label: "index.html"
        indent: 1
    after: |
      This repo has the HTML boilerplate and all the CSS files hooked up.

      The content we’ll need is already inside the `index.html` we just have to wrap it in the right tags.

  - title: "Create the table header row"
    before: |
      Let’s start the data table by creating the header row with the labels for each column.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <main>
        <div>
          <h1>Exoplanets</h1>

          <table border="1">
            <caption>NASA has announced the discovery of over 1000 exoplanets—below are five important discoveries.</caption>
            <thead>
              <tr>
                <th scope="col">Name</th>
                <th scope="col">Orbiting star</th>
                <th scope="col">Year of discovery</th>
                <th scope="col">Distance</th>
                <th scope="col">Notes</th>
              </tr>
            </thead>

      ⋮
    lines:
      - num: "2-4"
        fade: true
      - num: 6
        text: |
          Everything about a data table needs be wrapped by the `<table>` tag.

          The `border="1"` is a temporary attribute we’ll add to see all the edges of the cells. This must be removed from the final table—it’s really just a development tool.

          We’ll close `<table>` later when we get to the bottom of the information.
      - num: 7
        text: |
          Think of the `<caption>` tag as being like an `alt=""` attribute for images. It’s a summary of the information found in the table.

          Unlike an `alt=""` attribute though, the `<caption>` is always visible—and should always be visible.
      - num: 8
        text: |
          The `<thead>` tag defines a series of rows as being the header of the table.
      - num: 9
        text: |
          The `<tr>` element defines a row within the table.
      - num: 10
        text: |
          The `<th>` tag is used to create a cell, a specialized cell, a heading cell.

          The `scope="col"` attribute tells the browser and accessibility tools that this heading labels the column.

  - title: "Create the rows of data"
    before: |
      The next step is to create the five rows of data for our table. Each row will represent all the information for a single exoplanet.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
          <th class="notes" scope="col">Notes</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">PSR B1257+12 A</th>
          <td>Lich pulsar</td>
          <td>1992</td>
          <td>2300 ly</td>
          <td>First confirmed exoplanet</td>
        </tr>

        <!-- Copy and paste the row above to populate the remaining four exoplanets -->

      ⋮
    lines:
      - num: "2-4"
        fade: true
      - num: 5
        text: |
          The `<tbody>` tag is used to wrap around the rows of the data table that represent the primary information.
      - num: 6
        text: |
          Each row starts with the `<tr>` tag to define the row of information.
      - num: 7
        text: |
          The first cell of each row is a `<th>` tag to denote a heading for the whole row.

          Notice that it’s scope is set to `scope="row"` to define that it’s a heading for the row.
      - num: "8-11"
        text: |
          The rest of the data sits in basic `<td>` tags.
    after: |
      **The remaining 4 rows are up to you.** Copy and paste the above row and populate it with the information for the rest of the exoplanets.

  - title: "Add the table footer"
    before: |
      To finish off the `<table>` we’re going to put in the footer information: the totals, etc.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
                <td>1000th exoplanet discovered</td>
              </tr>
            </tbody>
            <tfoot>
              <tr>
                <th scope="row">Total</th>
                <td colspan="4">5</td>
              </tr>
            </tfoot>
          </table>
        </div>
      </main>
      ⋮
    lines:
      - num: "2-3"
        fade: true
      - num: "12-13"
        fade: true
      - num: 4
        text: |
          Don’t forget to close the `</tbody>` tag!
      - num: 5
        text: |
          The `<tfoot>` is the final row grouping tag, it’s to define rows of a table that are totals and extra information.
      - num: 7
        text: |
          Another row heading for this row.
      - num: 8
        text: |
          Notice the `colspan="4"` attribute on this `<td>`. I don’t want to put a bunch of blank cells across the row because every row must have the same number of cells.

          The `colspan="4"` attribute is telling this cell to merge and stretch so that it takes up the space of “4 columns”
      - num: "10-11"
        text: |
          Don’t forget to add the closing the `</tfoot>` and `</table>` tags.
    after: |
      Now that we’ve got all the `<table>` tags and data in place we can check it out in the browser.

      This is what you should see:

      ![](basic-table.png)

      **Notice of the total planets cell is stretching across four columns because of the `colspan="4"` attribute.**

      *That grey background colour is already in your `main.css`*

  - title: "Remove the default border"
    before: |
      Now that we’re happy with the layout of the rows and columns & everything looks good we **must** remove the `border="1"` attribute.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <main>
        <div>
          <h1>Exoplanets</h1>

          <table>
            <caption>NASA has announced the discovery of over 1000 exoplanets—below are five important discoveries.</caption>
            <thead>
      ⋮
    lines:
      - num: "2-4"
        fade: true
      - num: "7-8"
        fade: true
      - num: 6
        text: |
          No more `border="1"`

  - title: "Add the Web Dev Tools"
    before: |
      The default look of tables is pretty abysmal—Typographier has some slightly nicer table defaults, do let’s add that code into your website.
    folders:
      - label: "data-table"
        type: folder
      - label: "css"
        type: folder
        indent: 1
      - label: "main.css"
        indent: 2
        fade: true
      - label: "modules.css"
        indent: 2
        notes: "Get the code and paste it"
      - label: "type.css"
        indent: 2
        notes: "Get the code and paste it"
      - label: "index.html"
        indent: 1
        fade: true
    after: |
      *The web dev tools CSS files need to be populated:*

      - Go to [Modulifier](http://modulifier.web-dev.tools/) and copy the default CSS into `modules.css`—**be sure to press “Select all”**
      - Go to [Typografier](http://typografier.web-dev.tools/) and copy the default CSS into `type.css`

      *We’re not using a grid for this lesson so it doesn’t need to be included.*

      With the web dev tools in place, it looks better:

      ![](web-dev-tools.png)

      *Admittedly though, things are still a little whacky—we’ll fix it next.*

  - title: "Some basic styles"
    before: |
      Now that we have access to Typografier, let’s add some of those classes onto things.
    multi_code:
      - code_lang: "html"
        code_file: "index.html"
        code: |
          ⋮
          <body>

            <main class="pad-t-2 pad-b-2 gutter-1-2">
              <div class="wrapper">
                <h1>Exoplanets</h1>

                <table class="push-0">
                  <caption class="mega">NASA has announced the discovery of over 1000 exoplanets—below are five important discoveries.</caption>
                  <thead>
          ⋮
        lines:
          - num: 2
            fade: true
          - num: 4
            text: "Add some gutters and padding to the `<main>` tag."
          - num: 5
            text: "Add `.wrapper` to the `<div>` to contain everything to a nice size."
          - num: 6
            fade: true
          - num: 8
            text: "Remove the default margins from the bottom of the `<table>`"
          - num: 9
            text: "Let’s maake the caption a little bigger so it stands out from the rest of the text, using the `.mega` class."
          - num: 10
            fade: true
      - code_before: |
          Let’s style a little bit of the typography in the table’s body rows to make it a little more pleasing.
        code_lang: "html"
        code_file: "index.html"
        code: |
          ⋮
          </thead>
          <tbody>
            <tr>
              <th class="not-bold italic" scope="row">PSR B1257+12 A</th>
              <td>Lich pulsar</td>
              <td>1992</td>
              <td>2300 ly</td>
              <td>First confirmed exoplanet</td>
            </tr>
          ⋮
        lines:
          - num: 5
            text: |
              Let’s target the headings cells (`<th>`) in the `<tbody>` and remove the `bold` and add `italic`
      - code_before: |
          **Be sure to apply the `.not-bold` & `.italic` classes to all the `<th>` tags inside the `<tbody>`**

          And finally we’ll make the footer of the table completely bold.
        code_lang: "html"
        code_file: "index.html"
        code: |
          ⋮
            </tbody>
            <tfoot class="bold">
              <tr>
                <th scope="row">Total</th>
                <td colspan="4">5</td>
              </tr>
            </tfoot>
          </table>
          ⋮
        lines:
          - num: "2,4-10"
            fade: true
          - num: 3
            text: |
              Add the `.bold` class to the `<tfoot>`

    after: |
      Things look a little better now:

      ![](with-type.png)

  - title: "Some more custom styles"
    before: |
      Let’s open up our `main.css` and add one more custom style to the table: “zebra striping”.
    code_lang: "css"
    code_file: "css/main.css"
    code: |
      ⋮
      main {
        background-color: #f2f2f2;
      }

      tbody tr:nth-child(odd) {
        background-color: #e2e2e2;
      }
    lines:
      - num: "2-4"
        fade: true
      - num: "6-8"
        text: |
          This will select every odd-numbered row in the table and add a background colour—making it easier to separate the rows visually. This is called “zebra striping”.
    after: |
      Should look like this now:

      ![](zebra-stripes.png)

  - title: "Fix the column widths"
    before: |
      Tables automatically layout based on the content inside, but it doesn’t always create an optimal width for the columns of text. So let’s add some widths to the columns to make it better.
    multi_code:
      - code_lang: "html"
        code_file: "index.html"
        code: |
          ⋮
          <thead>
            <tr>
              <th class="name" scope="col">Name</th>
              <th class="star" scope="col">Orbiting star</th>
              <th class="year" scope="col">Year of discovery</th>
              <th class="distance" scope="col">Distance</th>
              <th class="notes" scope="col">Notes</th>
            </tr>
          </thead>
          ⋮
        lines:
          - num: "2-3"
            fade: true
          - num: "9-10"
            fade: true
          - num: "4-8"
            text: |
              Add a new `class` to each of the `<th>` tags so we can distinguish them in our CSS.
      - code_before: |
          Now add the widths into our CSS.
        code_lang: "css"
        code_file: "css/main.css"
        code: |
          ⋮
          tfoot {
            font-weight: bold;
          }

          .year {
            width: 7em;
          }

          .distance {
            width: 6em;
          }

          .notes {
            width: 16em;
          }
        lines:
          - num: "2-4"
            fade: true
    after: |
      *The widths for each of the columns aren’t some magic numbers—I just used the developer tools to change the width of the columns until I found a layout that looked nice to my eyes.*

      ![](widths.png)

  - title: "Make the table responsive"
    before: |
      Tables aren’t very responsive—but there are lots of different techniques we can use to help make them a little more responsive:

      - Make the table horizontally scrollable
      - Hide the table on small screens & show an alternative layout
      - Use the CSS `display` property to overwrite the table into `inline` & `block` on small screen
      - Use JavaScript to hide non-critical columns and allow people to hide & show the columns

      Well, we’re going to go with the horizontally scrollable table. It’s simple to implement and has okay user experience, but not as optimized as some of the other solutions.

      First we’ll surround the table in a new `<div>`.
    multi_code:
      - code_lang: "html"
        code_file: "index.html"
        code: |
          ⋮
          <main class="pad-t-2 pad-b-2 gutter-1-2">
            <div class="wrapper">
              <h1>Exoplanets</h1>

              <div class="table-wrapper scrollable">
                <table class="push-0">
                  <caption>NASA has announced the discovery of over 1000 exoplanets—below are five important discoveries.</caption>
          ⋮
        lines:
          - num: "2-4"
            fade: true
          - num: "7-8"
            fade: true
          - num: 6
            text: |
              We’ll also add two classes to the `<div>`:

              1. `.table-wrapper` — just made that up right now.
              2. `.scrollable` — a class from Modulifier that adds horizontal scrollbars when necessary. Don’t abuse this class—it’s very, very nasty.
      - code_before: |
          Further down the page, don’t forget to add the closing `</div>` tag.
        code_lang: "html"
        code_file: "index.html"
        code: |
          ⋮
                      <th scope="row">Total</th>
                      <td colspan="4">5</td>
                    </tr>
                  </tfoot>
                </table>
              </div>
            </div>
          </main>
          ⋮
        lines:
          - num: "2-6"
            fade: true
          - num: "8-9"
            fade: true
          - num: 7
      - code_before: |
          Now a little bit of CSS to finish the responsiveness off.
        code_lang: "css"
        code_file: "css/main.css"
        code: |
          ⋮
          .notes {
            width: 16em;
          }

          table {
            min-width: 50em;
          }

          @media only screen and (min-width: 60em) {

            .table-wrapper {
              overflow: visible;
            }

          }
        lines:
          - num: "2-4"
            fade: true
          - num: "6-8"
            text: |
              First we disallow the `<table>` from getting narrower than looks good.

              This isn’t a magic number—I just used the developer tools to make the screen narrow until the table started to look awkward, took the pixel width and divided by 16 to get `em`s.
          - num: "10-16"
            text: |
              Force the horizontal scrollbar to be permanently off at the large screen size.
    after: |
      Now when we shrink the screen down we should be able to scroll horizontally.

      ![](responsive.png)

---
