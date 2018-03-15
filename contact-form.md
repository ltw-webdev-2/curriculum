---
layout: lesson
title: "Contact form"
desc: "Create a functional website contact form using Formspree as the message sender."

markbot_submit: true
hide_show_for_marks: true

extra_tutorials:
  - title: "Forms slide deck"
    url: "/courses/web-dev-2/forms/"
  - title: "Forms"
    url: forms
  - title: "Forms cheat sheet"
    url: forms-cheat-sheet
    highlight: true

goal:
  image: goal.png
  before: |
    We’re going to look at how to make a functional contact form. With only HTML, and no backend server, it would be impossible to actually send messages—but there are some services that’ll help us out. We’ll use [Formspree](https://formspree.io/) to help make our contact form messages send.
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

fork:
  url: "https://github.com/acgd-webdev-2/contact-form"

steps:
  - title: "Project setup"
    before: |
      The form isn’t going to work at all without running on a web server—the quickest way to get the form onto a web server is to use GitHub.
    folders:
      - label: "contact-form"
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
      This repo has the HTML boilerplate and all the CSS files hooked up. The `main.css` file has everything we’ll need for today.

  - title: "Write the basic HTML"
    before: |
      Before we hook the contact form into Formspree let’s write all the HTML inputs necessary to make the form.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </head>
      <body>

        <section>
          <div>
            <h1>Send us a sweet little note</h1>

            <form>
              <div>
                <label for="name">Name</label>
                <input id="name" required>
              </div>
              <div>
                <label for="email">Your email</label>
                <input id="email" type="email" placeholder="me@me.com" required>
              </div>
              <div>
                <label for="subject">Subject</label>
                <select id="subject">
                  <option>Get a quote!</option>
                  <option>General question</option>
                  <option>Just to talk</option>
                </select>
              </div>
              <div>
                <label for="details">What’s up?</label>
                <textarea id="details" required></textarea>
              </div>
              <div>
                <button type="submit">Send message</button>
              </div>
            </form>
          </div>
        </section>

      </body>
      </html>
    lines:
      - num: "2-3"
        fade: true
      - num: "37-38"
        fade: true
      - num: 9
        text: |
          Every element related to the `<form>` must be wrapped by this tag.
      - num: 10
        text: |
          I usually wrap a `<div>` around every `<input>` because it gives more layout control—especially when using the grid system.
      - num: "11-12"
        text: |
          It’s extremely critical that the `for=""` attribute on the `<label>` matches the `id=""` attribute on the associated `<input>`
      - num: 16
        text: |
          The `placeholder=""` attribute allows us to put an example into the `<input>` field.

          **It should never be used to replace a `<label>`!**

          Also notice the `type="email"` attribute—this helps the browser validate the allowed information in the field.
      - num: "20-24"
        text: |
          We could use a regular `<input>` for the subject but I thought it’d be fun to have a few items to choose from.

          The `<select>` input will present the user with a menu of options to choose from.
      - num: 28
        text: |
          The `<textarea>` element is a multiline text field, people can press `Return` in the field to make new lines without submitting the form.
      - num: 31
        text: |
          A `<button>` tag is used to submit the form’s information. It cannot link to another page.

          Without the `type="submit"` attribute the button won’t actually submit the form—it’ll require JavaScript to be functional.
    notes:
      - label: 'Important'
        text: |
          Notice that a few of the form fields have the `required` attribute—it’s best practice that at least one field in a form is required.
    after: |
      After writing out that HTML, this is what we should see:

      ![](basic-html.png)

      That’s pretty darn ugly…

  - title: "Add the Web Dev Tools"
    before: |
      The default look of forms is pretty abysmal—Modulifier has some slightly nicer form defaults, so let’s add that code into your website.
    folders:
      - label: "contact-form"
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

      - Go to [Modulifier](http://modulifier.web-dev.tools/) and copy the CSS into `modules.css`—**make sure to press “Select all”**
      - Go to [Typografier](http://typografier.web-dev.tools/) and copy the default CSS into `type.css`

      *We’re not using a grid for this lesson so it doesn’t need to be included.*

      With the Web Dev Tools in place, it looks better:

      ![](web-dev-tools.png)

  - title: "Add some basic styling"
    before: |
      Now let’s add a few classes to the form elements to make it look nicer.

      The `main.css` file already has a class, `.contact`, to set the background colour for the `<section>`
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </head>
      <body>

        <section class="contact pad-t-2 pad-b-2">
          <div class="max-length">
            <h1>Send us a sweet little note</h1>

            <form class="push-0">
              <div class="push">
                <label for="name">Name</label>
                <input id="name" required>
              </div>
              <div class="push">
                <label for="email">Your email</label>
                <input id="email" type="email" placeholder="me@me.com" required>
              </div>
              <div class="push">
                <label for="subject">Subject</label>
                <select id="subject">
                  <option>Get a quote!</option>
                  <option>General question</option>
                  <option>Just to talk</option>
                </select>
              </div>
              <div class="push">
                <label for="details">What’s up?</label>
                <textarea id="details" required></textarea>
              </div>
              <div>
                <button class="btn btn-light mega" type="submit">Send message</button>
              </div>
            </form>
          </div>
        </section>

      </body>
      </html>
    lines:
      - num: "2-3"
        fade: true
      - num: "37-38"
        fade: true
      - num: 5
        text: |
          Add a few classes to make the `<section>` nicer: `.contact` (in `main.css` already) & `.pad-t-2` and `.pad-b-2` from `type.css`
      - num: 6
        text: |
          Add the `.max-length` class so the form’s width doesn’t go crazy on us.
      - num: 9
        text: |
          The `<form>` tag has some default margins that we’re going to remove.
      - num: 10
        text: |
          If we add `.push` to all the `<div>` tags (except the last) we can space all the inputs out nicely.
      - num: 14
      - num: 18
      - num: 26
      - num: 31
        text: |
          Add the `.btn` and `.btn-light` classes to the button to make it look better than the default styles.

          And make it a little larger with `.mega`
    after: |
      And now the form should look good—like this:

      ![](goal.png)

  - title: "Hook the form to Formspree"
    before: |
      Now that our form looks good we’re going to hook it into [Formspree](https://formspree.io/) so that our messages actually send.

      With HTML only, our forms don’t do anything. We can do some processing with JavaScript but without a backend server we can’t send emails. So Formspree is going to be our backend server.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </head>
      <body>

        <section class="contact pad-t-2 pad-b-2">
          <div class="max-length">
            <h1>Send us a sweet little note</h1>

            <form class="push-0" method="POST" action="https://formspree.io/bradlet@algonquincollege.com">
              <div class="push">
                <label for="name">Name</label>
                <input id="name" name="name" required>
              </div>
              <div class="push">
                <label for="email">Your email</label>
                <input id="email" type="email" placeholder="me@me.com" name="email" required>
              </div>
              <div class="push">
                <label for="subject">Subject</label>
                <select id="subject" name="_subject">
                  <option>Get a quote!</option>
                  <option>General question</option>
                  <option>Just to talk</option>
                </select>
              </div>
              <div class="push">
                <label for="details">What’s up?</label>
                <textarea id="details" name="message" required></textarea>
              </div>
              <div>
                <button class="btn btn-light mega" type="submit">Send message</button>
              </div>
            </form>
          </div>
        </section>

      </body>
      </html>
    lines:
      - num: "2-3"
        fade: true
      - num: "37-38"
        fade: true
      - num: 9
        text: |
          The `<form>` tag gets two new attributes—as shown in the [Formspree documentation](https://formspree.io/).

          - `method` — `POST`, tells the browser how to send the information to the server.
          - `action` — The URL to the server the information should be sent—**make sure to change it to your email address!**
      - num: 12
        text: |
          Every field in the form now gets a `name=""` attribute. It doesn’t really matter what the `name` is but a few of them are specialized:

          - `name="email"` — Formspree will use this as the email’s “Reply To” entry.
          - `name="_subject"` — Formspree will use this as the subject of the email message

          You can also provide the URL for a “Thank You” page—check out the [Formspree documentation](https://formspree.io/) to see how to do that.
      - num: 16
      - num: 20
      - num: 28
    after: |
      **Don’t forget to change the email address to your email address!**

  - title: "Commit, sync, test"
    before: |
      Commit & sync the code to GitHub so we can test that it works.

      **If you try to submit on your local computer Formspree will give you an error message.**

      After the website is live, on GitHub, go to the `github.io` URL and submit your form!

  - title: "Confirmation in your email"
    before: |
      The first message you get from Formspree will be a confirmation one. **You have to go to your email and confirm your email address!** After that Formspree will just send the message to your email address.

---
