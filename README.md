# Cloudflare DDNS client
This Node-application will check your current public IP address and update the A-record of the specified domain in Cloudflare DNS.

## Setup
First make sure you have node installed.

Then:
1. Copy `config-example.json` to `config.json`
2. Configure API key, zones and DNS records
3. Run `npm run start`, or `npm run dev`

There is also an option `--forceUpdate` which will ignore the current DNS settings and submit the update to Cloudflare anyways.
This is only possibly by running the script directly with node, like this: `node ./src/index.js --forceUpdate`. You might need to change file permissions for this to work (`chmod +x ./src/index.js`).

To run this script automatically you can add it to your crontab. My setup looks like this and runs every 5 minute:
`*/5 * * * * /usr/bin/env node /path/to/your/code/src/index.js > /dev/null 2>&1`

Use [crontab.guru](https://crontab.guru/) to find a different interval.