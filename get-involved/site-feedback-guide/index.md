# Site Feedback Guide

On occasion, the Make WordPress Accessible group has been asked to review a wordpress.org site and provide feedback on any accessibility issues. The following document contains a series of guidelines (organised by skill level and technology usage) that should enable you to do so — irrespective of whether you are a technical developer or a non-technical WordPress user.

- [Technical Users](https://make.wordpress.org/accessibility/handbook/get-involved/site-feedback-guide/#technical-users)
- [Non-technical Sighted Users](https://make.wordpress.org/accessibility/handbook/get-involved/site-feedback-guide/#non-technical-sighted-users)
- [Screen Reader Users](https://make.wordpress.org/accessibility/handbook/get-involved/site-feedback-guide/#screen-reader-users)
- [Sighted Keyboard Users](https://make.wordpress.org/accessibility/handbook/get-involved/site-feedback-guide/#sighted-keyboard-users)
- [All Users](https://make.wordpress.org/accessibility/handbook/get-involved/site-feedback-guide/#all-users)

## Technical Users

### CSS

If you use web developer tools and can easily disable Cascading Style Sheets (CSS) , Javascript and image display in your browser, please try the following:

- Disable all CSS:
  - Does the site still render in a logical order?
  - Are the various elements and sections still clear (e.g. headings, paragraphs, forms, lists, links and navigation)
- Enable CSS & disable all images:
  - Is alternate text or image replacement used?
  - Are headings and other important elements visible?
  - Is the contrast still usable?
- Disable all CSS & images:
  - Are the various elements and sections still clear?
  - Is alternate text used for images added via markup?
  - Could these images be better implemented using CSS?
  - Are headings and other important elements visible?
  - Is the contrast still usable?
- Disable Javascript:
  - Does the site still work effectively?
  - Are any visible links broken?

### Markup

- How semantic and proper is the mark-up?
- Are headings used effectively and in a reasonable order?
- Is list markup used for lists?
- Is blockquote markup used correctly or has it been used purely for presentation?
- Is emphasis markup used correctly or has it been used purely for presentation?
- Is tab indexing used wisely?
- Are accesskeys used at all?

## Non-technical Sighted Users

### Images

- Does the site use images in a way that supports reading & comprehension?
- If the site has few images, would it benefit from more to support those whose first language is not used on the site (e.g. sign language users)?

### Links

- Are links in the page’s content area easy to find/see or do you have to search for them?
- Does link text actually describe the resource it is pointing to?
- Would the link text still be understood if it was read out of context?
- If you are using a mouse:
  - Are links easy to click on?
  - Are hover styles used on links which do not depend entirely on color?
  - Do these styles also work on visited links?
- How effectively are links separated?

### Fonts

- Are the fonts used on the site easy to read?
- Are there too many font/text styles in use?

### Forms

- Are forms easy to use and complete?
- If you click on the label of a form input, does the cursor immediately appear in the relevant form input?
- If you make a mistake, does the form try to highlight your error, so you can correct it?

## Screen Reader Users

- How well does the site sound?
- Is it clearly read or are there redundancies or spots of missing information?
- Are image alt attributes used effectively?
- Are there any images that need much longer descriptions (e.g charts)?
- Can you access skip navigation links?
- Do the skip navigation links work effectively?
- Are you forced to move through too many navigation links to reach the one you want?
- If you have access to Heading Lists, do the headings support your understanding of the page?
- If you have access to Link Lists, do the links still make sense when rendered in this list?
- How effectively are links separated if you do not use a Link List?
- Are there any links that allow you to move up & down a given page?
- If “yes”, are they used effectively?
- If “no”, would the page benefit from such links?
- Are forms easy to understand and complete?
- If you make a mistake, does the form try to highlight your errors in an effective manner?

## Sighted Keyboard Users

- When you move into the page, do you become lost very easily?
- Can you access skip navigation links?
- Do the skip navigation links work effectively?
- Are links easy to find/see or do you have to search for them?
- Are there any links that allow you to move up & down a given page?
- If “yes”, are they used effectively?
- If “no”, would the page benefit from such links?
- Is it easy to see which link currently has focus?
- When completing forms, is it easy to see which form input currently has focus?
- Are there any areas of the site that you cannot access?

## All Users

### Readability

- Is it clear what the site is for?
- Can you easily distinguish the navigation menus from (say) the page’s main content?
- How readable is the site’s content?
- Is there any text that is hard to see and/or read?
- How easily can the content in a page be digested?
- Is it broken down into easy-to-digest chunks?
- Is the site’s content exceedingly verbose, or it is clear and brief in its presentation?
- Are the headings used in a way that makes sense?
- How about the spelling – is it correct?
- Are abbreviations expanded or explained?
- How useful is the title element at the top of the browser window?
- Does it reveal something useful about the current page?
- If you bookmark the page, is the bookmark’s text concise and accurate or too verbose?

### Additional Visitor Support

- Does the site have an effective search tool?
- Does the site include an accessibility statement?
- Does the site include a privacy policy
- Try to navigate to a non-existent page. Is the resulting error page helpful?
- Is it easy to make contact with the site’s owner or do you have to jump through hoops?


