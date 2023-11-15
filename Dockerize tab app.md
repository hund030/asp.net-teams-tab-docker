1. Teams Toolkit -> Prepare dependencies.
1. Right-click project and add docker support.
1. Update Properties/launchSettings.json. Update launchUrl in Docker profile, add sslPort and httpPort properties to map ports.
	
	```json
	"Docker": {
		"commandName": "Docker",
		"launchBrowser": true,
		"launchUrl": "https://teams.microsoft.com/l/app/00b4853f-4c0b-40da-b115-f8b3fbc5fda4?installAppPackage=true&webjoin=true&appTenantId=72f988bf-86f1-41af-91ab-2d7cd011db47&login_hint=zhihuan@microsoft.com",
		"environmentVariables": {
			"ASPNETCORE_URLS": "https://+:443;http://+80"
		},
		"publishAllPorts": true,
		"useSSL": true,
		"sslPort": 44302,
		"httpPort":  2544
	}
	```
1. F5 to debug, browser should be launched and teams tab app works.

* Environment variables are set in appsettings.Development.json file.
* Breaking points work.
* Hot reload does not work.