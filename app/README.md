This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

### Requirements

The following dependencies are used for this project. Feel free to experiment using other dependencies and versions.

1. Windows 10 64-bit OS
2. nvm version 1.1.12 (for Windows)
3. NodeJS LTS v20.15.0
   - (installed using nvm)
   - node v20.15.0
   - npm 10.7.0

### Core Libraries and Frameworks

The app depends these libraries and frameworks.

1. NextJS v14.2.5
2. React v18
3. TailwindCSS v3.4.1
4. ESLint v8

## Getting Started

1. Set up the environment variables. Create a `.env` file with reference to the `.env.example` file.
   | Variable Name | Description |
   | --- | --- |
   | NEXT_PUBLIC_BASE_PATH | Root directory path name that NextJS uses for assets, media and client-side routing for the app.<br>Set its value to blank `''` when working on development mode in localhost.<br><br>Set its value to the sub-directory name where the exported NextJS app is to be deployed, i.e. `/<YOUR_REPOSITORY_NAME>` when deploying on a repository (sub-directory) of a root GitHub Pages site, i.e, on<br>`https://<YOUR_GITHUB_USERNAME>.github.io/<YOUR_REPOSITORY_NAME>` |
   | WATCHPACK_POLLING | Enables hot reload on NextJS apps running inside Docker containers on a Windows host. Set it to `true` if running Docker Desktop with WSL2 on a Windows OS. |

2. Run the app on localhost using NodeJS [Running with NodeJS](#running-with-nodejs)) or Docker ([Running with Docker](#running-with-docker))

### Running with NodeJS

1. Install dependencies.<br>
`npm install`

2. Run the development server:

   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

   You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

### Running with Docker

Run the app for local development using Docker. Navigate to the project's root directory then run:

```
# 1. Build the client and server containers for localhost development.
docker compose -f docker-compose.dev.yml build

# 2. Create and start the development client and server containers
docker compose -f docker-compose.dev.yml up

# 3. Stop and remove the development containers, networks, images and volumes
docker compose -f docker-compose.dev.yml down
```

## Available Scripts

### `npm run dev`

Starts the local NextJS app in development mode on localhost.

### `npm run build`

Builds the static site into the "out" directory.

### `npm run lint`

Checks lint errors.

### `npm run lint:fix`

Fixes lint errors.

### `npm run export`

Builds and compiles the static website exporting it into the `"out"` directory.
