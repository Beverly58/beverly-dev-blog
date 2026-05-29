---

title: "A3 Reflection: Evaluating the Fandom Passport Prototype"
date: 2026-06-09
tags: [reflection, evaluation, web-development, accessibility, ai-assisted-development]
---------------------------------------------------------------------------------------

# A3 Reflection: Evaluating the Fandom Passport Prototype

For my final Bla+Bla prototype, I built **Fandom Passport**, a fandom community feature based on a passport-style identity system. The prototype allows users to select a fandom, view their fan identity, collect stamps, complete tasks, browse events, and engage with community content. My intention was to design a community feature that felt specific to fandom culture, rather than simply recreating standard social media functions such as posting, chatting, or uploading images.

This project was also a major technical jump for me. My previous coding work had mainly involved HTML, CSS, and p5.js, so building a full-stack prototype was outside my usual coding experience. I used an AI-assisted “vibe coding” workflow to help generate, debug, and revise parts of the implementation. This helped me build a working prototype, but it also introduced an important limitation: I did not preserve the required Bla+Bla technical stack.

## Evidence Used for Evaluation

### Evidence 1: Lighthouse Audit of Homepage

![Lighthouse audit result](/assets/lighthouse-homepage.png.png)

The Lighthouse audit of the homepage showed a **Performance score of 84**, **Accessibility score of 96**, and **Best Practices score of 77**. This suggests that the prototype performs reasonably well in local testing, especially in accessibility, while still having room for technical improvement.

### Evidence 2: Mini WCAG Accessibility Check

| Area Checked        | Method                                                                       | Finding                                                                                       | Improvement                                                         |
| ------------------- | ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Colour contrast     | I visually checked main text, buttons, muted labels, and pastel backgrounds. | Main headings and buttons are readable, but some small uppercase labels have weaker contrast. | Increase contrast for secondary labels and metadata text.           |
| Keyboard navigation | I used the Tab key to move through navigation and buttons.                   | Main items are reachable, but focus states could be more visible.                             | Add clearer focus outlines for interactive elements.                |
| Text readability    | I checked decorative fonts, small labels, and spacing.                       | The passport aesthetic is distinctive, but some decorative text may be harder to read.        | Increase important label sizes and reduce excessive letter spacing. |
| Icon labels         | I checked icon-supported buttons and navigation actions.                     | Most actions have visible labels, but some icon-based elements could be clearer.              | Improve aria-labels for icon-supported controls.                    |
| Responsive layout   | I resized the browser window and checked the homepage layout.                | The design works best on desktop; smaller screens can feel crowded.                           | Improve mobile spacing and stacked layouts.                         |

### Evidence 3: Task Walkthrough

| Task                      | Observation                                                              | UX Strength or Issue                                      |
| ------------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------- |
| Open the homepage         | Identity, fandom, rank, stamps, and points are visible immediately.      | Strong first impression and clear concept.                |
| Navigate to Stamps        | The Stamps page is accessible through main navigation and quick actions. | Navigation is clear and consistent.                       |
| Open Tasks                | The missions page communicates actions users can complete.               | Supports participation and engagement.                    |
| Change fandom             | The button is visible on the homepage.                                   | Useful, but could provide stronger confirmation feedback. |
| View Events and Community | Events and posts extend the passport experience.                         | Helps the prototype feel like a community system.         |

## Performance and Technical Behaviour

I tested the prototype locally using the browser, Chrome DevTools, and Lighthouse. The final version runs with a React frontend, a FastAPI backend, and a local MongoDB database. During testing, I confirmed that the backend could run on `localhost:8001` and the frontend could open on `localhost:3000`. I also checked that the homepage loaded successfully instead of staying on the “Could not open passport” error state.

The Lighthouse result provided measurable evidence for the prototype’s performance. A Performance score of 84 suggests that the homepage loads reasonably well in a local environment. Once MongoDB, the backend, and the frontend are all running correctly, navigation between pages such as Home, My Passport, Stamps, Tasks, Community, Events, and Profile feels responsive. React Router also helps the prototype feel smoother because page changes do not require a full reload.

