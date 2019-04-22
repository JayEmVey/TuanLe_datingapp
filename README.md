# TuanLe_datingapp

**Project structure**
- cms: Strapi
- blog: Gatsby
- mobile: TBD

# Installation guide
## CMS Backend
**Please note that Strapi may work on other Operating Systems, but are not tested at this time.**
Node:
- NodeJS >= 10.x
- NPM >= 6.x

**Please note that right now Node 11 is not supported, and the current Node LTS (v10) should be used.**
Database:
- MongoDB >= 3.6
- MySQL >= 5.6
- MariaDB >= 10.1
- PostgreSQL >= 10

1. Clone project: `git clone https://github.com/JayEmVey/TuanLe_datingapp.git`
2. Install dependencies:
* [Download and install MondgoDB](https://docs.mongodb.com/v3.2/administration/install-community/)
* Install Strapi `npm install strapi@alpha -g`
* Install npm packages: `cd cms && npm install`
3. Start server: `strapi start`

Server is up and ready to serve!

**Configuration files:**
*Development*
Database connection:
> api/config/environments/development/database.json
Server connection:
> api/config/environments/development/server.json

## Blog Frontend
1. Install Gatsby CLI: `cd blog && npm install --global gatsby-cli`
2. Install npm packages: `npm install`
3. Start for development: `gatsby develop`

**Configuration files:**
> gatsby-config.js

# Reference: [Building a static website using gatsby and strapi](https://blog.strapi.io/building-a-static-website-using-gatsby-and-strapi/)
