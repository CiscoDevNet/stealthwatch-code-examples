# Stealthwatch Enterprise Learning Labs Code

This is a set of sample scripts which walk users through the use of Stealthwatch's REST APIs

#### **Cognitive Intelligence Incidents API Configuration**
The Cognitive Intelligence Incidents REST API is disabled by default. To enable the API:

* Enable Cognitive Analytics in External Services on your SMC and Flow Collector(s).
* Locate `/lancope/tomcat/webapps/cta-events-collector/WEB-INF/classes/app.properties` file on your SMC system
* Under `#CTA_ENABLED` section set the `cta.api.enabled` option to `true`
* Restart web server on your SMC system: `systemctl restart lc-tomcat`

*(Note: The API returns CTA incidents for all domains and expects tenantId to be 0 in the API path parameter. Requesting data for any specific tenant will result in error.)*

For Updating CTA Postman to only show Dusti.hilton, add the following to pre-request JavaScript functionality:
```
var url = request.url;
pm.request.url = url + "?ipAddress=10.201.3.154";
```