However, the main technical weakness is setup reliability. The prototype depends on several services running at the same time: MongoDB, the backend server, the frontend server, and correct `.env` configuration. When one part was missing or incorrectly configured, the application failed to load properly. For example, if MongoDB was not active, the backend could not connect to the database. If the frontend environment variable pointed to the wrong backend URL, the app stayed on the retrying message. This showed me that a working interface is not enough; the technical setup must also be stable and clearly documented.

Another limitation was dependency management. The frontend required `npm install --legacy-peer-deps`, and the backend requirements file needed adjustment because one package could not be installed. These issues made the project harder to run for someone else, so I added README instructions explaining MongoDB, backend setup, frontend setup, and environment variables.

## User Experience and Accessibility

The strongest part of the prototype is the concept and user experience. The passport metaphor is consistent across the interface, including the home page, identity page, stamps, tasks, and events. This helps the feature feel specific to fandom culture. Instead of being a general community feed, the system presents fandom participation as something users can record, collect, and display.

The homepage works well as an entry point because it immediately shows the user’s fandom identity, rank, stamp progress, points, events, and community posts. This gives users a clear understanding of who they are in the system and what they can do next. The navigation labels are also understandable because pages such as My Passport, Stamps, Tasks, Community, and Events match the main user goals.

The accessibility evidence was mixed but useful. The Lighthouse Accessibility score of 96 suggests that the prototype has a relatively strong accessibility baseline. The mini WCAG check also showed that most main actions have visible text labels and that the core interface can be navigated. However, some smaller uppercase labels and muted metadata text could have better contrast. The decorative passport aesthetic is visually distinctive, but some text may be harder to read for users with low vision or on smaller screens. If I continued development, I would improve colour contrast, focus states, aria-labels, and mobile spacing.

## Critical Reflection on AI-Assisted Development and Technical Compliance

A major limitation of my final prototype is that I moved away from the required BlaBla template stack. The brief specified that the project should remain based on MojoJS, SQLite, and HTMX, while my final implementation used React, FastAPI, and MongoDB. I misunderstood the level of flexibility allowed when extending the template. I focused on building the Fandom Passport interaction, including the passport-style interface, user identity data, stamps, tasks, events, and community content, but I now understand that adding features should not have meant replacing the core stack.

AI tools were used as part of my development workflow. I used Emergent and ChatGPT to support parts of the implementation process, including code generation support, interpreting errors, debugging local setup problems, resolving dependency issues, configuring environment variables, and troubleshooting frontend/backend connection errors. This support helped me attempt a more ambitious prototype than I would normally attempt with only my previous HTML, CSS, and p5.js experience. However, it also made it easier to continue developing the implementation without fully checking whether the architecture still matched the brief.

This has been the most important lesson from the project. Technical compliance is not separate from design quality. Even though the prototype communicates the intended fandom community experience, the mismatch with the required stack means it does not fully meet an important implementation requirement. If I continued or repaired this project, my first priority would be to rebuild the core passport, stamp, and task interactions within the original BlaBla stack, rather than only improving the visual interface.


## Retrospective Assessment of Functional Requirements

Conceptually, the prototype meets the goal of designing a unique community feature. It includes fandom selection, a passport-style homepage, identity/profile areas, collectible stamps, missions, events, community content, and an admin page. These features support the intended experience of fandom identity and participation.

However, I cannot evaluate the project as fully successful because the implementation does not preserve the required technical stack. The strongest parts of the project are the concept, visual identity, and user flow. The weakest part is compliance with the original BlaBla template requirements. This is a significant issue, not just a small technical detail.

Overall, the project helped me understand both the potential and the risk of AI-assisted development. It allowed me to explore a more ambitious full-stack prototype, but it also showed that I need to check technical constraints earlier and more carefully. In future projects, I would confirm implementation requirements before building, document AI assistance more continuously, and make sure that the technical approach supports the brief rather than accidentally moving away from it.
