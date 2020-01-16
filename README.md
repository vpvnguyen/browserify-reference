# browserify-reference
Use require in the browser

## Documentation
http://browserify.org/

## Setup
A simple example of using Browserify to bundle node modules for use in the client browser.

Initialize NPM
- `npm init -y`

Install Browserify
- `npm install -g browserify`

Install node modules
> example uses npm uniq and cron to showcase node modules running in the browser

Use node modules
- Sample below will be an npm packaged used for the front end.
- `cronJob.js`:
```javascript
const CronJob = require('cron').CronJob;
new CronJob('* * * * * *', function() {
  console.log('You will see this message every second');
}, null, true, 'America/Los_Angeles');
```

When ready for production, use Browserify to bundle NPM packages
- `browserify cronJob.js -o <new_filename.js>`
- add a new `<script>` tag in `index.html` for `<new_filename.js>`
> `<script src="cronBundle.js"></script>`



