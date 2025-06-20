# Accessibility tickets, tasks, and reports

WordPress uses several systems for tracking issues. Issues in WordPress itself are tracked in [core ticket tracking](https://core.trac.wordpress.org/). Issues with the network of sites at WordPress.org are tracked in the [meta ticket tracker](https://meta.trac.wordpress.org/) or in various independent repositories in the [WordPress Github organization](https://github.com/WordPress/). Issues in the development of the block and site editors are tracked in the [Gutenberg repository at GitHub.](https://github.com/WordPress/gutenberg/issues)

## Core Accessibility Tickets

- [All open tickets](https://core.trac.wordpress.org/query?status=!closed&focuses=~accessibility)
- [All open tickets, grouped by workflow and sorted by component, type, summary](https://core.trac.wordpress.org/report/30?FOCUS=accessibility)
- [Good first bugs](https://core.trac.wordpress.org/query?status=!closed&focuses=~accessibility&keywords=~good-first-bug)
- [Tickets with patches to test](https://core.trac.wordpress.org/query?status=!closed&focuses=~accessibility&keywords=~has-patch)

## Gutenberg Accessibility Issues

Gutenberg issues have two different labels.

- The [accessibility focus](https://github.com/WordPress/gutenberg/issues?q=is%3Aopen+is%3Aissue+label%3A%22%5BFocus%5D+Accessibility+%28a11y%29%22), representing issues that directly impact accessibility, and
- The [Needs Accessibility Feedback label](https://github.com/WordPress/gutenberg/issues?q=is%3Aopen+is%3Aissue+label%3A%22Needs+Accessibility+Feedback%22), representing UX changes seeking feedback on accessibility.

## Accessibility tasks

Tickets that are ongoing tasks because there’s the need to find instances, touch several parts of the code base, etc. They need to be split into separate tickets for each instance. Any help welcome!

These include general, broad, issues that either require substantial refactoring or exist broadly across many aspects of the admin. All tasks use the [a11y-task keyword](https://core.trac.wordpress.org/query?keywords=~a11y-task), so they can be located easily.

### Contribute to a task

Accessibility tasks are long-term projects, and may be completed by one or several people. A task can be in many different stages. Usually, there’s a research phase, then a development phase. This may be repeated multiple times, depending on the scope of the task. In a research phase, you identify examples of the problem in core, document those problems, and open new tickets for each individual problem or small group of problems.

- Find a specific instance of a problem.
- Open a ticket for that instance.
- Add a comment to the tracking ticket with a link to the new ticket.

During the development phase, the open tickets are resolved. The ticket can be closed when you are unable to locate examples of that problem in core.

## Accessibility keywords

Accessibility tickets grouped by topics. We use custom keywords to keep track of some main accessibility issues. To give some background about the progress so far, these reports show all the tickets, even the closed ones. Append `&status=!closed` to the URL to filter out the closed tickets.

- [Color contrast](https://core.trac.wordpress.org/query?keywords=~color-contrast)
- [Best practices for required fields in forms](https://core.trac.wordpress.org/query?keywords=~required-fields)
- [Use buttons for buttons, links for links](https://core.trac.wordpress.org/query?keywords=~semantic-buttons)
- [Review usage of target=”_blank”](https://core.trac.wordpress.org/query?keywords=~target-blank)
- [Standardize the types of search in the core admin](https://core.trac.wordpress.org/query?keywords=~uniform-search)
- [Use aria-current where appropriate](https://core.trac.wordpress.org/query?keywords=~aria-current)
- [Settings API improvements](https://core.trac.wordpress.org/query?keywords=~settings-api)
- [Proximity of related information and user interface controls](https://core.trac.wordpress.org/query?status=!closed&keywords=~a11y-proximity)
- [Form controls improvements](https://core.trac.wordpress.org/query?status=!closed&keywords=~form-controls)

If you find an accessibility issue in WordPress core, or in one of the core themes, please [create a new ticket](https://core.trac.wordpress.org/newticket) and give it the focus “accessibility”.
