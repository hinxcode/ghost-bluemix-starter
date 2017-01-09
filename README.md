# Ghost 0.11.3 (stable) + clearDB + cloudant

Download Bluemix CLI & Cloud Foundry CLI from [here](https://console.ng.bluemix.net/docs/starters/install_cli.html)

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
  - ghost-cleardb
  - ghost-cloudant

```
Clone a copy of **config.example.js**, then update your auth of [Mailgun](https://www.mailgun.com/) in **config.js**
```
cp config.example.js config.js
```
Sign in to [Bluemix](https://console.ng.bluemix.net), create an Organization and a Space, then open your terminal
```
bluemix login

cf create-service cleardb spark ghost-cleardb

cf create-service cloudantNoSQLDB Lite ghost-cloudant
```
Ready to deploy
```
cf push
```
