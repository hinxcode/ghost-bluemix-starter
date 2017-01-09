# Ghost 0.11.3 (stable) + clearDB + cloudant

## Step by Step
Replace with your custom name `Name` & `Host` on **manifest.yml**, the example below:
```
---
applications:
- name: my-ghost-blog
  host: my-ghost-blog
  domain: mybluemix.net
  memory: 512M
  instances: 1
  path: .
  command: node index --production
  env:
    NODE_ENV: production
  services:
  - cleardb
  - cloudant
```
Clone a copy of **config.example.js**, then update your auth of [Mailgun](https://www.mailgun.com/) in **config.js**
```
cp config.example.js config.js
```
Sign in to [Bluemix](https://console.ng.bluemix.net), then create an Organization and a Space

Open your terminal and connect to bluemix, you can download CLI from [here](https://console.ng.bluemix.net/docs/starters/install_cli.html)
```
bluemix login
```
Ready to deploy
```
cf push
```
