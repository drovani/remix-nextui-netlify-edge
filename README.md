# Welcome to Remix!

- [Remix Docs](https://remix.run/docs)
- [Netlify Functions Overview](https://docs.netlify.com/functions/overview)

## Steps to recreate this project

1. [Create a new Remix app to deploy to Netlify](https://docs.netlify.com/frameworks/remix/#create-a-new-remix-app-to-deploy-to-netlify)
    1. `npx create-remix@latest --template netlify/remix-template`
1. [Install Tailwind CSS with Remix](https://tailwindcss.com/docs/guides/remix)
    1. `npm install -D tailwindcss postcss autoprefixer`
    1. `npx tailwindcss init --ts -p`
    1. Update `./tailwind.config.ts`
    1. Create `./app/tailwind.css`
    1. Add `LinksFunction` export to `./app/root.tsx`
1. Run `npm build && netlify serve` to validate that solution executes as expected.
1. [Implement NextUI in Remix](https://nextui.org/docs/frameworks/remix)
    1. `npm i @nextui-org/react framer-motion`
    1. Update `./tailwind.config.ts` with NextUI plugin
    1. Add `NextUIProvider` wrapper around the app in `./app/root.tsx`
1. Run `npm build && netlify serve` to validate that solution still executes as expected.
1. Add any NextUI component to the `./app/routes/_index.tsx` component
    1. Example: replace the first `<a>`nchor tag with a `<Link>` component
1. Run `npm build && netlify serve` and observe the following error:
```
  ◈ Loaded edge function remix-server
  [remix-server] ReferenceError: document is not defined
    at $431fbd86ca7dc216$export$b204af158042fbac (file:///home/drovani/remix-nextui-netlify-edge/build/server/assets/server-build-CTJ-Eq0G.js:14439:155)
    at $431fbd86ca7dc216$export$f21a1ffae260145a (file:///home/drovani/remix-nextui-netlify-edge/build/server/assets/server-build-CTJ-Eq0G.js:14443:15)
    at $507fabe10e71c6fb$var$setupGlobalFocusEvents (file:///home/drovani/remix-nextui-netlify-edge/build/server/assets/server-build-CTJ-Eq0G.js:15512:86)
    at $507fabe10e71c6fb$export$ec71b4b83ac08ec3 (file:///home/drovani/remix-nextui-netlify-edge/build/server/assets/server-build-CTJ-Eq0G.js:15605:3)
    at $f7dceffc5ad7768b$export$4e328f61c538687f (file:///home/drovani/remix-nextui-netlify-edge/build/server/assets/server-build-CTJ-Eq0G.js:15716:3)
    at useLink (file:///home/drovani/remix-nextui-netlify-edge/build/server/assets/server-build-CTJ-Eq0G.js:18728:53)
    at file:///home/drovani/remix-nextui-netlify-edge/build/server/assets/server-build-CTJ-Eq0G.js:18762:7
    at Wc (file:///home/drovani/remix-nextui-netlify-edge/build/server/assets/server-build-CTJ-Eq0G.js:13602:13)
    at Zc (file:///home/drovani/remix-nextui-netlify-edge/build/server/assets/server-build-CTJ-Eq0G.js:13727:13)
    at Z$1 (file:///home/drovani/remix-nextui-netlify-edge/build/server/assets/server-build-CTJ-Eq0G.js:13784:9)
```
1. Reset the `<a>`nchor tag back to the HTML element and rerun `npm build && netlify serve`; all is well.