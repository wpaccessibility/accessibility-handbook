# Front end checks for web accessibility

Testing for valid, semantic HTML is essential for the accessibility of your work. In this page we list some essential requirements and best resources. It gives you the minimum tests you need to do during development and before you commit your work.

While you develop, always check the following items while developing: keyboard navigation, W3C validation, WCAG 2 AA validation and then announcement of dynamic changes for screen readers.

**Note**: automated testing is not perfect. Automated testing rarely catchies more than about 30% of types of issues. They also give false positives. Manual testing is required to find most issues.

## What is web accessibility?

_Using semantic, meaningful, valid HTML5_.

The way all devices, browsers and users can understand and interact with the functionality on a web page. The best resource for HTML5 are the [Mozilla Developer Network web docs](https://developer.mozilla.org/en-US/).

For WordPress, we aim to meet [WCAG accessibility guidelines](https://www.w3.org/WAI/) at level AA and the [W3C standards](https://www.w3.org/standards/webdesign/htmlcss). In the WordPress Accessibility handbook section [Best Practices](https://make.wordpress.org/accessibility/handbook/best-practices/) you’ll find examples and resources.

You need to do two different checks, one for **keyboard navigation** and one for **DOM validation**.

### Key topics to check

- [Write semantic, meaningful HTML](https://make.wordpress.org/accessibility/handbook/best-practices/markup/semantic-html/)
  - Use a `<button>` to invoke an action and an `<a>` for a change of location.
  - A `<div>` or `<span>` doesn’t natively provide interactivity, and should not be used for links or buttons.
- [Heading text and level matter](https://make.wordpress.org/accessibility/handbook/best-practices/markup/heading-structure-in-theme-development/)
- [Make link and button text meaningful](https://make.wordpress.org/accessibility/handbook/best-practices/content/good-link-texts/)
- Use the [.screen-reader-text](https://make.wordpress.org/accessibility/handbook/best-practices/markup/the-css-class-screen-reader-text/) class, a CSS class to hide text visually while leaving it available to screen readers.
- Always give images a proper alt attribute following the [alt decision tree](https://www.w3.org/WAI/tutorials/images/decision-tree/)
- Forms:
  - always explicitly link [labels to an input control](https://webaim.org/techniques/forms/controls). If the label must be invisible for the design, hide it with the screen-reader-text class
  - Wrap check box groups and radio buttons in a `<fieldset>` and add a `<legend>` describing the group of controls
- Always define both a `:hover` and `:focus` states in your CSS
- Announce dynamic changes with [aria-live](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Live_Regions) or [wp.a11y.speak()](https://make.wordpress.org/accessibility/handbook/best-practices/markup/wp-a11y-speak/)

## Keyboard Navigation

All functionality should work using a **keyboard only**. This essential for all assistive technology to work properly. Most keyboard testing should be checked manually. The best time to test this is during development.

### How to keyboard test:

- [Keyboard Accessibility](https://webaim.org/techniques/keyboard/) by WebAIM
- [Workshop keyboard accessibility](http://rianrietveld.com/2016/05/10/keyboard/)

Tab through your pages, links and forms to do the following tests:

- Confirm all links can be reached and activated via keyboard, including any inside drop downs
- Confirm all links have a strong visible focus indicator
- Confirm all focusable [visually hidden content](https://make.wordpress.org/accessibility/handbook/best-practices/markup/the-css-class-screen-reader-text/) (such as [skip links](https://make.wordpress.org/accessibility/handbook/best-practices/markup/skip-links/)) become visible when in focus.
- Confirm all interactions – form fields, buttons, and other controls – can be triggered via keyboard. Any action you can complete with a mouse must also be possible from the keyboard.
- Perform keyboard tests both with a screen reader and without. Screen reader use of the keyboard can override custom keyboard scripting.

## WCAG 2 AA automated validation

The generated DOM, the front end of your web project, must conform to WCAG 2 AA. You can use automated validation to get a limited scope of your success at this.

Recommended:

- [aXe browser addon](https://www.deque.com/aXe/) for Chrome and FireFox. The addon adds a tab to your inspector with a validate button. After validating you see the errors and warnings for that particular webpage and how to fix them. Make sure to also test in different views and with the menu open and closed, for example.
- [HTML_CodeSniffer](http://squizlabs.github.io/HTML_CodeSniffer/)
- Accessibility Inspector in the [Firefox Developer Tools](https://developer.mozilla.org/en-US/docs/Tools). A good read about this by Marco Zehe:  How to use [NVDA and Firefox to test your web pages for accessibility](https://www.marcozehe.de/articles/how-to-use-nvda-and-firefox-to-test-your-web-pages-for-accessibility/)

More tools:

- [React-a11y](https://github.com/reactjs/react-a11y), Identifies accessibility issues in your React.js elements
- Static AST checker for [a11y rules on JSX elements](https://github.com/evcohen/eslint-plugin-jsx-a11y)
- More [Toolbars and toolkits ](https://make.wordpress.org/accessibility/handbook/which-tools-can-i-use/useful-tools/#toolbars-toolkits) in the Accessibility Handbook

## Automated testing

The big difference between PHP and JavaScript code standard checks and accessibility checks is that the accessibility checks need to be performed on the generated DOM, not on the code base. You need to run checks on a working WordPress site. This can be done using automation that sets up your environment dynamically, but still requires a fully built and run installation.

There are several command line tools for automated testing like [aXe-cli](https://github.com/dequelabs/axe-cli) and [pa11y](https://github.com/pa11y/pa11y).

**Note**: automated accessibility testing doesn’t catch all the issues, rarely more than 30%. Testing in the browser and manual keyboard testing still needs to be part of your workflow.

### Setup for aXe-cli

Install axe-core for CLI first:

```
npm install axe-cli -g
npm install chromedriver –g`
```

Then run axe in the command line: 

```
axe url -b c
```

The url can be any url, also a local one. You get a report of the accessibility issues for that url. The **-b** stands for browser, **c** for chrome, as this browser gives the best results (better than the default PhantomJS). You will get the errors and warnings in your console.

You can provide more (space separated) urls to the command like

```
axe url url2 url3 -b c
```

or call a file with urls like:

```
axe $( cat list-of-urls.txt ) -b c
```

**Note**:  You can run [axe-cli on more than one url](https://make.wordpress.org/accessibility/handbook/best-practices/test-for-web-accessibility/test-for-web-accessibility-frontend-code/#setup-for-axe-cli) in one command, but axe-cli is not build to run on a large amount of urls or on a complete site, axe-cli is not a crawler. Deque Labs recommends to use the [axe-webdriverjs](https://www.npmjs.com/package/axe-webdriverjs), a chainable aXe API for Selenium’s WebDriverJS for testing on a large amounts of urls.

### Setup for pa11y

The [setup for pa11y](https://github.com/pa11y/pa11y) is well documented in the GitHub repository.

## Dynamic content

Content that changes dynamically during time, like JavaScript generated error messages or content, must also be announced for screen readers. The best way is to test this with a screen reader like Apple VoiceOver (for Mac) or NVDA (for Windows). Listen to your website!

While we know that many developers work primarily on MacOS, testing only with Apple’s VoiceOver is not sufficient. VoiceOver, while fairly common, has many non-standard interpretations of accessibility interactions that aren’t the most accurate representation of average user experience.

### Screen reader testing

- [Testing with Screen Readers: Questions and Answers](https://webaim.org/articles/screenreader_testing/)
- [Screen reader keyboard shortcuts and gestures](https://dequeuniversity.com/screenreaders/)
- [Basic screen reader commands for accessibility testing](https://developer.paciellogroup.com/blog/2015/01/basic-screen-reader-commands-for-accessibility-testing/)

### Best screen reader / browser combinations

- VoiceOver with Safari,
- NVDA with Chrome or FireFox
- JAWS with Chrome, Edge or FireFox
- Windows Narrator with Edge

The screen readers ChromeVox and Orca don’t perform well enough as a screen reader, at this moment, to give representative test information.

### How to use a screen reader

- [List of screen reader test tools](https://make.wordpress.org/accessibility/handbook/which-tools-can-i-use/useful-tools/#screen-reader-testing) in the Accessibility Handbook
- [VoiceOver Getting Started](https://help.apple.com/voiceover/info/guide/10.8/English.lproj/index.html)
- [VoiceOver cheat sheet](http://pauljadam.com/demos/iosvocheatsheet.html) by Paul J. Adam
- [NVDA](https://www.nvaccess.org/)
- [NVDA shortcuts](https://dequeuniversity.com/screenreaders/nvda-keyboard-shortcuts)

## Related posts

- [Test for web accessibility: introduction](https://make.wordpress.org/accessibility/handbook/best-practices/test-for-web-accessibility/)
- [Test for web accessibility: content](https://make.wordpress.org/accessibility/handbook/best-practices/test-for-web-accessibility-content/)
- [Test for web accessibility: design](https://make.wordpress.org/accessibility/handbook/test-for-web-accessibility-design/)
