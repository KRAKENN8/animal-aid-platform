---
status: Accepted
date: 19.10.2026
decision-makers: Ivan Petrov & Maksim Koroljov
---

# Frontend Technology Choice

## Context and Problem Statement

The platform has a public catalog of stray animals, search, animal cards and forms for volunteers and shelters. A frontend technology must be chosen. Public pages should load fast and be indexable by search engines.

## Decision Drivers

* SEO and fast first load of the public catalog
* Small team and fixed diploma deadline
* Maintainability and component reuse
* Ability to work with a separate REST API
* Support for interactive forms and role-based pages

## Considered Options

* Next.js
* React
* Angular
* Vue.js
* HTML + CSS

## Decision Outcome

Chosen option: "Next.js", because it supports server-side rendering and static generation for SEO, is built on React and its ecosystem, provides routing and data loading out of the box, works with TypeScript.

### Consequences

* Good, because public pages are indexable, first load is fast, one framework covers routing and rendering, large community and documentation, TypeScript support reduces errors
* Bad, because a Node.js runtime must be deployed, App Router has a learning curve, the boundary between server and client components is a source of bugs, deployment is more complex than a static site, frequent framework updates require maintenance

### Confirmation

"Next.js" was chosen as the most comfortable option of all those considered, having the most advantages for the team members: server-side rendering for the public catalog, React components, built-in routing, a large community and documentation.

## Pros and Cons of the Options

### Next.js

* Good, because of SSR and SSG, built-in routing, large ecosystem, typed code with TypeScript, image and font optimization
* Bad, because of the Node.js runtime in deployment, a steeper learning curve than a plain SPA, the server and client component boundary, more complex deployment than static hosting, significant changes between major versions

### React

* Good, because of reusable components, large ecosystem, flexible choice of libraries, simple static hosting as an SPA, a lot of learning material
* Bad, because SEO is weaker in an SPA, first load is slower, routing is assembled manually, data loading is assembled manually, project structure is not enforced

### Angular

* Good, because it is a complete framework with a clear structure, built-in forms, built-in routing, dependency injection, TypeScript by default
* Bad, because of a steep learning curve, heavy for a small project, more boilerplate, SEO needs extra setup (Angular SSR), larger bundle size than lighter alternatives

### Vue.js

* Good, because of a gentle learning curve, clear documentation, reactive components, single-file components, a lightweight core
* Bad, because the team's experience is unknown, a smaller ecosystem than React, SSR needs an extra framework (Nuxt), flexibility allows inconsistent code style, fewer ready-made third-party libraries than React

### HTML + CSS

* Good, because there are no dependencies, pages load fast, SEO is natural, hosting is trivial, it is easy to start
* Bad, because there is no component model, dynamic features require a lot of manual JavaScript, code is duplicated across pages, there is no built-in routing or state management, it does not scale for a platform with accounts
