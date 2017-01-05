---
layout: slide-deck

title: "Modular type"

slides:
  - type: super-big-text
    content: |
      **Modular type**

  - content: |
      ## Why?

      - More flexible layouts—less work
      - Reduce code duplication
      - Be more declarative & clear
      - Cohesive vertical rhythm
      - Abstracts type size from HTML semantics
      - Easier working on teams

  - content: |
      ## How?

      1. Pick a scale (musical scales are popular)
      2. Use math to calculate all the things
      3. Use only those set classes

  - content: |
      ## All the maths!

      ```
      font-size: base-font-size × type-scale ^ distance-from-base
      line-height: ceil(font-size ÷ base-line-height) × (base-line-height ÷ font-size)
      ```

      *(With a little finessing based on our design eyes.)*

  - content: |
      ## Typografier

      *I don’t want to have to write this code every time!*

      - Generate a whole type system
      - Media query size configuration
      - Type scale selection
      - *And lots more features…*

      [**Typografier »**](https://typografier.web-dev.tools)

  - content: |
      ## Classes for size

      - Different sizes are defined by different classes
      - Each class has an optimized `line-height`
      - 10 different font-sizes—you shouldn’t need more
      - Based on the metric system:
        <br>`.micro, .milli, .kilo, etc.`

  - type: interactive
    resizable: true
    html: |
      <link href="css/type.css" rel="stylesheet">

      <h1 class="micro">Heading Level 1</h1>
      <h2 class="giga">Heading Level 2</h2>
      <p class="yotta">Text block</p>
      <p class="milli">Another text block</p>

  - content: |
      ## Classes for spacing

      - Different classes to add amounts of spacing
      - Spacing is always divisible by `line-height` to fit the vertical rhythm

  - type: interactive
    resizable: true
    html_hidden: |
      <link href="css/type.css" rel="stylesheet">
    html: |
      <h1 class="push-0">Heading Level 1</h1>
      <h2 class="push-2">Heading Level 2</h2>
      <h3 class="island">Heading Level 3</h3>
    css_hidden: |
      h3 {
        background-color: #c883d4;
        border-radius: 8px;
      }

  - content: |
      ## Type-specific utility classes

      - Different classes to change styles & weights
      - Different classes to change alignments
      - Classes to control line-length

  - type: interactive
    resizable: true
    html_hidden: |
      <link href="css/type.css" rel="stylesheet">
    html: |
      <h1 class="italic not-bold">Heading Level 1</h1>
      <h2 class="text-right">Heading Level 2</h2>
      <p class="max-length">Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</p>

  - content: |
      ## Videos & tutorials

      - [Modular typography ➔](/topics/modular-typography/)
      - [**Typografier »**](https://typografier.web-dev.tools/)
      - [Typografier cheat sheet ➔](/topics/typografier-cheat-sheet/)
---
