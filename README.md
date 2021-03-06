# Sigfox Platform

## About this project

This project is a cloud platform to manage and visualize Sigfox devices and messages. It was modified to include the support of Sigfox Data advanced callbacks.

## Get started

### [Demo](https://sigfox-platform.thenorthweb.com)

### Try it now with [Heroku](https://heroku.com)

Deploy an instance on your Heroku account to play around with it!

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

An alternative way to get it running at Heroku is to install the [Heroku Toolbelt](https://toolbelt.heroku.com) and follow these steps:

```
git clone https://github.com/guy-noel/herokuv4.git my-project
cd my-project
heroku apps:create my-project
git push heroku master
```

If you are not familiar with Heroku, just create an account an follow the procedure:

1. **Create a new app:**

![create app](doc/img/deploy-1.png)

2. **Build & deploy app (5 to 10min):**

![build app](doc/img/deploy-2.png)

3. ** Link the application with a MongoDB MLab database (Free):**

*Note that if you don't link a database to your application, all the data will be erased every time the application restarts.*

* Go to [https://mlab.com](https://mlab.com/login/) and create an account and login.

* Create a new MongoDB cluster:

![plan-region](doc/img/plan-region.PNG)

Wait for the cluster to be created (1 to 3 minutes)

* Create database user in SECURITY>Database Access

![user](doc/img/user.PNG)

* White list IP range in SECURITY>Network Access:

![whistlist](doc/img/whitelist.PNG)

* Create database in COLLECTIONS>ADD YOUR OWN DATA

![DB](doc/img/DB.PNG)

* Copy your MongoDB URI in CONNECT>CONNECT APPLICATION :

![URI](doc/img/URI.PNG)

* Go back to your Heroku Dashboard and go to the Settings tab:

![heroku-show-env-variables](doc/img/heroku-show-env-variables.png)

* Click on Reveal Config Vars and add your MongoDB URI:

![heroku-add-MONGODB_URI](doc/img/heroku-add-MONGODB_URI.png)

**You may also add the variable SECRET with a password of your choice. This SECRET will be used to cypher all the connector passwords you add in the application.**

* Restart all dynos:

![heroku-restart-dynos](doc/img/heroku-restart-dynos.png)


### User guide

- Open app and register:

![login](doc/img/login.png)

![register](doc/img/register.png)

Note that, the first user to register will be granted an admin role.
The other users to register will be granted user roles.


## Development

This project uses Loopback 3, Angular 4, Fireloop and MongoDB.

### Requirements

### API (To Be Updated, below is an old version)

Below is the functional/sequential diagram representing the message journey.

![message_journey](doc/img/message-journey.png)

### Webapp

#### Color code

| GPS | Sigfox | WiFi | BLE |
| :-------: | :-------: | :-------:	| :-------: |
| ![#9B7A48](https://placehold.it/15/9B7A48/000000?text=+) `#9B7A48` | ![#792FAA](https://placehold.it/15/792FAA/000000?text=+) `#792FAA` | ![#2F2A30](https://placehold.it/15/2f2A30/000000?text=+) `#2F2A30` | ![#3C58CE](https://placehold.it/15/3C58CE/000000?text=+) `#3C58CE` |

#### Developers

##### Linking a Sigfox device to the platform

Once the application is deployed, head over to the 'connectors'. You will need to create a developer access token in order to secure the API calls. You can then copy & paste the callback information you need in the device type new callback onto the [Sigfox Backend](https://backend.sigfox.com/).

##### Adding a custom parser

A short wiki can be found [here](https://github.com/IoT-Makers/sigfox-platform/wiki/Adding-a-custom-parser).

## Roadmap


## Authors

* [Antoine de Chassey](https://github.com/AntoinedeChassey)
* [Louis Moreau](https://github.com/luisomoreau)

## Contributors

Feel free to submit a Pull Request and don't forget to add you name and your useful links ;)

> Made with &nbsp;:heart:&nbsp; by Antoine de Chassey & Louis Moreau
> Slightly updated by Guillaume Noel
