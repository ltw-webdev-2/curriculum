---
layout: slide-deck
title: "Modular CSS"
desc: "A introduction to Modular CSS, writing code for patterns, and a tool, Modulifier, to help simplify use."

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
    notes: |
      **Buttons**—3 different starter buttons styles
    html: |
      <link href="css/modules.css" rel="stylesheet">

      <a class="btn">Go!</a>
      <a class="btn btn-light">Go, Go Power Rangers!</a>
      <a class="btn btn-ghost">Thunderbirds are Go!</a>
    css_hidden: |
      a {
        margin-bottom: 1em;
      }

  - type: interactive
    notes: |
      **List groups**—bullet-less horizontal & vertical lists
    html: |
      <link href="css/modules.css" rel="stylesheet">

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
    notes: |
      **Icons**—icon classes for different common sizes with & without labels
    html: |
      <link href="css/modules.css" rel="stylesheet">

      <i class="icon i-18"><img src="images/icon.svg" alt=""></i>
      <span class="icon-label">Icons ahoy!</span>

      <i class="icon i-64"><img src="images/icon.svg" alt=""></i>
      <span class="icon-label">Icons-r-us!</span>

  - type: interactive
    resizable: true
    notes: |
      **Embed containers**—make images & videos responsive, in a way that space is made available before the media finishes downloading
    html: |
      <link href="css/modules.css" rel="stylesheet">

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
      - [**Modulifier cheat sheet ➔**](/topics/modulifier-cheat-sheet/)

---
