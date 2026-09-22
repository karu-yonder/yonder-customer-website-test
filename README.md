# yonder-customer-website-test

Static test page for loading the Yonder customer widget against a chosen environment and activity provider (AP). Use it to preview chatbot and widget behaviour on a blank site, without embedding the script on a real customer website.

**Live page:** [https://karu-yonder.github.io/yonder-customer-website-test/](https://karu-yonder.github.io/yonder-customer-website-test/)

## How to use

Open the live page, then set `env` and `ap` in the control panel, or pass them as query params.

| Param          | Required | Values                   |
| -------------- | -------- | ------------------------ |
| `env`          | Yes      | `dev`, `staging`, `prod` |
| `ap` (or `id`) | Yes      | Activity provider id     |

Examples:

- [Staging](https://karu-yonder.github.io/yonder-customer-website-test/?env=staging&ap=123): `?env=staging&ap=123`
- [Dev](https://karu-yonder.github.io/yonder-customer-website-test/?env=dev&ap=123): `?env=dev&ap=123`
- [Prod](https://karu-yonder.github.io/yonder-customer-website-test/?env=prod&ap=123): `?env=prod&ap=123`

The page sets `window.YONDER__CLIENT_CODE` from `ap` and loads the matching widget script:

| Environment | Script                                        |
| ----------- | --------------------------------------------- |
| `dev`       | `https://dev.widget.yonderhq.com/main.js`     |
| `staging`   | `https://staging.widget.yonderhq.com/main.js` |
| `prod`      | `https://widget.yonderhq.com/main.js`         |

You can also open `index.html` locally in a browser.

## Deployment

GitHub Pages publishes `index.html` from `main` via the built-in Pages action.

- Action: [pages-build-deployment](https://github.com/karu-yonder/yonder-customer-website-test/actions/workflows/pages/pages-build-deployment)
- Workflow runs: [Actions](https://github.com/karu-yonder/yonder-customer-website-test/actions)
- Live URL: [https://karu-yonder.github.io/yonder-customer-website-test/](https://karu-yonder.github.io/yonder-customer-website-test/)

A push to `main` triggers `pages-build-deployment` and updates the live page.
