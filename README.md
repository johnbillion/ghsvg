# GHSVG

Create an SVG of your GitHub Sponsors

## Install
```bash
npm install --save-dev ghsvg
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

### Basic configuration

- `username`: The username of the account you want the sponsors for.
- `outFile`: The output svg file.
- `range`: The dollar amount range of sponsorships you want to include.
- `monthlyTiersRange`: Specify a different range for monthly sponsorships you want to include.
- `oneTimeTiersRange`: Specify a different range for one-time sponsorships you want to include.
- `customAmountRange`: Specify a different range for custom amount sponsorships you want to include.
- `svgWidth`: The total width of the SVG (in px).
- `svgImageWidth`: The width of each image in the SVG (in px).
- `quiet`: No Output

**Note:** Since the sponsorship amount is not public, if you are creating the SVG for a user account other than yours, the ranges will have no effect and all sponsors will be included.

#### Example configurations

##### .ghsrc.json or .ghsrc.json5
```json
{
  "username": "shivammathur",
  "outFile": "sponsors.svg",
  "range": [1, 12000],
  "svgWidth": 1024,
  "svgImageWidth": 64
}
```

##### .ghsrc.js or .ghsrc.cjs
```javascript
module.exports = {
  "username": "shivammathur",
  "outFile": "sponsors.svg",
  "range": [1, 12000],
  "svgWidth": 1024,
  "svgImageWidth": 64,
};
```

##### .ghsrc or .ghsrc.yaml
```yaml
username: shivammathur
outFile: sponsors.svg
range: [1, 12000]
svgWidth: 1024
svgImageWidth: 64
```

##### .ghsrc.toml
```toml
username = "shivammathur"
outFile = "sponsors.svg"
range = [ 1, 12_000 ]
svgWidth = 1_024
svgImageWidth = 64
```

### Run

```bash
ghsvg
```

In addition to using a configuration file, you can also specify the configuration options in the CLI. To see available options:

```bash
ghsvg --help
```

## License

MIT