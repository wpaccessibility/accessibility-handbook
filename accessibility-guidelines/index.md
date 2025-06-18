## Accessibility Guidelines

The primary guidance for web accessibility on a global basis are the Web Content Accessibility Guidelines, commonly referred to as WCAG. WordPress requires that all content meet WCAG guidelines, but also pushes to provide accessibility beyond that minimum whenever possible.

## WordPress Accessibility Coding Standard

> All new or updated code released in WordPress must conform with the WCAG 2.2 guidelines at level AA.  
    [WordPress Accessibility Coding Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/accessibility-coding-standards/).

## WCAG explained

When building a new website, theme, or plugin, ask yourself these four questions:

1. [Is all content available to everyone?](https://make.wordpress.org/accessibility/handbook/which-questions-should-you-ask/#perceivable) (Perceivable)
2. [Can visitors use all functionality?](https://make.wordpress.org/accessibility/handbook/which-questions-should-you-ask/#operable) (Operable)
3. [Can visitors comprehend all content?](https://make.wordpress.org/accessibility/handbook/which-questions-should-you-ask/#understandable) (Understandable)
4. [Can visitors use any device?](https://make.wordpress.org/accessibility/handbook/which-questions-should-you-ask/#robust) (Robust)

These are the four principles of [Web Content Accessibility Guidelines](http://www.w3.org/WAI/intro/wcag) (WCAG) of what a website should be: [perceivable](http://www.w3.org/TR/WCAG20/#perceivable), [operable](http://www.w3.org/TR/WCAG20/#operable), [understandable](http://www.w3.org/TR/WCAG20/#understandable) and [robust](http://www.w3.org/TR/WCAG20/#robust).

These guidelines are created and updated by the [Web Accessibility Initiative](https://www.w3.org/WAI/) (WAI), a part of the international [World Wide Web Consortium](http://www.w3.org/) (W3C).

## Perceivable

Is all content available to everyone?

- Provide text alternatives for non-text content (e.g., images).
- Provide captions and other alternatives for multimedia.
- Create content that can be presented in different ways without losing meaning.
- Make it easy for users to see and hear content (e.g., by using color well, offering multimedia controls, and allowing text resizing).

## Operable

Can visitors use all functionality?

- Make all essential functionality available from a keyboard.
- Give users enough time to read and use content.
- Do not use content that causes seizures.
- Help users navigate and find content.

## Understandable

Can visitors comprehend all content?

- Make text readable and understandable.
- Use easy-to-comprehend text — avoid complex wording.
- Make content appear and operate in predictable ways.
- Guide users to avoid and correct mistakes.

## Robust

Can visitors use any device?

- Content must be able to be interpreted reliably by a wide variety of user agents, including assistive technologies.
- All user interface components should have programmatically determinable names and roles.

## Levels of Accessibility

There are 3 levels of accessibility:

- A (basic)
- AA (the global accessibility standard)
- AAA (for dedicated software)

Most European Union and many other countries use the accessibility standard WCAG 2.0 AA or equivalent for their government websites. Some countries require compliance with these guidelines for commercial websites, so the accessibility team uses these guidelines to improve WordPress core. [Overview of government accessibility laws and policies from the Web Accessibility Initiative](https://www.w3.org/WAI/policies/).

WCAG provides [techniques for implementing its principles](https://www.w3.org/WAI/policies/). Each issue has several solutions (techniques). Choose those that suit your theme or plugin best.

Use common sense when following WCAG techniques. **Pick** the one(s) that work well with your theme or plugin.

Decide which **browser and versions** your theme or plugin will support. Some WCAG techniques apply only to older browsers, e.g, Internet Explorer 7 and below. [WordPress no longer supports Internet Explorer as of version 5.8](https://wordpress.org/news/2021/05/dropping-support-for-internet-explorer-11/#:~:text=A%20large%20majority%20of%20popular,will%20no%20longer%20be%20supported.).
