---
layout: lesson
title: "Basic accessibility"
desc: "A quick look at some basic additions to a website to make it more accessible."

markbot_submit: true
hide_show_for_marks: true

extra_tutorials:
  - title: "Accessibility"
    url: accessibility
  - title: "Accessibility checklist"
    url: accessibility-checklist
    highlight: true
  - title: "Accessibility slide deck"
    url: "/courses/web-dev-3/accessibility/"

goal:
  no_image: true
  image: goal.png
  before: |
    We’re going to explore some additions we can make to our website to make it more accessible.

    Modulifier is already providing a bunch of accessibility features for us—assuming the “Accessibility” module is enabled.
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

important:
  title: "Accessibility is really broad"
  text: |
    **There is so much to making an accessible website. The list below is a good start but should not be considered “all there is”.**

    The only way to truly test website accessibility is with live user feedback. Find people and test your website with their different conditions and tools.

fork:
  url: "https://github.com/acgd-webdev-2/basic-accessibility"

steps:
  - title: "Project setup"
    before: |
      We’re going to start a website from scratch, so we can completely concentrate on just the accessibility.

      After forking & cloning the repository, create the following files in your folder.
    folders:
      - label: "basic-accessibility"
        type: folder
      - label: "css"
        type: folder
        indent: 1
      - label: "modules.css"
        indent: 2
      - label: "index.html"
        indent: 1
    after: |
      Let’s add some basic code to the files now.

      1. Fill the `index.html` with the default boilerplate.
      2. [Go to Modulifier](https://modulifier.web-dev.tools/) and get a fresh copy—select all modules—and link up the `modules.css` file.

      *We’re not even going to bother with a `main.css` because we’re not going to touch any CSS in this lesson.*

      **You can find the text inside the `content.txt` file.**
    notes:
      - label: "HTML snippets"
        text: "Create the boilerplate with `html5`, `viewport` & `css`"
  - title: "Use good semantics"
    before: |
      The first, most important, thing that helps accessibility is proper semantics. *Every website should be sure to use the most appropriate tags where possible.*
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </head>
      <body>

        <header>
          <h1>Pangolin</h1>
          <nav>
            <ul>
              <li><a href="#">Description</a></li>
              <li><a href="#">Behaviour</a></li>
              <li><a href="#">Conservation</a></li>
            </ul>
          </nav>
        </header>

        <main>
          <section>
            <h2>Description</h2>
          </section>

          <section>
            <h2>Behaviour</h2>
          </section>

          <section>
            <h2>Conservation</h2>
          </section>
        </main>

        <footer>
          <small>© 1821 Pangolin</small>
        </footer>

      </body>
      </html>
    lines:
      - num: "2-4"
        fade: true
      - num: "34-35"
        fade: true
    after: |
      Make sure every, single page has:

      - `<title>` — that’s unique to every page
      - `<header>`
      - `<nav>`
      - `<main>`
      - `<footer>`
      - `<h1>` — that’s unique to every page
      - Proper heading structure
      - Any other semantically appropriate tags…

  - title: "Link sections"
    before: |
      It’s a good idea to link important sections of the document to the navigation, if it’s single page, to make keyboard navigation much better.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
          <h1>Pangolin</h1>
          <nav>
            <ul>
              <li><a href="#description">Description</a></li>
              <li><a href="#behaviour">Behaviour</a></li>
              <li><a href="#conservation">Conservation</a></li>
            </ul>
          </nav>
        </header>

        <main>
          <section id="description" tabindex="0">
            <h2>Description</h2>
          </section>

          <section id="behaviour" tabindex="0">
            <h2>Behaviour</h2>
          </section>

          <section id="conservation" tabindex="0">
            <h2>Conservation</h2>
          </section>
        </main>
      ⋮
    lines:
      - num: "2-4"
        fade: true
      - num: "5-7"
        text: |
          Add ID hash links to the internal page navigation.
      - num: "8-12"
        fade: true
      - num: 13
        text: |
          Add the matching `id="…"` attributes to the appropriate sections.

          We also need to add `tabindex="0"` to these elements. This helps keyboard tabbing order by focusing the `<section>` elements when the links are clicked.
      - num: "14-16"
        fade: true
      - num: 17
      - num: "18-20"
        fade: true
      - num: 21
      - num: "22-24"
        fade: true

  - title: "Add ARIA landmark roles"
    before: |
      The [Web Accessibility Initiative (WAI)](https://www.w3.org/WAI/) has a series of recommendations to make websites more accessible, an important specification is [Accessible Rich Internet Applications (ARIA)](https://www.w3.org/WAI/ARIA/).

      One of the major things ARIA adds is a “role” system, where we can define specific elements as being important landmarks on the page.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </head>
      <body>

        <header role="banner">
          <h1>Pangolin</h1>
          <nav role="navigation">
            <ul>
              <li><a href="#description">Description</a></li>
              <li><a href="#behaviour">Behaviour</a></li>
              <li><a href="#conservation">Conservation</a></li>
            </ul>
          </nav>
        </header>

        <main role="main">
          <section>
            <h2>Description</h2>
          </section>

          <section>
            <h2>Behaviour</h2>
          </section>

          <section>
            <h2>Conservation</h2>
          </section>
        </main>

        <footer role="contentinfo">
          <small>© 1821 Pangolin</small>
        </footer>

      </body>
      </html>
    lines:
      - num: "2-4"
        fade: true
      - num: "31-35"
        fade: true
      - num: 5
        text: |
          The masthead of the website should always have the role of `banner`
      - num: 6
        fade: true
      - num: 7
        text: |
          The primary navigation should always have the role of `navigation`
      - num: "8-15"
        fade: true
      - num: 16
        text: |
          The main content of the page should always have the role of `main`
      - num: "17-29"
        fade: true
      - num: 30
        text: |
          The website footer, where the copyright notice, and terms of use, etc. are should always have the role of `contentinfo`

          If the `<footer>` contains more than just the copyright notice, like social media links, a secondary navigation, contact information, then `role="contentinfo"` should be on something else that contains only the copyright notice, etc. only
    after: |
      **These landmark roles should only be used once per page—only one `<header>` can be `banner`, only one `<nav>` can be `navigation`, etc.**

  - title: "Add skip links"
    before: |
      Skip links are hidden links that allow keyboard users to jump to specific points on the page.

      Ideally they shouldn’t be hidden, but most picky designers (that’s you) think they’re ugly and want them to be hidden. *If they are hidden, it’s extremely important that they become visible when the keyboard navigates to them.*

      (Modulfier already has skip links built into it.)
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </head>
      <body>

        <ul class="skip-links">
          <li><a href="#main">Jump to main content</a></li>
          <li><a href="#nav">Jump to navigation</a></li>
        </ul>

        <header role="banner">
          <h1>Pangolin</h1>
          <nav role="navigation" id="nav" tabindex="0">
            <ul>
              <li><a href="#description">Description</a></li>
              <li><a href="#behaviour">Behaviour</a></li>
              <li><a href="#conservation">Conservation</a></li>
            </ul>
          </nav>
        </header>

        <main role="main" id="main" tabindex="0">
          <section id="description">
            <h2>Description</h2>
      ⋮
    lines:
      - num: "2-3"
        fade: true
      - num: "5-8"
        text: |
          Skip links are essentially just a small list of links—but they must be the very first thing inside the `<body>`

          Modulifier has CSS styles for these already that will hide them by default and only show them when the user navigates with the keyboard.
      - num: "9-11"
        fade: true
      - num: 12
        text: |
          Make sure to add IDs to the appropriate elements on the page.

          And also make sure to add the `tabindex="0"` to help with keyboard focus.
      - num: "13-19"
        fade: true
      - num: 21
      - num: "22-23"
        fade: true
    after: |
      Open the website in your browser and press `Tab` to navigate around with the keyboard—you should see the skip links pop up when you’re moving around.

  - title: "Better image alternatives"
    before: |
      Let’s say that we have an image on our website—but it doesn’t make sense to use a `<figure>` element, maybe because it’s described much further down the page.

      Maybe in this situation, the `alt="…"` attribute is too limiting: we can’t describe all our content in a single sentence. But it’d still be nice to provide an alternative.

      ARIA provides an `aria-details` attribute that allows us to point to another HTML element for the `alt` instead.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <main role="main" id="main" tabindex="0">
        <img src="images/map.jpg" alt="" aria-details="countries">

        <section id="description">
          <h2>Description</h2>

          <div id="countries">
            <h3>Some countries where pangolins are found</h3>
            <ol>
              <li>Botswana</li>
              <li>Kenya</li>
              <li>Mozambique</li>
              <li>Namibia</li>
              <li>South Africa</li>
              <li>Tanzania</li>
              <li>Uganda</li>
              <li>Zambia</li>
              <li>Zimbabwe</li>
            </ol>
          </div>
        </section>
      ⋮
    lines:
      - num: 2
        fade: true
      - num: 3
        text: |
          The new `<img>` tag here has an empty `alt=""` attribute and uses the `aria-details="…"` attribute to point to the ID of an HTML element in another location on the page that describes the image fully.
      - num: "5-6"
        fade: true
      - num: "8-21"
        text: |
          The element that `aria-details="…"` points to must have a matching `id="…"` attribute.
      - num: 22
        fade: true

  - title: "Better link alternatives"
    before: |
      Let’s say we have a few “Read more” links on the page. All the text inside each `<a>` tag says exactly “Read more” but each link points to a different location.

      From an accessibility point-of-view, that’s really confusing because the same text, points to different places.

      ARIA provides another attribute for us to give a little extra text to elements to help with accessibility—the `aria-label="…"` attribute.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
          </ol>
        </section>

        <section id="behaviour">
          <h2>Behaviour</h2>
          <a href="https://en.wikipedia.org/wiki/Pangolin#Behavior" aria-label="Read more about Pangolin behaviour">Read more</a>
        </section>

        <section id="conservation">
          <h2>Conservation</h2>
          <a href="https://en.wikipedia.org/wiki/Pangolin#Conservation" aria-label="Read more about Pangolin conservation">Read more</a>
        </section>
      </main>
      ⋮
    lines:
      - num: "2-6"
        fade: true
      - num: 7
        text: |
          The `aria-label="…"` attribute can be added to elements to give them a better, more descriptive text representation.

          Accessibility tools will present `aria-label="…"` to users instead of the text inside the element.
      - num: "8-11"
        fade: true
      - num: 12
      - num: "13-14"
        fade: true

  - title: "Link focus states"
    before: |
      We don’t actually have to do anything right now. Browsers have default focus states for links and *Modulifier changes them to be large black outlines*.

      *Try navigating around the page using the `Tab` key.*

      ![](focus.png)

      **Those black boxes that surround links are extremely important for accessibility access and should never be removed.** You’re welcome to style them a little to make sure there’s enough contrast with the background—because black boxes won’t show up on a dark background.
    after: |
      **That’s absolutely not all there is to accessibility.** Much more testing needs to be done with accessibility validators and tools like VoiceOver.

---
