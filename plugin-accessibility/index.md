## Plugin Accessibility

There are no plugin accessibility requirements in the WordPress plugin directory. This is because of the labor required to test plugins for accessibility. However, you are strongly encouraged to consider accessibility when creating or updating your plugins.

## Why is plugin accessibility important?

Accessibility is the key to making your plug-in usable by people with disabilities. The accessibility of your user interface has an impact on what countries and organizations can legally use your plugin. Accessibility is required by many governments for any commercial site, and by even more for sites within governmentally supported institutions such as schools. The laws governing accessibility are variable, but most laws reference a set of guidelines called the Web Content Accessibility Guidelines (WCAG), authored by the World Wide Web Consortium (W3C).

The most common guidelines in current use are [WCAG version 2.1 at level AA](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_customize&levels=aaa). While many of these guidelines are specific to content, there are many aspects of accessibility that your plugin can and should employ.

## Resources:

- Inclusive Design Components by Heydon Pickering
- United Kingdom’s Design System library
- United States’ Design System library
- Accessible Components by Scott O’Hara

## Interactive Elements

Forms, buttons, toggles, tabs – these are all elements commonly used both in the admin of your plugin and in public-facing interfaces. They’re also some of the most critical pieces for achieving a basic level of accessibility.

At minimum, you should be considering:

### Fields should be labeled

Every form input needs to have an associated `<label>` element. Those labels should be an accurate representation of the information required for that form. The label should be associated with the field using a for/id relationship:

```html
<label for="my_field">Share your story</label>
<textarea id="my_field" name="my_story"></textarea>
```

Avoid hiding your labels visually. If you do need to hide a label, use a standard `.screen-reader-text` class to do so.

[Learn more about visually hidden text](https://make.wordpress.org/accessibility/handbook/markup/the-css-class-screen-reader-text/).

### Form groups need group names

If you’re providing a group of checkboxes or radio buttons, the label for the input isn’t usually enough information: it tells you the value you’re selecting, but not the question you’re trying to answer. Checkboxes and radio buttons should be grouped inside a `<fieldset>` with a `<legend>`.
 
```html
<fieldset>
    <legend>Why do you love WordPress plugins?</legend>
      <input type="radio" id="radio1" value="money"> <label for="radio1">Money</label>
      <input type="radio" id="radio2" value="fame"> <label for="radio2">Fame</label>
      <input type="radio" id="radio3" value="respect"> <label for="radio3">Respect</label>
</fieldset>
```

### Buttons should be `<button>` or `<input>` elements

Attaching JavaScript to `<div>` or `<span>` elements can work great for mouse users, but leaves a ton of gaps for anybody using a screen reader or keyboard to use your site. Using standard form elements helps ensure that forms and toggles work for everybody.

You can use an anchor element for button-like behavior, but this creates accessibility problems, such as preventing the user from cancelling the action.

### Announce dynamic changes audibly

When an AJAX action runs, announce it audibly or move focus to an appropriate new location on the page.

WordPress contains a useful method called `wp.a11y.speak()` that you can use to announce results audibly. This gives screen reader users important feedback that something is happening, and what they can do next. If you’d show a result visually, you should also announce it audibly. 

Learn more about [wp.a11y.speak()](https://make.wordpress.org/accessibility/2015/04/15/let-wordpress-speak-new-in-wordpress-4-2/).

Moving focus to a new location on the page will also generate new information for screen readers. This is appropriate when the action taken changes the user’s view, and they need to be informed of the change.

### Make it easy to identify and correct errors

When users input data into a form, provide them with feedback when a submission is made and notify them when they have entered something incorrectly. The error message should clearly describe the error and provide them with suggestions for correcting the error. Errors must be indicated by more than just a change of color.

You can use icons and error lists to present this visually but make sure you audibly announce it.

### Use Color Appropriately

Good color contrast is important to make sure that users with a variety of visual impairments can use your interface. The most common problem cited is color blindness, but presbyopia (age-related vision impairments) are even more common, and most specifically impacted by low contrast. As eyes age, their ability to perceive low contrast differences decreases.

The WCAG 2.1 guidelines measure contrast using a ratio comparing the relative luminosity of the colors. The guidelines stipulate a minimum contrast of 4.5:1 for normal text and 3.0:1 for large text using this ratio.

You can test your colors using many tools:

- [Joe Dolson’s Color Contrast Tool](https://www.joedolson.com/tools/color-contrast.php)
- [WebAIM’s ContrastChecker](https://webaim.org/resources/contrastchecker/color)
- [Lea Verou’s Contrast Ratio](https://contrast-ratio.com/)

Good color contrast doesn’t mean extremely high contrast; the guidelines set a minimum baseline, and any contrast that meets that baseline is acceptable.

### Accessible Images

You may think that you’re not including any images in your project. Possibly this is true; but are you using [dashicons](https://developer.wordpress.org/resource/dashicons/) or other icon fonts? Are you using SVG graphics?

For accessibility, “images” doesn’t only refer to the `img` element. It means any non-text graphical elements on the page.

This is particularly crucial if you’re using images to represent controls – a hamburger menu icon, an arrow, or a plus or minus icon. These images are used to represent information.

All of these images require accessibility considerations. The W3C offers a [useful decision tree to help you decide](https://www.w3.org/WAI/tutorials/images/decision-tree/) what kind of text you need for an image. If your image is conveying information or activating a control, it’s going to need some form of accessible name.

Making an image accessible doesn’t necessarily mean ensuring that it is named, however. If an image is the sole presentation of data, then it needs to be named. If it is supplemental, and that same information is presented in text, then it should be hidden from screen readers.

- [Accessible SVGS from CSS Tricks](https://css-tricks.com/accessible-svgs/)
- [Font Icon accessibility from Font Awesome](https://fontawesome.com/docs/web/dig-deeper/accessibility)

## Animations

Animations can cause a variety of symptoms in many users, ranging from mild dizziness to triggering migraines and nausea. You can help users avoid these problems by making all of your animations support the `prefers-reduced-motion` flag.

`prefers-reduced-motion` is a system preference that allows the user to indicate that they would prefer not to see animations. But this only works if the code properly supports it!

You can check for this system preference using the CSS media feature:

```css
@media (prefers-reduced-motion) {
    .animation {
    // adjust your animations if reduced motion is requested.
    }
}
```

Reduced motion doesn’t have to mean no animation at all, but it should be very minimal – no more than is absolutely necessary. When in doubt, eliminate the animation entirely.

You can check for the media query in JavaScript by checking the value of the media query:

`const mediaQuery = window.matchMedia(“(prefers-reduced-motion: reduce)”);`

- [Respecting “Prefers Reduced Motion” with JavaScript and React](https://since1979.dev/respecting-prefers-reduced-motion-with-javascript-and-react/), by Stephan Nijman
- [Prefers-reduced-motion ](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion)from MDN Web Docs


