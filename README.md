# GitHub Insights

A front-end web app built around the **GitHub REST API**, written in vanilla JavaScript and styled with **Tailwind CSS**. It shows a GitHub profile at a glance, lets you search any user's public repositories, and visualizes their language usage with interactive charts.

## Features

- **Profile sidebar** for the authenticated user: avatar, name, username, bio, followers, following, public repo count, and membership duration (via Moment.js)
- **Country flag** resolved from the user's profile location using GitHub's emoji API
- **User search** with debounced input: type a username to load their public repositories
- **Repository grid**: cards with name (linked to GitHub), description, and primary language
- **Profile Insights** view: pie and bar charts (Chart.js) of language frequency and percentage across the user's repos

## Tech Stack

| Purpose     | Technology |
| ----------- | ---------- |
| Language    | Vanilla JavaScript (ES modules) |
| Styling     | Tailwind CSS 3 + custom CSS |
| Charts      | [Chart.js](https://www.chartjs.org/) (CDN) |
| Dates       | [Moment.js](https://momentjs.com/) |
| Data        | [GitHub REST API](https://docs.github.com/en/rest) |

## Project Structure

```
github-insights/
├── src/
│   ├── index.html        # App layout (sidebar, search, repo grid, insights)
│   ├── script.js         # API calls, search, rendering, charts
│   ├── input.css         # Tailwind entry file
│   ├── style.css         # Custom styles
│   └── icons/            # SVG icons
├── dist/
│   └── output.css        # Compiled Tailwind CSS
├── tailwind.config.js    # Custom colors and font sizes
└── package.json
```

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) and npm
- A GitHub [personal access token](https://github.com/settings/tokens) (classic, no scopes needed for public data)

### Installation

```bash
git clone https://github.com/SifeYassine/github-insights.git
cd github-insights
npm install
```

### Configuration

Open `src/script.js` and replace the placeholder with your token:

```js
headers.append("Authorization", "bearer <My_Token>");
```

> ⚠️ Never commit your real token. The sidebar shows the profile of the user who owns this token.

### Build the CSS

```bash
npm run build
```

This runs the Tailwind CLI in watch mode and writes `dist/output.css`.

### Run

The app uses ES modules and imports Moment.js from `node_modules`, so it must be served over HTTP from the **project root** rather than opened as a file. For example:

```bash
npx serve .
```

Then visit `http://localhost:3000/src/` (or use the VS Code *Live Server* extension).

## Usage

1. The sidebar loads your own profile automatically.
2. Type a GitHub username in the **Search** box; after a short pause their repositories appear.
3. Click **Profile Insights** to see that user's language breakdown as pie and bar charts.
4. Click the GitHub logo or the **GitHub Insights** title to switch back to the repository grid.

## Author

**Sifeddine Yassine** · [@SifeYassine](https://github.com/SifeYassine)
