# [touchtunes](https://github.com/elyx0/touchtunes#readme) *1.0.0*

> Simple test


### src/filter.ts


#### filter(settings, components, options) 

Filters the settings list using components and keep only entries
where the requires array is emprty or has at least
one element present in the components array




##### Parameters

| Name | Type | Description |  |
| ---- | ---- | ----------- | -------- |
| settings |  | {Setting[]} | &nbsp; |
| components |  | {Component[]} | &nbsp; |
| options |  | {Object} Options | &nbsp; |
| options.omitRequires |  | Whether or not to include the requires in the response (false) | &nbsp; |




##### Returns


- `Array.&lt;Setting&gt;`  




### src/middlewares/logger.ts


#### loggerMiddleware(req, res, next) 






##### Parameters

| Name | Type | Description |  |
| ---- | ---- | ----------- | -------- |
| req |  | {Object} Express Request | &nbsp; |
| res |  | {Object} Express Response | &nbsp; |
| next |  | {Function} Callback to next middleware | &nbsp; |




##### Returns


- `Void`




*Documentation generated with [doxdox](https://github.com/neogeek/doxdox).*
