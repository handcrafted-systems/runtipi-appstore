# Apprise API

Take advantage of [Apprise](https://github.com/caronc/apprise) through your network with a user-friendly API.

- Send notifications to more than 100+ services.
- An incredibly lightweight gateway to Apprise.
- A production ready micro-service at your disposal.
- A Simple Website to verify and test your configuration with.

Apprise API was designed to easily fit into existing (and new) eco-systems that are looking for a simple notification solution.

## Apprise URLs

📣 In order to trigger a notification, you first need to define one or more [Apprise URLs](https://github.com/caronc/apprise/wiki) to support the services you wish to leverage. Visit <https://github.com/caronc/apprise/wiki> to see the ever-growing list of the services supported today.

## Screenshots

There is a small built-in *Configuration Manager* that can be optionally accessed through your web browser allowing you to create and save as many configurations as you'd like. Each configuration is differentiated by a unique `{KEY}` that you decide on:<br/>
![Screenshot of GUI - Using Keys](https://raw.githubusercontent.com/caronc/apprise-api/master/Screenshot-1.png)<br/>

Below is a screenshot of how you can assign your Apprise URLs to your `{KEY}`. You can define both TEXT or YAML [Apprise configurations](https://github.com/caronc/apprise/wiki/config).<br/>
![Screenshot of GUI - Configuration](https://raw.githubusercontent.com/caronc/apprise-api/master/Screenshot-2.png)

Below is a screenshot of the review tab where you can preview what Apprise URL(s) got loaded from your defined configuration. It also allows you to view the tags associated with them (if any). Should you chose to send a test notification via this API, you can select the tags in advance you wish to target from here.<br/>
![Screenshot of GUI - Review](https://raw.githubusercontent.com/caronc/apprise-api/master/Screenshot-3.png)

With configuration in place, you'll be able to use the *Notification* tab to send a test message to one or more of the services you defined in your configuration. You can also select from the tags (if any) you pre-assigned to your URLs defined. If you did not define any tags with you configured URLs, then you do not need to identify any here. You can use the tag `all` to notify all of your services regardless of what tag had otherwise been assigned to them (if any at all).<br/>
![Screenshot of GUI - Notifications](https://raw.githubusercontent.com/caronc/apprise-api/master/Screenshot-4.png)

At the end of the day, the GUI just simply offers a user friendly interface to the same API developers can directly interface with if they wish to.