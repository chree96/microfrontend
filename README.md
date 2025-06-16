# microfrontend

## Introduction
This project is an example of a microfrontend architecture mainly built with React.JS (and a Dashboard in Vue to show multi-frameworks compatibility). It demonstrates how to split a web application into independent modules, each managed and deployed separately. The integration is achieved using Webpack Module Federation for dynamic loading of microfrontends.

## Project structure
The monorepo contains four main packages (inside the packages/ folder):
- container: The main (host) application that orchestrates and integrates the microfrontends.
- marketing: Microfrontend dedicated to marketing pages (React).
- auth: Microfrontend dedicated to authentication (React).
- dashboard: Microfrontend for the user dashboard (Vue).

## Tech Stack
- React
- Vue (only for dashboard)
- Webpack 5 + Module Federation
- Material UI
- React Router

## Architecture
Each microfrontend is exposed via Module Federation (remoteEntry.js) and can be started independently in development (localhost:8081, 8082, 8083, etc.). The container imports the remotes via webpack and displays them based on routing.

## How to run locally
1. Install dependencies
```sh
npm install
```

2. Start each package in a different shell
```sh
cd packages/container && npm start
cd packages/marketing && npm start
cd packages/auth && npm start
cd packages/dashboard && npm start
```

3. Visit http://localhost:8080 to view the main application.

## Notes
- The dashboard is written in Vue to showcase interoperability between different frameworks using Module Federation.
- All microfrontends share some dependencies to reduce duplication.
