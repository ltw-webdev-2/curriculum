---
layout: lesson
title: "Using a type system"
desc: "A quick look at using a generated type system from Typografier in your website to simplify making responsive layouts."

markbot_submit: true
hide_show_for_marks: true

extra_tutorials:
  - title: "Modular type slide deck"
    url: "/courses/web-dev-2/modular-type/"
  - title: "Modular typography"
    url: modular-typography
  - title: "Typografier"
    url: "https://typografier.web-dev.tools/"
    highlight: true
  - title: "Typografier cheat sheet"
    url: typografier-cheat-sheet
    highlight: true

goal:
  image: goal.gif
  before: |
    Typografier is a tool I created for myself that generates a responsive type system. It was inspired by lots of other type systems like [Bootstrap](https://getbootstrap.com/), [Foundation](http://foundation.zurb.com/) and [Type Scale](http://type-scale.com/) but has it’s own features and doesn’t require you to use the whole framework to implement it in your websites.

    Let’s look at how to use Typografier in your website.
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

fork:
  url: "https://github.com/acgd-webdev-2/using-a-type-system/"

steps:
  - title: "Set up the project"
    before: |
      Before we get started, create some files and get ready.
    folders:
      - label: "using-a-type-system"
        type: folder
      - label: "index.html"
        indent: 1
      - label: "css"
        type: folder
        indent: 1
      - label: "type.css"
        indent: 2
      - label: "main.css"
        indent: 2
      - label: "images"
        type: folder
        indent: 1
        fade: true
      - label: "glyptodon.jpg"
        indent: 2
        fade: true
    after: |
      1. Make an `index.html`
      2. Make a `type.css` in your `css` folder
      3. Make a `main.css` in your `css` folder
    notes:
      - label: "Naming conventions"
        text: "Don’t forget to follow the [naming conventions](/topics/naming-paths-cheat-sheet/#naming-conventions)."

  - title: "Add HTML boilerplate"
    before: "*Use the `html5`, `viewport`, and `css` snippets.*"
    code_lang: "html"
    code_file: "index.html"
    code: |
      <!DOCTYPE html>
      <html lang="en-ca">
      <head>
        <meta charset="utf-8">
        <title>Using a type system</title>
        <meta name="viewport" content="width=device-width,initial-scale=1">
        <link href="css/type.css" rel="stylesheet">
        <link href="css/main.css" rel="stylesheet">
      </head>
      <body>

      </body>
      </html>
    lines:
      - num: "7-8"
        text: |
          Don’t forget to attach both CSS files: `type.css` and `main.css`
    notes:
      - label: "HTML snippets"
        text: "Create the boilerplate with `html5`, `viewport` & `css`"
      - label: "Important"
        text: "The order of these files is extremely important: `type.css` should always come before `main.css` in the HTML."

  - title: "Add CSS boilerplate"
    before: "*Use the `cssviewport`, `borderbox` & `textsize` snippets.*"
    code_lang: "css"
    code_file: "css/main.css"
    code: |
      @-moz-viewport { width: device-width; scale: 1; }
      @-ms-viewport { width: device-width; scale: 1; }
      @-o-viewport { width: device-width; scale: 1; }
      @-webkit-viewport { width: device-width; scale: 1; }
      @viewport { width: device-width; scale: 1; }

      html {
        box-sizing: border-box;

        -moz-text-size-adjust: 100%;
        -ms-text-size-adjust: 100%;
        -webkit-text-size-adjust: 100%;
        text-size-adjust: 100%;

        font-family: Georgia, serif;
      }

      *, *::before, *::after {
        box-sizing: inherit;
      }

      .img-flex {
        display: block;
        width: 100%;
      }
    lines:
      - num: "15"
        text: "Let’s set the default font for the website to `Georgia`"
      - num: "22-25"
        text: "Make sure to add the class for scalable images."
    notes:
      - label: "CSS snippets"
        text: "Create the boilerplate with `cssviewport`, `borderbox` & `textsize`"

  - title: "Add content to the HTML"
    before: |
      Let’s add all the content we need to the HTML including the basic tags.

      *You can copy-paste all this content from the `content.txt` file.*
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <article class="card">
          <img class="img-flex" src="images/glyptodon.jpg" alt="">
          <div>
            <h1>Glyptodon</h1>
            <p>Glyptodon was a large, armored mammal, a relative of armadillos, that lived during the Pleistocene epoch. It was roughly the same size and weight as a Volkswagen Beetle, though flatter in shape.</p>
            <p>With its rounded, bony shell and squat limbs, it superficially resembled turtles, and the much earlier dinosaurian ankylosaur, as an example of the convergent evolution of unrelated lineages into similar forms.</p>
            <footer>
              <p><a href="https://en.wikipedia.org/wiki/Glyptodon">Information from Wikipedia</a></p>
            </footer>
          </div>
        </article>

      </body>
      </html>
    lines:
      - num: 2
        fade: true
      - num: "16-17"
        fade: true
      - num: 4
        text: "Notice the `.card` class, we’re going to add some really basic styles to this in the next step."
      - num: 5
        text: "Don’t forget to add the `.img-flex` class to all the images."
      - num: 6
        text: "This `<div>` is here—not for semantics—but because we’ll need a hook later to add some spacing."
      - num: 11
        text: |
          It makes more semantic sense to use a `<small>` tag here because it’s a copyright-like notice. I’m using a `<p>` tag simply because I want to demonstrate a point about margins & font-sizes.

  - title: "Add some basic CSS"
    before: "Now we’ll add a little bit of CSS just so our card is recognizable—but the majority of the code we’re going to write is classes in our HTML."
    code_lang: "css"
    code_file: "css/main.css"
    code: |
      ⋮
      .img-flex {
        display: block;
        width: 100%;
      }

      a {
        color: currentColor;
      }

      .card {
        overflow: hidden;

        background-color: #d9ccaa;
        border-radius: 6px;
      }
    lines:
      - num: "2-5"
        fade: true
      - num: "7-9"
        text: |
          Change the default colour of links to match the text.

          - If you do this it’s extremely important that you DO NOT remove the underline.
      - num: "12"
        text: "The `overflow: hidden` here is used to chop the corners of the image off to make them round."
    after: |
      We should see something like this when we refresh in the browser.

      ![](basic-css.png)

  - title: "Add the Typografier CSS"
    before: |
      We’re going to use Typografier to generate a fully complete type system for us to use in our website.

      ### [Go to Typografier.](https://typografier.web-dev.tools/)

      *Keep all the settings as their defaults.*

      ![](typografier.jpg)

      Copy all code generated by Typografier, in the right-hand panel & paste it into your `type.css` file.

      *That’s it—we have a fully functional type system. Now we can concentrate fully on our layout and write much less CSS.*

      **We should never touch the generated CSS just in case we want to replace it later.**
    after: |
      Refresh to see what Typografier has done to the type. Try resizing your browser and notice how the font-sizes and line-heights adjust.

      ![](type-css.png)

  - title: "Add spacing classes"
    before: |
      Let’s start by making the space around things consistent.

      The spacing classes add padding and margins that match the type size and line-height. This allows us to create a consistent vertical rhythm because all space around and inside elements matches the type sizes.

      **It’s important to remember that Typografier removes all top margins and uses only the bottom margins—this makes it much easier to keep a consistent vertical rhythm.**
    code_lang: html
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <article class="card">
          <img class="img-flex" src="images/glyptodon.png" alt="">
          <div class="island">
            <h1>Glyptodon</h1>
            <p>Glyptodon was a large, armored mammal, a relative of armadillos, that lived during the Pleistocene epoch. It was roughly the same size and weight as a Volkswagen Beetle, though flatter in shape.</p>
            <p>With its rounded, bony shell and squat limbs, it superficially resembled turtles, and the much earlier dinosaurian ankylosaur, as an example of the convergent evolution of unrelated lineages into similar forms.</p>
            <footer>
              <p class="push-0"><a href="https://en.wikipedia.org/wiki/Glyptodon">Information from Wikipedia</a></p>
            </footer>
          </div>
        </article>

      </body>
      </html>
    lines:
      - num: "2-5"
        fade: true
      - num: "7-10"
        fade: true
      - num: "12-17"
        fade: true
      - num: 6
        text: |
          The `.island` class adds padding, equal to the `line-height` around all four sides.

          We’re using `.island` here to add space around the text but still allow the image to be full bleed.
      - num: 11
        text: |
          The `.push-0` class will remove the default `margin` from the bottom of an element.

          We’re using it here because if we didn’t remove the bottom margin, there would be extra space at the bottom caused by the margin of the `<p>` adding onto the padding of `.island`
    after: |
      So, our layout should look like this now:

      ![](spacing.png)

  - title: "Add font sizes"
    before: |
      Now, let’s add a few classes to adjust the font size on some elements, to make them bigger and smaller.

      Typografier’s font-size classes are based on the metric system, or computer sizes if that’s more familiar. `.micro` is the smallest, going up to `.kilo`, `.giga`, and all the way to `.yotta`

      *There are only 10 font-sizes to choose from—if you need more than that you’re probably doing something wrong.*
    code_lang: html
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <article class="card">
          <img class="img-flex" src="images/glyptodon.jpg" alt="">
          <div class="island">
            <h1 class="zetta">Glyptodon</h1>
            <p class="mega">Glyptodon was a large, armored mammal, a relative of armadillos, that lived during the Pleistocene epoch. It was roughly the same size and weight as a Volkswagen Beetle, though flatter in shape.</p>
            <p>With its rounded, bony shell and squat limbs, it superficially resembled turtles, and the much earlier dinosaurian ankylosaur, as an example of the convergent evolution of unrelated lineages into similar forms.</p>
            <footer class="micro">
              <p class="push-0"><a href="https://en.wikipedia.org/wiki/Glyptodon">Information from Wikipedia</a></p>
            </footer>
          </div>
        </article>

      </body>
      </html>
    lines:
      - num: "2-6"
        fade: true
      - num: "9"
        fade: true
      - num: "11-17"
        fade: true
      - num: 7
        text: "The `.zetta` class is the second largest font-size. We’re using it here to make our `<h1>` a little bigger than normal."
      - num: 8
        text: "The `.mega` class is one font-size larger than the default body copy."
      - num: 10
        text: "The `.micro` font-size is the smallest size possible—we’re using it on `<footer>` because the information isn’t too important."
    after: |
      Refresh to see the layout now. Make sure to resize your browser to see how the font sizes change.

      ![](font-sizes.png)

  - title: "Add stylistic classes"
    before: |
      Typografier has a few stylistic classes to control font styles and text positions.

      *Be warned though, many of these stylistic classes aren’t responsive: if you make something `bold` it’s always bold.*
    code_lang: html
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <article class="card">
          <img class="img-flex" src="images/glyptodon.jpg" alt="">
          <div class="island">
            <h1 class="zetta">Glyptodon</h1>
            <p class="mega italic">Glyptodon was a large, armored mammal, a relative of armadillos, that lived during the Pleistocene epoch. It was roughly the same size and weight as a Volkswagen Beetle, though flatter in shape.</p>
            <p>With its rounded, bony shell and squat limbs, it superficially resembled turtles, and the much earlier dinosaurian ankylosaur, as an example of the convergent evolution of unrelated lineages into similar forms.</p>
            <footer class="micro text-center">
              <p class="push-0"><a href="https://en.wikipedia.org/wiki/Glyptodon">Information from Wikipedia</a></p>
            </footer>
          </div>
        </article>

      </body>
      </html>
    lines:
      - num: "2-7"
        fade: true
      - num: "9"
        fade: true
      - num: "11-17"
        fade: true
      - num: 8
        text: "We’re permanently setting this text to be `.italic` in order to make it stand out on all screen sizes."
      - num: 10
        text: "The `.text-center` class will make the text always be centered, there’s nothing responsive about this, it’ll be centered on every single screen size."
    after: |
      Refresh and see what we’ve got.

      ![](stylistic.png)

  - title: "Control the line-length"
    before: |
      Finally, we’re going to add one last class that will help control the line-length of the card: `.max-length`
    code_lang: html
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <article class="card max-length">
          <img class="img-flex" src="images/glyptodon.jpg" alt="">
          <div class="island">
            <h1 class="zetta">Glyptodon</h1>
            <p class="mega italic">Glyptodon was a large, armored mammal, a relative of armadillos, that lived during the Pleistocene epoch. It was roughly the same size and weight as a Volkswagen Beetle, though flatter in shape.</p>
            <p>With its rounded, bony shell and squat limbs, it superficially resembled turtles, and the much earlier dinosaurian ankylosaur, as an example of the convergent evolution of unrelated lineages into similar forms.</p>
            <footer class="micro text-center">
              <p class="push-0"><a href="https://en.wikipedia.org/wiki/Glyptodon">Information from Wikipedia</a></p>
            </footer>
          </div>
        </article>

      </body>
      </html>
    lines:
      - num: 2
        fade: true
      - num: "5-17"
        fade: true
      - num: 4
        text: "We can use `.max-length` class to force an element or text to never exceed a recommended maximum line-length."
    after: |
      That’s it we’re done.

      With Typografier we were able to make a nice layout, with spacing consistency and good vertical rhythm without touching CSS (except to add some colours).

---
