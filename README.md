# React Router Dom Catch-All Route Order Bug
This repository demonstrates a common issue in React Router Dom v6 related to the order of routes, specifically when using a catch-all route (`/*`).  The incorrect placement of the catch-all route leads to other routes not being matched.

## Bug Description:
When a catch-all route (`/*`) is defined *before* other specific routes, it will always match first, preventing subsequent routes from ever being reached. This typically results in the catch-all component (e.g., a 404 page) being displayed even when other routes should match.

## How to reproduce:
1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that navigating to `/about` still shows the 404 page instead of the About component.

## Solution:
Ensure that catch-all routes are always placed *last* in your route definitions within the `<Routes>` component.