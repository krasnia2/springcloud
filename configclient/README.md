# configclient
- Demonstrates how to talk to the config server to get app configs
- spring.application.name=<app_name> determines what config values are pulled in
- Custom Annotations: None
- Integrates with Spring Security.

# Why
- Because we want our microservices to pull their config from a config server
 
# Steps
- Create spring boot app
- Create bootstrap.properties and configure:
	- Profile: spring.profiles.active=<profile>. 
		- Determines which profile to use to pull properties.
	- Config service uri: spring.cloud.config.uri=<config_server_uri>
		- Location of the Configuration Service
	- App name: spring.application.name=<app_name> 
		- Application name determines which properties to pull from config server
- You may still have an application.properties file. Those properties will be loaded after the boostrap.properties have been loaded.


# Testing
- Access any resource on the configclient. Verify properties have been loaded