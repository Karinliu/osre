# Osre
[Osre](https://osremarketsuite.nl/) asked me to build a small website with a number of requirements:
* Use the framework [Vue.js](https://vuejs.org/)
* Use the SpaceX V4 api and use the [launch](https://api.spacexdata.com/v4/launches) api and the [rocket](https://api.spacexdata.com/v4/rockets) api.
* Use components


## API
The [launch](https://api.spacexdata.com/v4/launches) Api holds the information about the name of the launch, flight number and the youtube or wikipedia page about the launch.

The [rocket](https://api.spacexdata.com/v4/rockets) Api holds the information about the rocket.


## The pages
The website contains 3 main pages, namely:
* A Home page which consist of the upcoming launches.
* Launch page about the launches that where successful on the top of the page. And the launches where unsuccessful on the bottom of the page.
* Rockets page with content about the active rockets. With a shortcut to the retired rockets.

When a user goes to a page that does not exist, than they land on a 404 error page.

## Download my VueJS application

```bash
# Git clone
git clone https://github.com/Karinliu/osre.git

# cd to map
cd ./SpaceX

# install dependencies
$ npm install 

# serve with hot reload at localhost:3000
$ npm run dev
```