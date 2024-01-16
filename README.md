# Contents

- [Documentation](https://github.com/daffaalex22/wisata-clone/edit/main/README.md#documentation)
- [Accessing The App](https://github.com/daffaalex22/wisata-clone/edit/main/README.md#accessing-the-app)
- [Run Locally](https://github.com/daffaalex22/wisata-clone/edit/main/README.md#accessing-the-app)

## Documentation
This repo is created as a technical test for recruitment for Fullstack Engineer position at Wisata App.

This is a Clone for one of the page from [Wisata App](https://wisata.app/stay/the-langham-jakarta-9001948244/?guest_per_room=2&number_of_room=1&checkin=2024-06-25&checkout=2024-06-26). 

### Technology

Upon inspecting the page, the author found that Wisata App uses many components from Google's Material Design. Morever, the author found that Wisata App is made using Nuxt. In an attempt to create a result as similar as the prescribed page, this project is made using:

- Nuxt, a JS library based off of Vue.js
- Vuetify, a UI library for Vue.js that's created based on Google's Material Design Specification

#### Decisions

There might be a couple of other decisions that I do not list here due to time limitation.

* Upon inspecting the page, it's found that wisata.app is built using Nuxt
![Inspect](/assets/inspect-element-nuxt.png)
* The author cannot find Hotel's headline with the exact same copywriting, so `data.general_info.descriptions.headline`, which consists of only 3 words, is used instead.
* The icon used for when `meal_plan_description === ""` (i.e. Without breakfast) cannot be found in the Material Design Icons specification
* Upon implementing the Skeleton Loader, the author found an error that doesn't render the whole components showing property's offer after fetching data from API. The way the author solves that is by implementing some watchers and updating the associated reactive states. Due to this close-to-deadling error, Skeleton loader is not implemented
* It is stated on the `exterior-technical-test-b` repository that the **See details** (Room details) button feature should not be implemented. However, the this feature is the same feature as clicking the image grids (See Photos button). Due to this confusion and time limitation, the author doesn't implement this.

### API
The API used here is the one's provided from the test description:
```
https://exterior-technical-test-api.vercel.app/
```

The endpoints used are:
```
https://exterior-technical-test-api.vercel.app/property?id=<PROPERTY_ID>
https://exterior-technical-test-api.vercel.app/property/availability/<PROPERTY_ID>
```

## Accessing The App

The App can be accessed at [wisata-clone.vercel.app/](https://wisata-clone.vercel.app/)

On the root page, user will be redirected to `/stay/<SLUG>/?<QUERY_PARAMS>` page instead. While it's has been said on the requirement that the Search Feature doesn't need to be implemented, user can actually change the `SLUG` part or the `QUERY_PARAMS` part of the URL to access different hotels/property page, as well as discovering availability for different dates.

## Run Locally
### Setup

Clone this repository

```bash
git clone https://github.com/daffaalex22/wisata-clone.git
```

Make sure to install the dependencies:

```bash
# npm
npm install

# pnpm
pnpm install

# yarn
yarn install

# bun
bun install
```
### Development Server
Start the development server on `http://localhost:3000`:
```bash
# npm
npm run dev

# pnpm
pnpm run dev

# yarn
yarn dev

# bun
bun run dev
```
