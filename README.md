# Sample Svelte SPA/MicroFrontend

This is a Svelte project that compiles to a single JS file that can be published and ingested by other app-shells in a micro-frontend manner.

## Build project
`npm run build`

Rollup will bundle everything into `./public/build/itemdetail.js`
That file should then be deployed at a publicly accessbile url.

## Using the FE
To use the microfrontend on any other site:

Find the public url of the js file and include it on the page like so: `<script type="module" src="https://.../itemdetail.js"></script>`

Then, add the html file either immediately after, or dynamically: `<itemdetail-spa issueid="1234" theme="dark" baseapiurl="https://evanpayne.com" preview="true"  />`

`baseapiurl` can be left off, as can `theme`.  The other props are required.

Attribute order *does* make a difference.  It should be:
- issueid (required if `preview` is true)
- theme (optional, 'light' or 'dark')
- baseapiurl (optional)
- preview (required, 'true' or 'false)
