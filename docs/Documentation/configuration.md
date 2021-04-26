
## Configuration


* Api.defaultVersion - keep default api version (used if route does not contain version).
* Api.useVersioning - enable versions support. Numeric.
* Api.versionPrefix - by default version in routes is /v\d+/

 Api.ServiceFallback - if defined class name service will be loaded using this fallback class if service does not exist.

 
## Services configuration

Any service that is loaded as a fallback service or specific service that is possible to setup using configuration file.

In the config/api.php in Api.Service section, you can define service options.

Lets consider how one can configure options for `ArticlesService`.

Configuration are hierarchical in the next sense: 

* one can define default options for any service in the application in the `Api.Service.default.options` section.
* one can define options for any service in the application in the `Api.Service.articles.options` section.

Now lets consider a case where we have service with defined version number 2. In this case there are many ways to configure service supported. For example:

* one can define default options for any service in the application in the `Api.Service.default.options` section.
* one can define default options for any service for defined version, and in this case you will use the `Api.Service.v2.default.options` section.
* one can define options for a specific (`articles`) service for defined version in the application in the `Api.Service.v2.articles.options` section.


All defined options are overridden from up to down in described order.
This allows for common service settings, and the aility overwrite then in bottom level.


 * Api.Service.classMap - defines name map, which allows for defining services action classes with custom location logic.

## Actions configuration

Any action that could be loaded as a default action defined in fallback class, or specific action class, can be 
configured using configuration file.

Lets consider how one can configure options for `IndexAction` of `ArticlesService`.

Configuration are hierarchical in the next sense: 

* one can define default options for any action for all services within the application in the `Api.Service.default.Action.default` section.
* one can define default options for `index` action for all services within the application in the `Api.Service.default.Action.index` section.
* one can define options for any action in a specific (`articles`) service in the `Api.Service.articles.Action.default` section.
* one can define options for `index` action in a specific (`articles`) service in the `Api.Service.articles.Action.index` section.

Now lets consider a case where we have service with defined version number 1. In this case, there are more ways to configure action supported:

* one can define default options for any action for all services in the application in the `Api.Service.default.Action.default` section.
* one can define default options for `index` action for all services within the application in the `Api.Service.default.Action.index` section.
* one can define default options for any action for all services for defined version of the application in the `Api.Service.v1.default.Action.default` section.
* one can define default options for `index` action for all services for defined version of the application in the `Api.Service.v1.default.Action.index` section.
* one can define options for any action in the specific (`articles`) service for defined version in the `Api.Service.v1.articles.Action.index` section.
* one can define options for `index` action in the specific (`articles`) service for defined version in the `Api.Service.articles.Action.index` section.


All defined options are merged from up to down in described order.
This allows for configuration of shared behavior for all actions, or for specific subset of actions provided by the services.

## Auth configuration

See it in auth.md

