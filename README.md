# Single Page Application starter

This is a suggested stack to build modern SPA.  
It's hosted here: TODO

It's composed of:

-   [Docker](https://www.docker.com/)
-   [Nginx](https://www.nginx.com/)
-   [Vite](https://vitejs.dev/)
-   [TypeScript](https://www.typescriptlang.org/)
-   [React](https://reactjs.org/)
-   [Tanstack Router](https://tanstack.com/router/v1) - A better alternative to React Router.
-   🐓 [react-dsfr](https://react-dsfr.codegouv.studio/) - The React Toolkit for [The French Design System](https://www.systeme-de-design.gouv.fr/) (DSFR)
-   [MUI](https://mui.com/material-ui/) - As a backup component library to fallback to if you don't find the component you need in [the DSFR library](https://components.react-dsfr.codegouv.studio/?path=/story/%F0%9F%87%AB%F0%9F%87%B7-introduction--page).
-   🐓 [vite-envs](https://github.com/garronej/vite-envs) - A solution to avoid having to re-build the app when you change the environment variables.
-   🐓 [tss-react](https://www.tss-react.dev/) - A CSS-in-JS solution.
-   🐓 [i18nifty](https://www.i18nifty.dev/) - A solution to to make your app available in multiple languages.
-   [react-query](https://react-query.tanstack.com/) - A solution to manage your API calls.
-   🐓 [oidc-spa](https://www.oidc-spa.dev/) - A solution to integrate OpenID Connect in your app. (Keycloak)
-   🐓 [tsafe](https://github.com/garronej/tsafe) - Type safety utilities.
-   🐓 [ts-ci](https://github.com/garronej/ts-ci) - GitHub Actions to manage the lifecycle of the project and publish automatically on Docker Hub.
-   [Prettier](https://prettier.io/) - Code formatter.
-   [Orval](https://orval.dev/) - A solution to generate API clients based on OpenAPI specs.

🐓: Made by us.

## Running locally

```env
git clone https://github.com/InseeFrLab/vite-insee-starter
cd vite-insee-starter
cp .env.sample .env.local
yarn
yarn dev
```

## The TODO rest API

For demoing this stack we created a simple todo app REST API.  
It's available here: https://github.com/InseeFrLab/todo-rest-api

## Keycloak theme

When authenticating you will notice that the login pages are DSFR themed.  
We're using the custom keycloak theme of the DSFR: [keycloak-theme-dsfr](https://github.com/codegouvfr/keycloak-theme-dsfr) 🐓.  
It has been created using [react-dsfr](https://react-dsfr.codegouv.studio/) and [Keycloakify](https://keycloakify.dev/).

## Build with this stack:

### Onyxia

-   [Source code](https://github.com/InseeFrLab/onyxia)
-   [Public instance](https://datalab.sspcloud.fr)

<a href="https://youtu.be/FvpNfVrxBFM">
  <img width="1712" alt="image" src="https://user-images.githubusercontent.com/6702424/231314534-2eeb1ab5-5460-4caa-b78d-55afd400c9fc.png">
</a>

### The French Interministeriel Base of Free Software

-   [Source code](https://github.com/codegouvfr/sill-web/)
-   [Deployment of the website](https://sill-preprod.lab.sspcloud.fr/)

<a href="https://youtu.be/AT3CvmY_Y7M?si=Edkf0vRNjosGLA3R">
  <img width="1712" alt="image" src="https://github.com/garronej/i18nifty/assets/6702424/aa06cc30-b2bd-4c8b-b435-2f875f53175b">
</a>

## Why pushing tss-react over other styling solution?

You might think that tss-react isn't the more obvious choice and I'm just pushing it because we made it but here me out.  
It has approximately 900 000 downloads per month and is used by establish solution like [Jitsi](https://jitsi.org/) and
it integrates flawlessly with MUI. It's even [mentioned in the official MUI documentation](https://mui.com/material-ui/migration/migrating-from-jss/#2-use-tss-react).

But more importantly. It's arguably the one of the most powerful styling solution. It enables to write styles as a function of the internal state of the component.  
It let you express sophisticated styling logic in a way that is easy to read and maintain.

It's drawback is that, as it's a dynamic styling solution (as opposed to statically extracted ones like tailwind), it's doesn't have the same performance and is not
compatible with Next.js Server Components. However at Insee we're building SPA and the performance hit is negligible (we're talking about a few milliseconds).
