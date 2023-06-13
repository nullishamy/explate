#  explate - the chromium extension template 

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


## Credits
https://github.com/Samic8/Hippocampus