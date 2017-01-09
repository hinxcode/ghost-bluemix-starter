# Ghost 0.11.3 (stable) + clearDB + cloudant

1. Replace with your custom name `Name` & `Host` on **manifest.yml**, the example below:
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

2. Clone a copy of **config.example.js**, then update your auth of [Mailgun](https://www.mailgun.com/) in **config.js**
```
cp config.example.js config.js
```

3. Sign in, then create an Organization and a Space on [Bluemix](https://console.ng.bluemix.net)
4. Using CLI for deploying, Download them from [here](https://console.ng.bluemix.net/docs/starters/install_cli.html)

5. Open your terminal and connect to bluemix
```
bluemix login
```

6. Ready to deploy
```
cf push
```
