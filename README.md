# Monsters Rolodex

A small React app that shows a searchable gallery of "monster" profile cards. I built it in early 2020 while learning React: component composition, state, lifecycle methods and deploying to GitHub Pages.

## What it does

- Fetches a list of users from the [JSONPlaceholder](https://jsonplaceholder.typicode.com/) REST API when the app mounts
- Renders each user as a card with a generated monster avatar from [RoboHash](https://robohash.org/), plus their name and email
- Filters the cards live as you type in the search box

## How it's built

```
App                 class component: holds the fetched users and the search text in state
├── SearchBox       controlled input that reports each keystroke back up to App
└── CardList        maps the filtered users to cards
    └── Card        avatar + name + email
```

- **React 16** (class component with `componentDidMount` for the data fetch), bootstrapped with Create React App
- Presentational components receive data through props and keep no state of their own
- Filtering runs in `render()`, so the list always matches the current search text
- Deployed to GitHub Pages with the `gh-pages` package

## Branches

- `master`: source code
- `gh-pages`: production build served by GitHub Pages

## Run locally

```bash
git clone -b master https://github.com/SugamKumar/monsters.git
cd monsters
npm install
npm start          # dev server at http://localhost:3000
npm run build      # production build
npm run deploy     # publish the build to GitHub Pages
```
