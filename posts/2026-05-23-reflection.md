---
title: "A3 Reflection: Evaluating the Fandom Passport Prototype"
date: 2026-06-09
tags: [reflection, evaluation, web-development, accessibility]
---

# A3 Reflection: Evaluating the Fandom Passport Prototype

For my final Bla+Bla prototype, I built a web application called **Fandom Passport**, a community feature designed for fan communities. Instead of recreating a normal social platform, I focused on a more distinctive fandom identity system. The prototype uses a passport metaphor to represent fan identity, participation, events, missions, and collectible stamps. Looking back at the project, I think the strongest part is that the concept became visually clear and functional as a web experience. At the same time, testing also showed some technical and usability limitations that I would improve in future development.

## Evidence Used for Evaluation

### Evidence 1: Lighthouse Audit of Homepage

![Lighthouse audit result](/assets/lighthouse-homepage.png.png)

The Lighthouse audit of the homepage showed a **Performance score of 84**, **Accessibility score of 96**, and **Best Practices score of 77**. This suggests that the prototype performs reasonably well overall, especially in accessibility, but still has room for technical improvement.

### Evidence 2: Mini WCAG Accessibility Check

| Area Checked | Method | Finding | Improvement |
|---|---|---|---|
| Colour contrast | I visually checked the main text, buttons, muted labels, and pastel background colours. | Main buttons and headings are readable, but some small uppercase labels have lower contrast against the light background. | Increase contrast for secondary labels and metadata text. |
| Keyboard navigation | I used the Tab key to move through the main navigation and quick action buttons. | The main navigation items and buttons are reachable, but the visible focus state could be stronger. | Add clearer focus outlines for all interactive elements. |
| Text readability | I checked decorative fonts, small labels, letter spacing, and information hierarchy. | The passport aesthetic is distinctive, but some decorative or small text may be harder to read for some users. | Increase important label sizes and reduce excessive letter spacing where needed. |
| Icon buttons and labels | I checked navigation buttons, quick actions, and icon-supported buttons. | Most actions include visible text labels, but some icon-based elements could be clearer for assistive technologies. | Add or improve aria-labels for icon-based buttons. |
| Responsive layout | I resized the browser window and checked the homepage layout. | The interface works best on desktop; smaller screen widths can make the card layout feel crowded. | Improve mobile spacing and simplify stacked layouts on small screens. |

### Evidence 3: Task Walkthrough

| Task | Observation | UX Strength or Issue |
|---|---|---|
| Open the homepage | The user identity, fandom, rank, stamps, and points are visible immediately. | Strong first impression and clear concept. |
| Navigate to Stamps | The Stamps page can be accessed from the main navigation and quick actions. | Navigation is clear and consistent. |
| Open Tasks | The missions page communicates that users can complete actions. | Supports engagement and participation. |
| Use Change my fandom | The button is visible on the homepage. | Useful function, but it could provide stronger confirmation feedback. |
| View Events and Community | Events and posts are shown as part of the wider passport experience. | Helps the prototype feel like a community system rather than a single static page. |

## Performance and Technical Behaviour

To evaluate technical performance, I tested the prototype locally using the browser, Chrome DevTools, and Lighthouse. The final version runs with a React frontend, a FastAPI backend, and a local MongoDB database. During testing, I confirmed that the backend could run on `localhost:8001` and the frontend could open on `localhost:3000`. I also tested the frontend/backend connection by checking that the homepage loaded correctly instead of staying on the “Could not open passport” message.

The Lighthouse result was useful because it gave measurable evidence instead of only relying on my own impression. The Performance score of 84 shows that the homepage performs reasonably well in a local environment. The interface loads smoothly once all required services are running, and navigation between pages such as Home, My Passport, Community, Events, Stamps, Tasks, and Profile feels responsive. Because the application uses React Router, moving between pages does not require a full page reload, which helps the prototype feel more polished.

