## Run Locally
### Setup
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
## Documentation
This repo is created as a technical test for recruitment for Fullstack Engineer position at Wisata App.

This is a Clone for one of the page from [Wisata App](https://wisata.app/stay/the-langham-jakarta-9001948244/?guest_per_room=2&number_of_room=1&checkin=2024-06-25&checkout=2024-06-26). 

### Technology

Upon inspecting the page, the author found that Wisata App uses many components from Google's Material Design. Morever, the author found that Wisata App is made using Nuxt. In an attempt to create a result as similar as the prescribed page, this project is made using:
- Nuxt, a JS library based off of Vue.js
- Vuetify, a UI library for Vue.js that's created based on Google's Material Design Specification

#### Decisions

* Upon inspecting the page, it's found that wisata.app is built using Nuxt
![Inspect](/assets/inspect-element-nuxt.png)
* The author cannot find Hotel's headline with the exact same copywriting, so `data.general_info.descriptions.headline`, which consists of only 3 words, is used instead.
* The icon used for when `meal_plan_description === ""` (i.e. Without breakfast) cannot be found in the Material Design Icons specification

### API
The API used here is the one's provided from the test description:
```
https://exterior-technical-test-api.vercel.app/
```

The endpoints used are:
```
```