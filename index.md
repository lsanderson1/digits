<img src="doc/landing.png">

Digits is an application that allows users to:

  * Register an account
  * Create and manage a set of contacts.
  * Add Timestamped notes in regards to each contact.

## Installation

First, [install Meteor](https://www.meteor.com/install).

Second, [download a copy of Digits](https://github.com/lsanderson1/digits). Note that Digits is a private repo and needs permission to access it.

Third, cd into the app/ directory of your local copy of the repo, and install third party libraries with:

```
$ meteor npm install
```

## Running the system

Once the libraries are installed, you can run the application by invoking the "start" script in the [package.json file](https://github.com/ics-software-engineering/meteor-application-template-react/blob/master/app/package.json):

```
$ meteor npm run start
```

The first time you run the app, it will create some default users and data. Here is the output:

```
 meteor npm run start 

> meteor-application-template-react@ start C:\Users\llsan\OneDrive\Documents\GitHub\digits\app>meteor npm run start
> meteor --no-release-check --exclude-archs web.browser.legacy,web.cordova --settings ../config/settings.development.json

[[[[[ ~/GitHub/ICS314/meteor-application-template-react/app ]]]]]

=> Started proxy.                             
=> Started HMR server.                        
=> Started MongoDB.                           
I20220529-12:09:18.384(-10)? Creating the default user(s)
I20220529-12:09:18.389(-10)?   Creating user admin@foo.com.
I20220529-12:09:18.453(-10)?   Creating user john@foo.com.
I20220529-12:09:18.515(-10)? Creating default data.
I20231106-20:54:25.017(-10)? Creating the default user(s)
I20231106-20:54:25.212(-10)?   Creating user admin@foo.com.
I20231106-20:54:25.356(-10)?   Creating user john@foo.com.
I20231106-20:54:25.520(-10)? Creating default contacts.
I20231106-20:54:25.522(-10)?  Adding Johnson (john@foo.com)
I20231106-20:54:25.556(-10)?  Adding Casanova (john@foo.com)
I20231106-20:54:25.560(-10)?  Adding Binsted (admin@foo.com)
=> Started your app.

=> App running at: http://localhost:3000/
```

Periodically, you might see `Error starting Mongo (2 tries left): Cannot run replSetReconfig because the node is currently updating its configuration` after the `=> Started HMR server.`. It doesn't seem to be a problem since the MongoDB does start.

### Viewing the running app

If all goes well, the template application will appear at [http://localhost:3000](http://localhost:3000).  You can login using the credentials in [settings.development.json](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/config/settings.development.json), or else register a new account.

### ESLint

You can verify that the code obeys our coding standards by running ESLint over the code in the imports/ directory with:

```
meteor npm run lint
```

## User Interface Walkthrough

#### Landing page

When you retrieve the app at http://localhost:3000, this is what should be displayed:

<img src="doc/landing.png">

The next step is to use the Login menu to either Login to an existing account or register a new account.

#### Login page

Clicking on the Login link, then on the Sign In menu item displays this page:

<img src="doc/login.png">

#### Register page

Alternatively, clicking on the Login link, then on the Register menu item displays this page:

<img src="doc/register.png">


#### Landing (after Login) page, non-Admin user

Once you log in (either to an existing account or by creating a new one), the navbar changes as follows:

<img src="doc/johnfoolanding.png">

You can now add new Contacts documents, and list the Contacts you have created. Note you cannot see any Stuff created by other users.

#### Add Contacts page

After logging in, here is the page that allows you to add new Contacts:

<img src="doc/addcontact.png">

#### List Contacts page

After logging in, here is the page that allows you to list all the Contacts you have created:

<img src="doc/listcontact.png">

You click the "Edit" link to go to the Edit Stuff page, shown next.

#### Edit Contact page

After clicking on the "Edit" link associated with an item, this page displays that allows you to change and save any existing contacts.

<img src="editcontact.png">

#### Landing (after Login), Admin user

You can define an "admin" user in the settings.json file. This user, after logging in, gets a special entry in the navbar:

<img src="doc/adminlanding.png">

#### Admin page (list all users contacts)

To provide a simple example of a "super power" for Admin users, the Admin page lists all of the Contacts by all of the users:

<img src="doc/adminusers.png">

Note that non-admin users cannot get to this page, even if they type in the URL by hand.
