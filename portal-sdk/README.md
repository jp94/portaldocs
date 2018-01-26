# Azure portal extension documentation
This is the home page for all documentation related to onboarding, developing, operating, and anything else to do with owning an Azure portal extension.
Couldn't find what you needed? [Ask about the docs on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-missing-docs).
## Onboarding a new extension
* [Overview / Getting Started](./generated/top-onboarding.md)
* [Steps that do not involve the Ibiza team (e.g. compliance, marketplace integration)](top-external-onboarding.md)
* [Manage cloud/environment specific configuration](./generated/top-extensions-configuration.md)
* [Exit criteria](./generated/top-exit-criteria.md)
Kickoff the onboarding experience by sending mail to __ibiza-onboading-kick@microsoft.com__.
## Azure portal architecture
Learn how the framework is structured and how it is designed to run in multiple clouds / environments.
* [Architecture overview](http://top-level/architecture.md)
## What's new
* [No-PDL Blades and Parts](http://top-whats-new#no-pdl.md) - *Reduces the number of files and concepts to build UI*
* [Forms without edit scope](http://top-forms.md) - *More intuitive APIs for building forms*
* [Editable Grid V2](http://top-level/editable-grid.md) - *Improved APIs designed to work with new forms*
* [Extension Availability Alerts](http://top-level/availibility-alerts.md) - *Get notified if your extension goes down*
* [Actionable Notifications](http://top-level/availibility-alerts.md) - *Point users to well known next steps*
* [EV2 support for the Extension Hosting Service](http://top-level/hosting-service#ev2.md) - *Nuff said*
* [Multi-Column for Essentials Controls]() - *Better use of screen real estate*
* [TreeView improvements]() - *Checkboxes, commands, and Load More / Virtualization*

## Development guide
Azure portal extension development is supported on the Microsoft Windows 8, Windows Server 2012 R2, and Windows 10.
1. Install the SDK(top-extensions-install-software.md)
* [How to use the MSI Installer](downloads.md)
* [How to update portal Nuget packages](./generated/top-portalfx-extensions-nuget.md)
2. Configure your IDE - *Typescript version / Compile on save*
* [Visual Studio](portalfx-ide-setup.md) *(with Extension project template)*
* [VS Code]()
[Ask an sdk setup question on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-sdkupdate)
## Developing your user interface UI
The next few sections walk through the different types of UI that can be built using the framework. There are [Samples](http://needslink) that show how to do many common development tasks. 
### Blades
The primary UI building block is a called a blade. A blade is like a page. It generally takes up the full screen, has a presence in the portal breadcrumb, and has an 'X' button to close it.
[Developing blades](portalfx-blades.md#blades)
[Ask a question about blades on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-blades-parts)
### Parts
If you want your experience to have a presence on Azure dashboards then you will want to build parts (a.k.a. tiles).
[Developing parts](portalfx-blades.md#blades)
[Ask a question about parts on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-blades-parts)
### Building UI with HTML templates and Fx controls
Any template based UI in the portal (e.g. [template blades]() or [template parts]()) can make use of a rich controls library maintained by the Ibiza team.
* [Controls overview](portalfx-controls.md)
* [Controls playground]()
[Ask a controls related question on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-controls)
### Styling and Theming
When using HTML and framework controls you have some control over styling. These documents walk through the relevant topics.
* [CSS Style sanitization]()
* [Adding Custom CSS]()
* [Layout classes]()
* [Typography]()
* [Iconography]()
* [Theming]()
### Forms
Many experiences require the user to fill out a form. The Ibiza controls library provides support for forms. It also provides a TypeScript based section model that lets you build your form in code without expressing all the fields in an html template.
* [Developing forms](./generated/portalfx-forms.md)
[Ask a forms related question on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-forms)
### Common scenarios and integration points
* [Blades that __create__ or provision resources and services](portalfx-create.md)
* [Adding your resource or service into the __browse__ menu]()
* [Common UX for Azure Resource Manager (ARM) based services]()
[Ask about browse integration on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-browse)
[Ask about create scenarios on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-create)
### Other UI concepts
* [Context panes]()
* [Dialogs]()
* [Notifications]()
* [Blade opening and communication between blades]()
### Loading and managing data
Since your extension is just web code, you can make AJAX calls to various backend services to load data into your UI. The framework provides a data library you can use to manage this data.
* [Making authenticated calls to Azure Resource Manager (ARM)](portalfx-data.md#making-authenticated-ajax-calls)
* [Data Context, data views, and data caches](portalfx-data.md)
* [Auto-refreshing client data](portalfx-data-refreshingdata.md#auto-refreshing-client-side-data-aka-polling)
* [Shaping and filtering data](portalfx-data-projections.md) 
* [Adressing Data Merge Failures](portalfx-data.md#data-merging)
* [Legacy accessing C# model objects](portalfx-data-typemetadata.md#type-metadata)
* [Legacy Data Atomization](portalfx-data-atomization.md#data-atomization)
[Ask about data management on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-data-caching)

### Advanced development topics
* [Memory management]()
* [Custom domains (e.g. aad.portal.azure.com)]()
* [Sharing blades and parts across extensions]()
## Debugging
* [Using developer mode]()
* [Debugging extension load failures]()
* [Debugging console errors]()
* [Debugging javascript](https://github.com/Azure/portaldocs/blob/master/portal-sdk/generated/portalfx-debugging.md#debugging-javascript)
* [Debugging knockout](https://github.com/Azure/portaldocs/blob/master/portal-sdk/generated/portalfx-debugging.md#debugging-knockout)
* [Debugging the data stack](https://github.com/Azure/portaldocs/blob/master/portal-sdk/generated/portalfx-debugging.md#debugging-the-data-stack)
## Testing
The Ibiza team provides limited testing support. Due to resource constraints the C# and Node.js framework is open source. This is so that partners can unblock themselves in case the Ibiza team cannot make requested improvements as quickly as you might expect.
* [Unit testing support]()
* [C# Test Framework (Open source)]()
* [Node.js Test Framework (Open source)]()
[Ask a test related question on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-test)
## Telemetry and alerting
The Ibiza team collects standard telemetry for __generic actions__ like blade opening and commmand execution. It also collects __performance__, __reliability__, and __user feedback__ information that facilitate the operation of your extension. You can also write your own events via the telemetry system. Ibiza supports alerting for common operations scenarios.
* [Portal telemetry overview]()
* [Getting access to raw portal telemetry data]()
* [Consuming telemetry via pre-build Power BI Dashboards]()
* [Performance and reliability monitoring / alerting]()
* [Collecting feedback from your users]()
* [Set up and verify telemetry logging from your extension]()
[Ask about telemetry on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-telemetry)
[Ask about performance and reliability on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-performance)
## Localization / Globalization
The Azure portal supports multiple languages and locales. You will need to localize your content.
* [Localization overview and supported languages](https://github.com/Azure/portaldocs/blob/master/portal-sdk/generated/portalfx-localization.md#understanding-localization)
* [Setting up Localization for your extension]()
* [Setting up Localization for your gallery package]()
* [Testing locaization with side-loading]()
* [Formatting numbers, currencies and dates](https://github.com/Azure/portaldocs/blob/master/portal-sdk/generated/portalfx-globalization.md#globalization-api)
[Ask about localization / globalization on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-localization-global)
## Accessibility
The Azure portal strives to meet high accessibility standards to ensure the product is accessible to to users of all levels of ability. There is regular testing and a process with SLAs for getting issues addressed quickly.
* [Accessibility guidelines]()
* [Accessibility testing and SLAs]()
[Ask about accessibility on stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-accesibility)
## Deploying your extension
Learn how to deploy your extension to the various clouds and environments.
* [Extension registration, environments (e.g. dogfood, prod), clouds (e.g. Mooncake, BlackForest, Fairfax) and Ibiza team SLAs]()
* [Understanding the journy from private preview to public preview to GA](./generated/portalfx-extensions-developmentPhases.md)
[Ask a deployment question on Stackoverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-deployment)
### Deployment using the Ibiza hosting service
The Ibiza team provides and operates a common extension hosting service that makes it easy to get your bits into a globally distributed system without having to manage your own infrastructure.
* [Hosting service overview](portalfx-extension-hosting-service.md)
* [Onboarding your extension to hosting service]()
* [Validating extension registeration with hosting service]()
* [Versioning your extension](portalfx-extension-versioning.md)
* [Deploying your extension using Express V2 + Hosting Service]()
* [SLA for registering extension with hosting service]()
### Custom extension deployment infrastructure
You should strive to use the Ibiza hosting service. If for some reason this is not possible then [learn how to build a custom extension deployment infrastructure]().
## Upgrading the Ibiza SDK
Extensions are required to be running a version of the Ibiza SDK that has been published withing the past 4 months. 
* [Upgrade policy and alerts](portalfx-deploy.md#3-understand-extension-runtime-compatibility)
* [Upgrading Ibiza NuGet packages](./generated/top-portalfx-extensions-nuget.md)
* [Updating the C# test framework]()
* [Updating the msportalfx-test framework]()

## Legacy features
These features are supported, but have had no recent investment. No additional investment is planned. There are modern capabilities that should be used instead if you are developing new features.
* [PDL based blades and parts]()
* [Controls in the msportalfx namespace]()
* [EditScope](./generated/portalfx-legacy-editscopes.md)
## Frequently asked questions
* TBD
*
*
*