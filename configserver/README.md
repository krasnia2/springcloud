# configserver
- Enables HTTP access to a configuration store
- Custom Annotation: @EnableConfigServer
- Support for placeholders in URI (i.e. nested structures)
- Support for multiple profiles (i.e default, dev, qa, prod)
- File name (when storing config via file) contains the app name, and an optional proifle
- Aggregates All properties from matching files (useful for shared config and app specific config)
- Integrates with Spring Security.
- Support for Encryption/Decryption
	- Java Cryptography Extension

# Why
 - Remove settings such as feature Toggles, Connection Strings, Logging Levels from compiled code into an externaly managed configuration store.
 - Promote consistancy between same microservices as you spin-up or tear them down (i.e. all microservices read their property from one source)
 
# Steps
- Choose a config source (git, filesystem, db)
- Add configuration to config source
- Build Spring Config Project
- Secure Access to config server?

# Testing
 - URI structure
 	- /{application}/{profile}/{label}
 - Get local config for the Blue app
 	- http://localhost:8888/BLUE/default
 - Get local config for the Blue app with and property app.name
 	- http://localhost:8888/BLUE/native/app.name