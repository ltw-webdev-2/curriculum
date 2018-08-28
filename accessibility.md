---
layout: slide-deck
title: "Accessibility"
desc: "A quick overview of major accessibility concerns, how they affect our websites, and how we can make access to our websites better."

slides:
  - type: super-big-text
    content: |
      **Accessibility**

  - content: |
      ## Make the web work for everyone

      The Web is accessible by default—if your website isn’t accessible it’s your fault.

  - content: |
      ## Visual impairments

      *Blindness, partial or full; colour blindness; cataracts; glaucoma; age; etc.*

      - Allow text to be resized
      - Have good contrast in colours
      - Test for colour blindness related issues
      - Make sure the website works well with screen readers
      - Use proper alt attributes

  - content: |
      ## Mobility and dexterity impairments

      *Missing a hand, limited movement, difficulty with fine control, trouble holding a mouse, termors or shakes, etc.*

      - Recognize and prepare for the fact that not everybody will use a mouse
      - Make the website keyboard accessible
      - Increase hit areas of links and buttons

  - content: |
      ## Auditory impairments

      *Deafness, partial deafness, etc.*

      - Provide text captions and subtitles

  - content: |
      ## Cognitive impairments

      *Dyslexia, memory issues, problem solving issues, attention deficits, hyperactivity, reading abilities, etc.*

      - Make it clear where in the website the user is
      - Organize your content correctly & use proper headings
      - Make the text easily scannable
      - Clearly mark links
      - Use lots of images and graphics

  - content: |
      ## WAI-ARIA

      *Describes enhancements to websites to make them more accessible*

      Extra attributes to help accessibility tools understand your content better

  - type: code
    html: |
      <!-- Define important landmarks -->
      <header role="banner">
      <!-- banner, navigation, search, main, contentinfo -->

      <!-- Define more accessible information -->
      <a href="…" aria-label="More complex information">

      <!-- Define an HTML element that contains the alternative description -->
      <img src="…" alt="…" aria-details="thing">

  - type: youtube-embed
    video: c0nvdiRdehw

  - type: youtube-embed
    video: cSSgndQ5mVs?start=55&end=164

  - content: |
      ## Tools

      - [Web Developer Toolbar](http://chrispederick.com/work/web-developer/)
      - [Sim Daltonism](https://michelf.ca/projects/sim-daltonism/)
      - [**VoiceOver**](https://www.apple.com/accessibility/osx/voiceover/)

  - content: |
      ## Videos & tutorials

      - [Accessibility ➔](/topics/accessibility/)
      - [Accessibility cheat sheet ➔](/topics/accessibility-cheat-sheet/)
      - [Accessibility checklist ➔](/topics/accessibility-checklist/)

---
