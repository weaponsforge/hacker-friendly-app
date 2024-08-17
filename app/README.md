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

1. Install dependencies.<br>
`npm install`

2. Set up the environment variables. Create a `.env` file with reference to the `.env.example` file.
   | Variable Name | Description |
   | --- | --- |
   | NEXT_PUBLIC_BASE_PATH | Root directory path name that NextJS uses for assets, media and client-side routing for the app.<br>Set its value to blank `''` when working on development mode in localhost.<br><br>Set its value to the sub-directory name where the exported NextJS app is to be deployed, i.e. `/<YOUR_REPOSITORY_NAME>` when deploying on a repository (sub-directory) of a root GitHub Pages site, i.e, on<br>`https://<YOUR_GITHUB_USERNAME>.github.io/<YOUR_REPOSITORY_NAME>` |

2. Run the development server:

   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

   You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

## Available Scripts

### `npm run dev`

Starts the local NextJS app in development mode on localhost.

### `npm run build`

Builds the static site into the "out" directory.

### `npm run lint`

Checks lint errors.

### `npm run lint:fix`

Fixes lint errors.



