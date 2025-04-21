# GHSVG

Create an SVG of your GitHub Sponsors

<a href="https://github.com/sponsors/johnbillion"><img src="https://cdn.jsdelivr.net/gh/johnbillion/johnbillion@latest/sponsors.svg" alt="Sponsor johnbillion"></a>

## Install
```bash
npm install --save-dev @johnbillion/ghsvg
```

## Configure

- Create a `.env` file if you don't already have one in your project, and set the `GITHUB_TOKEN` in it.
```dotenv
GITHUB_TOKEN=ghp_xxx
```

- Create a configuration file.

Configuration file can be 
  - A `.ghsrc` file written in JSON or YAML.
  - A `.ghsrc.json`, `.ghsrc.yml`, `.ghsrc.yaml`, or `.ghsrc.json5` file.
  - A `.ghsrc.js`, `.ghsrc.cjs` or `.ghsrc.mjs` file that exports an object.
  - A `.ghsrc.toml` file.

### Configuration

#### Required

- `username`: The GitHub user or organization for fetching the sponsors.

#### Optional

- `outFile`: The output SVG file.
- `otherSponsors`: A newline separated file with sponsors from sources other than GitHub Sponsors.
- `range`: The dollar amount range of sponsorships you want to include.
- `monthlyTiersRange`: Specify a different range for monthly sponsorships you want to include.
- `oneTimeTiersRange`: Specify a different range for one-time sponsorships you want to include.
- `customAmountRange`: Specify a different range for custom amount sponsorships you want to include.
- `svgWidth`: The total width of the SVG (in px).
- `svgImageWidth`: The width of each image in the SVG (in px).
- `svgImageSpace`: The space between each image in the SVG (in px).
- `quiet`: No Output

**Note:** Since the sponsorship amount is not public, if you are creating the SVG for an account other than yours, the ranges will have no effect and all sponsors will be included.

#### Example configurations

##### .ghsrc.json or .ghsrc.json5
```json
{
  "username": "johnbillion",
  "outFile": "sponsors.svg",
  "range": [1, 12000],
  "svgWidth": 1024,
  "svgImageWidth": 64
}
```

##### .ghsrc.js or .ghsrc.cjs
```javascript
module.exports = {
  "username": "johnbillion",
  "outFile": "sponsors.svg",
  "range": [1, 12000],
  "svgWidth": 1024,
  "svgImageWidth": 64,
};
```

##### .ghsrc or .ghsrc.yaml
```yaml
username: johnbillion
outFile: sponsors.svg
range: [1, 12000]
svgWidth: 1024
svgImageWidth: 64
```

##### .ghsrc.toml
```toml
username = "johnbillion"
outFile = "sponsors.svg"
range = [ 1, 12_000 ]
svgWidth = 1_024
svgImageWidth = 64
```

### Run

```bash
npx ghsvg
```

In addition to using a configuration file, you can also specify the configuration options in the CLI. To see available options:

```bash
npx ghsvg --help
```

## History

This package originated as a fork of [GHSVG by Shivam Mathur](https://github.com/shivammathur/ghsvg). Thanks Shivam!

## License

[MIT](LICENSE)
