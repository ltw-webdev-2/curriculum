---
layout: slide-deck

title: "Modular CSS"

slides:
  - type: super-big-text
    content: |
      **Modular CSS**

  - content: |
      ## Why?

      *Because we write the same CSS over and over*

      - `@viewport…`
      - `box-sizing: border-box`;
      - `body { margin: 0; }`
      - `.img-flex`
      - `list-style-type: none`
      - .etc

  - content: |
      ## We see the same patterns repeated

      - Lists without bullets
      - Horizontal lists
      - Responsive images & videos
      - Icons beside text
      - Buttons

  - content: |
      ## A pattern library

      - A bunch of CSS classes to reduce what we type
      - Common layouts that we do on many websites

  - content: |
      ## Modulifier

      *I don’t want to have to write the same code every time!*

      - Generates a whole pattern library

      [**Modulifier »**](https://modulifier.web-dev.tools)

  - type: interactive
    html: |
      <link href="css/modules.css" rel="stylesheet">

      <!--
        Buttons
        • 3 default button styles to start code with
      -->

      <a class="btn">Go!</a>
      <a class="btn btn-light">Go, Go Power Rangers!</a>
      <a class="btn btn-ghost">Thunderbirds are Go!</a>
    css_hidden: |
      a {
        margin-bottom: 1em;
      }

  - type: interactive
    html: |
      <link href="css/modules.css" rel="stylesheet">

      <!--
        List groups
        • Bullet-less horizontal/vertical lists
      -->

      <ul class="list-group">
        <li>Diplodocus</li>
        <li>Apatosaurus</li>
        <li>Brontosaurus</li>
      </ul>

      <ul class="list-group-inline">
        <li>Velociraptor</li>
        <li>Microraptor</li>
      </ul>

  - type: interactive
    html: |
      <link href="css/modules.css" rel="stylesheet">

      <!--
        Icons
        • Different icon sizes with/out labels
      -->

      <i class="icon i-18"><img src="images/icon.svg" alt=""></i>
      <span class="icon-label">Icons ahoy!</span>

      <i class="icon i-64"><img src="images/icon.svg" alt=""></i>
      <span class="icon-label">Icons-r-us!</span>

  - type: interactive
    resizable: true
    html: |
      <link href="css/modules.css" rel="stylesheet">

      <!--
        Embed containers
        • Responsive images & videos
      -->

      <div class="embed embed-16by9">
        <img class="embed-item" src="images/placeholder-16by9.svg" alt="">
      </div>

      <div class="embed embed-16by9">
        <iframe class="embed-item" src="https://www.youtube.com/embed/tpuhLkh358Y" frameborder="0" allowfullscreen></iframe>
      </div>
    css_hidden: |
      div {
        margin-bottom: 1em;
      }

  - content: |
      ## Videos & tutorials

      - [Modules ➔](/topics/modules/)
      - [**Modulifier »**](https://modulifier.web-dev.tools/)
      - [Modulifier cheat sheet ➔](/topics/modulifier-cheat-sheet/)

---
