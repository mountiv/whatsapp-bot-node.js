# WhatsApp ChatBot with Node.js ©

[![PRETTIER](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://gitter.im/jlongster/prettie)
[![LICENSE](https://img.shields.io/github/license/arshadkazmi42/awesome-github-init.svg)](https://github.com/arshadkazmi42/awesome-github-init/LICENSE)
[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Flucioerlan%2FWhatsapp-Chatbot&count_bg=%23E71A18&title_bg=%23555555&icon=dependabot.svg&icon_color=%23E7E7E7&title=views&edge_flat=false)](https://hits.seeyoufarm.com)

![giff-wats](https://user-images.githubusercontent.com/67064886/90330135-d3c60780-df80-11ea-838c-f49bf15458b8.gif)

<br>

# Description 

This service communicates with whatsapp web, using the puppeteer. This bot is inspired by 99% of the bots I see out there on the internet, from e-commerces

 Credits to the author of the library [PEDRO](https://github.com/pedroslopez)  
 <br>
Special thanks for the structure [CAIO](https://github.com/caioagiani)
<br><br>


## 1 - API

The api has nothing to do with the service, the only thing it does is to communicate with the postgres database, I decided to post it too.

### Create table into Postgres

**/ChatBot-WhatsApp/api** 
```sh
$ npx knex migrate:latest
```
<br>



### Insert data into Postgres

**/ChatBot-WhatsApp/api** 
```sh
$ npx knex seed:run
```
<br>


### Sample request using CURL in the command line/terminal:

**/ChatBot-WhatsApp/api** 
```
curl http://localhost:4001/api/user/38581407838 | python3 -m json.tool
```
<br>


### Access the documentation for all methods in the swagger

 http://localhost:4001/api/docs
<br>


## 1 - SERVICE

Scan QRCODE

![2020-08-15_20-26](https://user-images.githubusercontent.com/67064886/90330116-c27cfb00-df80-11ea-8c57-0409cccd15dc.png)


Attention you need to do this, right after running npm install in the Service folder, open service/node_modules/whatsapp-web.js/src/Client.js and add these lines

**LINE 43**  
```
 this.lastMessage = null;
```

**LINE 441 up until 443** 
```
    setPrevMessage(status){
        this.lastMessage = status;
    }
```
<br>

This function is for the puppeteer to go back and forth between pages.



# Installations

### Requirements

You will need to install some stuff, if they are not yet installed in your machine:

* [Node.js (v4.3.2 or higher; LTS)](http://nodejs.org)
* [NPM (v3.5+; bundled with node.js installation package)](https://docs.npmjs.com/getting-started/installing-node#updating-npm)
<br>

---

### Install through Github

**After cloning**

```bash
$ cd ChatBot-WhatsApp
```

**Install all of the projects dependencies with:**

```bash
$ npm install

```

**Copy the .env-examples file to .env**

```
$ cp .env-examples .env
```

**Running**

```bash
$ npm start

```
<br>


---

### Running with Docker

```
$ docker-compose up
```
<br>