However, the testing process also revealed technical weaknesses. The main issue was setup reliability. The application depends on MongoDB, the backend server, the frontend server, and correct `.env` files. When one of these parts was not running, the whole experience failed. For example, if MongoDB was not active, the backend produced connection errors. If the frontend environment variable did not point to the backend correctly, the page stayed on the retrying message. This showed that the prototype works, but its reliability depends heavily on local configuration.

Another technical issue was dependency management. The frontend needed `npm install --legacy-peer-deps`, and the backend requirements needed adjustment because one package could not be installed. These issues did not change the visual design, but they affected how easily another person could run the prototype. Because of this, I added clearer README instructions for MongoDB, backend setup, frontend setup, and environment variables. If I continued the project, I would add an `.env.example` file and possibly use Docker to make the setup more stable.

## User Experience and Accessibility

The user experience is one of the stronger parts of the prototype. The passport metaphor is consistent across the visual style, navigation, identity page, stamps, tasks, and events. This helps the application feel different from a normal social media platform. It also fits the brief because the prototype focuses on a unique community feature rather than standard chat or upload functions.

The homepage works well as an entry point. It immediately shows the user’s fandom identity, rank, stamp progress, points, upcoming events, and community posts. This gives users a quick understanding of who they are in the system and what they can do next. The main navigation is also clear because labels such as My Passport, Stamps, Tasks, Community, and Events match the user’s expected actions.

The mini WCAG check showed that the prototype is generally readable and navigable, especially because most important buttons use visible text labels. The Lighthouse Accessibility score of 96 also suggests that the basic accessibility performance is strong. However, the check also revealed areas for improvement. Some small uppercase labels and muted metadata text have lower contrast against the pastel background. The decorative visual style supports the passport theme, but some text may be harder to read for users with low vision or on smaller screens. Keyboard navigation works for the main interface, but focus states could be more visually obvious.

If I had more time, I would improve colour contrast, add clearer focus outlines, and check all icon-supported buttons for better aria-labels. I would also refine the mobile layout because the current interface works best on desktop, while smaller screens can make the card layout feel crowded.

## Critical Reflection and Improvement Planning

The biggest lesson I learned is that a strong concept still needs technical stability. At first, I focused mainly on the fandom passport idea: fan identity, stamps, missions, and participation. This gave the project a clear design direction. However, during implementation and testing, I realised that the technical structure is just as important. If the backend or environment variables fail, the user cannot experience the concept at all.

One design decision that worked well was using the passport metaphor consistently. Visa labels, stamps, rank, and missions all support the idea that fandom participation can be collected and recorded. This made the application feel more unique than a standard community feed.

One weaker implementation decision was relying on several manual setup steps. I had to run MongoDB, activate the backend environment, start the backend server, and run the frontend separately. In future, I would plan the technical setup earlier and document it while building, not only at the end. I would also make error states more user-friendly. Instead of only showing “Could not open passport,” the app could explain whether the backend connection failed or the user session was unavailable.

I would also improve the reward system. The current stamp and task pages communicate the idea, but the interaction could be more dynamic. For example, completing a task could immediately unlock a stamp, update progress, and show a confirmation animation. This would make the relationship between user action and reward clearer.

## Retrospective Assessment of Functional Requirements

Compared with my original plan, the final prototype meets the main functional requirements. My goal was to create a unique Bla+Bla community feature for fandom users, and the final application does this through the Fandom Passport system. It includes fandom selection, a passport-style homepage, identity/profile areas, stamps, tasks, events, community content, and an admin page.

Some requirements were adjusted during development. Initially, I imagined a more complex fan qualification system with deeper unlocking logic. In the final prototype, I focused on making the main experience clear and functional rather than adding too many advanced features. This was a realistic decision because the assignment asked for a prototype of the standout feature, not a complete production system.

I also realised that some standard social platform features were less important. Chat and photo upload were not the focus of my concept. The more important functions were the passport identity, stamp collection, and mission system, because these made the community experience more distinctive.

Overall, I think the prototype successfully demonstrates the core idea of a fandom community passport. It performs reasonably well in local testing, has a strong accessibility score, and provides a clear user experience. The main improvements I would make are simplifying setup, strengthening accessibility details, and making the reward interactions more dynamic.
