# COYM — Comment on Your Major

COYM is a web app for exploring university majors and sharing student perspectives. Browse majors, read recent comments, join discussions, and see activity across the community.

**Live app:** [coym.netlify.app](https://coym.netlify.app)

**Backend API:** [coym-backend.onrender.com](https://coym-backend.onrender.com)

**API repository:** [github.com/lucakim27/coym-api](https://github.com/lucakim27/coym-api)

## Features

- Search a catalogue of university majors.
- Browse recent comments and popular majors.
- Comment on majors, reply to discussions, and like comments.
- Sign in, manage a profile, and explore community members.
- View community activity and charts.
- Submit feedback or feature requests.
- Responsive layouts for desktop and mobile screens.

## Built with

- Vue 3
- Vue Router
- Axios
- Chart.js and Vue Chart.js
- Vue CLI
- Netlify

## Run locally

### Prerequisites

- Node.js (18 or later recommended)
- npm
- Access to a running COYM API

### Install and configure

```bash
npm install
```

Create a `.env.local` file in the project root and set the API base URL:

```dotenv
VUE_APP_ROOT_API=https://coym-backend.onrender.com
```

For a local API, replace the value with its local base URL, such as `http://localhost:10000`. Vue CLI reads `VUE_APP_*` variables when it builds the app. Restart the development server or rebuild after changing this value.

Only put public configuration, such as the API URL, in frontend environment variables. Values bundled into a browser app are visible to users; never put database passwords, API secrets, or private keys there.

### Start the development server

```bash
npm run serve
```

The Vue CLI development server prints its local URL when it starts.

### Build for production

```bash
npm run build
```

The production files are generated in `dist/`.

### Lint the code

```bash
npm run lint
```

## Deploy to Netlify

This repository includes `public/_redirects` for Vue Router history-mode routes. Netlify should publish the production build from `dist/`.

Configure the following in the Netlify site settings:

| Setting | Value |
| --- | --- |
| Build command | `npm run build` |
| Publish directory | `dist` |
| Environment variable | `VUE_APP_ROOT_API=https://coym-backend.onrender.com` |

Set the variable for the deploy contexts you use, then trigger a new deploy. The value is applied at build time, so updating it without rebuilding will not change the deployed bundle.

## Project structure

```text
public/       Static files and SPA route fallback
src/
  assets/     Images and stylesheets
  components/ Shared Vue components
  views/      Page-level views
  router.js   Vue Router configuration
  App.vue     Root application component
  main.js     Application bootstrap
```

## Pages

| Route | Page |
| --- | --- |
| `/` | Home, recent comments, and popular majors |
| `/search` | Search majors |
| `/comment/:id` | Major discussion and replies |
| `/people` | Community members |
| `/profile/:id` | Member profile |
| `/chart` | Community activity charts |
| `/setting` | Profile settings and requests |
| `/aboutUs` | About COYM |
| `/privacyPolicy` | Privacy policy |
| `/termsAndConditions` | Terms and conditions |

## Related project

The Express and MySQL API is maintained in the [COYM API repository](https://github.com/lucakim27/coym-api). The frontend uses the `VUE_APP_ROOT_API` environment variable as its API base URL.
