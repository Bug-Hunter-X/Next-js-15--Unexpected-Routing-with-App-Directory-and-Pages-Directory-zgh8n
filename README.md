# Next.js 15 Routing Conflict: App Directory and Pages Directory

This repository demonstrates a conflict that can arise when using both the Next.js 15 App Directory and the traditional Pages directory simultaneously.  The presence of both can lead to unexpected routing behavior, where requests might be handled by the wrong directory.

## Bug Description

When creating a simple 'Hello World' page in the App directory, it is expected that accessing the root route ('/') would render this page. However, if a similarly named file exists in the 'pages' directory, routing may become ambiguous, potentially serving the 'pages' version instead.  This can create difficult-to-debug routing problems.

## Steps to Reproduce

1. Create a Next.js 15 app.
2. Place a `page.js` inside the `app` directory.
3. Place a `pages/index.js` inside the pages directory.
4. Start the development server.
5. Access the root URL. Observe unexpected behavior.

## Solution

To resolve the conflict, either:

* Remove the legacy `pages` directory, entirely moving to the new App Router.
* Re-structure your routes so the pages in app directory and pages directory do not conflict.

This clear separation ensures predictable routing and avoids unexpected behavior.