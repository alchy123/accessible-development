 # Accessible Development Notes

## ATs - Assistive Technologies

* Screen readers
* Speech recognition software
* Screen magnifiers
* Alternative input devices, designed for people with motor skill impairments.

## The Accessibility Tree
* Accessibility tree is a part of website's DOM. All accessible objects are created in the accessibility tree for each DOM element that needs to be exposed to assistive technologies.
* Use semantic HTML in proper way, this helps.

## Accessibility Testing
* Using AT
    * Screen reader
* Contrast Checkers
* Automated Tools
    * Lighthouse in Chrome
    * Accessibility Inspector in Firefox
    * aXe
* AI assistants
    * You can interact and get help from AI assistants to improve accessibility

## WCAG - Web Content Accessibility Guidelines

* These are the set of recommandations developed by the World Wide Web Consortium (W3C) to make web content more accessible, especially for people with disabilities.
* Our goal is to reach the AAA level every time we can, it is the best level of accessibility for the WCAG.

* AA requirements
    * 4.5:1 contrast for normal text
    * 3:1 for large text (>=24px)
* AAA requirements (our goal)
    * 7:1 contrast for normal text
    * 4.5:1 for large text (>=24px)

## Notes

* Use texts and shapes with the colors. Make it more understandable and accessible with combining them.
* background-blend-mode with background-color. This two property is useful when the background image is preventing our contents accessibility.
* Add *clear and concise* **alt(alternative) text** for your image contents. Do not specify to your alternative text a part like "An image of.." because screen readers is already doing that, you shouldn't do that, just explain the image. Try to end your alt text with a dot.
    * If an image is purely decorative(for example an abstract image for the website background that is not important for the visually impaired person, icons combined with text is also an example), we don't need to write any descriptive text as the value for that attribute. **We should add an empty alt attribute in this situation** because without it, a screen reader may read out the image file name instead and that can be disturbing. Adding the decorative images with CSS might be smart because you don't have to deal with alt text because screen readers ignore those CSS images, because that image isn't part of the HTML DOM as an actual content then.
    * If the image has a label or adherent text that describes the image, an alternative text also becomes redundant. Do not misunderstood, text should be on HTML content, not on the image as image in this situation!
    * Who this help:
        * People with little or no vision
        * People who have turned off images
        * Search engines like Google
* About links:
    * Links should be recognizable as links.
    * If you're making a card a link then you shouldn't just wrap with the a tag, that would force the visually impaired person to read all of the text inside of the card before saying it's a link. Also with this bad implementation, images in the card may not be readable too. Instead, the link should be positioned inside the card without wrapping any text. With a little CSS trick, you can make card clickable and more understandable that it's a link. Also, use *aria-label* in this situation too, it would be good. Suggestion, make the text of the link bold and your link text should be explanatory independently. Don't do "click me" but do something like "Check out more of their awesome art by clicking this card.".
    * They should have non-ambiguous text. Examples of bad practice are "click here", "more", "continue", etc.
    * Know how to use the properties like aria-label and other things about accessibility
    * Put a dot in the end of your explanations. This would help them to take a breath and serve a better experience.
* About Labels:
    * According to the WCAG, the accessibility guidelines, placeholder text is not an accessible replacement for the label element. The placeholder should only be used as a brief example of the text to be entered, mainly because of inconsistent support for screen readers. Try to use both a label and a placeholder that gives an explanatory example about input field.
        * Note, if your design is really focused with not using labels somehow, try to change that design if you can, if you can't, try to add labels in an invisible way that screen readers can use. But if you can, add the labels, because we are trying to be accessible to everyone. Adding a visible label would also help the people that don't visually impared, remember!
    * Associate the labels with input fields. So the important note here is, you should know how to use semantic HTML in the right way and always make your designs in an accessible way.
* Note: Text inside links and buttons actually act as labels and providing an accessible name in the browser's accessibility layer. If, for whatever reason, we want to create a custom button without using the button element, we would need to add a so called *aria-label* attribute that substitutes the regular button label.
    * **Important Note**: People may think why do we need the use default semantic html elements when we can create our own special ones. Here's the thing, using the semantic elements help us keep ourselves on the way of standards. We have many different kind of standards to keep web more meaningful and accessible. With semantic HTML, we are making our design follow the standards more properly. For example, a semantic button element has built-in accessibility features, but when we create a button without the semantic button element, we need to use aria-label to give that accessibility features. W3C, WHATWG, ECMA International, Wasm, these are some popular organizations and standards that help us create an accessible web. Accessibility isn't just for disabled persons. Every piece of the web is interacting with each other on many aspects, if we don't have a known structure, a standard, then how can we sustain and keep up this web alive. Accessibility is meant for every person and software.
* Radio buttons:
    * We should know that the radio buttons could have even more semantically correct HTML than they currently have. We should use the fieldset tag to group the set and legend tag to provide a context for screen reader users.
* Use semantic HTML tags, for example 'main', 'nav', 'section', 'footer', 'button' and so on. When we use semantic HTML tags, our changes manifest in easier navigation using assistive technologies like screen readers because they can quickly identify these landmarks and provide shortcuts or navigation commands to jump directly these sections. For example, a user can skip directly to the main content or quickly access the navigation menu. This reduces time and effort required to navigate through unneccessary content, enhancing the efficiency of the user experience. This also provide a better communication/accessibility among the software technologies like search engines and many other softwares that somehow interact with our web page.
    * Additional note about why this helps to the Search Engine Optimization: Search engines index our websites with their technologies and want to put that website to the place where it belongs to when someone search something. So while indexing our website, search engine also takes informations from our website and tries to understand what is it all about. It is doing that with the help of semantic HTML, how can it understand your website if didn't use semantic HTML. Then how can search engines understand which tag contains which information?
    * Use unordered lists for your consecutive items like nav items on top your page or any other consecutive ones. 
* Use the assistive technologies, look up to how search engines work and how other softwares communicate and consume our website to understand. This way, you can have a grounded experience to how to program your website!
* About text size
    * Use rem instead of px. Users can change the browsers default font size, your website's font-size change with that browser change when you use rem, but pixels are fixed values.
    * Because I said try to be AAA on WCAG level. I'm not mentioning evey detail of WCAG for every 'About..' note here. Here, I just add additional useful notes.
* About headings
    * Use them correctly and properly! One web page must have one h1 and other tags come in logical order. Headings work like the way of book contents work. 
* ARIA - Accessible Rich Internet Applications
    * ARIA is a set of attributes that you can add to HTML elements to provide more context and information to assistive technologies. It helps fill in the gaps where HTML's native semantics fall short.
    * We want to use ARIA when we're creating a UI component that doesn't exist in HTML. We need to provide additional information or context to assistive technologies, which can't be achieved with HTML alone. *However*, avoid using ARIA if the same functionality can be achieved with native HTML elements.
    * 'role' attribute defines the role of an element to assistive technologies.
    * 'tabindex' attribute allows to control keyboard accessibility.
    * 'aria-checked' attribute indicates the current state of checkboxes and similar widgets, with possible values of 'true', 'false' or 'mixed'. It helps assistive technologies convey the state of these elements to users.
    * When it aria-live is set to "off" that is the assumed default for elements. So it should not be neccessary set this explicitly.
    aria-live="polite" is the most common one to use. Any region which receieves updates that are important for the user, to reach  