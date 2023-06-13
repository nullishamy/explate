#  explate

## Getting started
```bash
git clone https://github.com/nullishamy/explate my-extension # Clone the repository
cd my-extension                                              # Change into the directory
npm i                                                        # Install dependencies
npm run dev                                                  # Run the dev server
```

## The tools
Explate uses parcel (v2!) and its ecoystem as the compiler, bundler, transformer, and optimiser.
it uses the web extension defaults, in combination with some additional config, to provide the following
toolset by default:
- TypeScript
- TailwindCSS
- PostCSS

You can extend the toolset, or remove components you do not want, through the rc/plugin system:

Explate declares a parcelrc, which you can add additional parcel stages on to. See [the docs for this](https://parceljs.org/features/plugins/) and their [plugin browser](https://parceljs.org/plugin-browser/) which allows you to search for parcel plugins to add to the project.

To add a plugin, install the npm package, and follow their instructions for enabling it in the parcelrc file.

Parcel will compile the manifest file (rewriting relevant parts for hot reloading in the development environment) so that you get the full toolset with minimal manual configuration.

Parcel cannot yet bundle the `options_page` (see [the open issue](https://github.com/parcel-bundler/parcel/issues/9090)), so you will not be able to use tailwind, etc inside it.

## Adding a framework

You can add a framework to the template by following Parcel's guide, the steps below will show you how to add React.

Follwing [the React guide](https://parceljs.org/recipes/react/), we will first install React.
```bash
npm i react react-dom
```

(and the types, if you kept TypeScript)
```bash
npm i -D @types/react @types/react-dom
```

Then, add the initialisation boilerplate to our main file (entry.ts by default)
```jsx
import { createRoot } from "react-dom/client";
import { App } from "./App";

const container = document.getElementById("app");
const root = createRoot(container)
root.render(<App />);
```

Finally, make our JSX
```jsx
export function App() {
  return <h1>Hello world!</h1>;
}
```

## Credits
https://github.com/Samic8/Hippocampus