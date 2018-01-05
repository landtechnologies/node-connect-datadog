# node-connect-datadog

Datadog middleware for Connect JS / Express

## Notes on Landtech Fork
Uses `datadog-metrics` rather `node-dogstatsd`, which means you don't need to have the agent running on the server.
The two libraries do not have identical APIs, in particular we had to tweak the use of the `.histogram` function here.

## Usage

Add middleware immediately before your router.

	app.use(require("connect-datadog")({}));
	app.use(app.router);

## Options

All options are optional.

* `dogstatsd` node-dogstatsd client. `default = require('datadog-metrics')` and run `.init({})`
* `stat` *string* name for the stat. `default = "node.express.router"`
* `tags` *array* of tags to be added to the histogram. `default = []`
* `path` *boolean* include path tag. `default = false`
* `method` *boolean* include http method tag. `default = false`
* `protocol` *boolean* include protocol tag. `default = false`
* `response_code` *boolean* include http response codes. `default = false`

## License

View the [LICENSE](https://github.com/AppPress/node-connect-datadog/blob/master/LICENSE) file.

