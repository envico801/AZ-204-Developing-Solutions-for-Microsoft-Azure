# MADSF - Az 204 developing solutions for microsoft azure - microsoft learn

## Questions

### Part I - Implement Azure App Service web apps

#### Chapter 1 - Explore Azure App Service

Q:: What is Azure App Service primarily used for?
A:: Azure App Service is primarily used for hosting web applications, REST APIs, and mobile back ends.
Q:: How does Azure App Service facilitate scaling?
A:: Azure App Service facilitates scaling by providing built-in auto scale support. This includes scaling up/down resources such as the number of cores or amount of RAM, as well as scaling out/in by increasing or decreasing the number of machine instances running the web app.
Q:: Explain the concept of deployment slots in Azure App Service.
A:: Deployment slots in Azure App Service allow you to deploy your web app to a separate slot instead of the default production slot. These slots are live apps with their own host names, and content and configurations can be swapped between slots, including the production slot.
Q:: What deployment options does Azure App Service provide for continuous integration and deployment?
A:: Azure App Service provides continuous integration and deployment support through various options including Azure DevOps Services, GitHub, Bitbucket, FTP, or a local Git repository. It auto-syncs code and future changes into the web app from the connected sources.
Q:: What are the supported programming languages and frameworks for Azure App Service on Linux?
A:: Supported languages and frameworks for Azure App Service on Linux include Node.js, Java (JRE 8 & JRE 11), PHP, Python, .NET, and Ruby. Custom Linux containers are also supported for other runtimes.
Q:: Describe the limitations of Azure App Service on Linux.
A:: Limitations of Azure App Service on Linux include lack of support on Shared pricing tier, features visibility on the Azure portal, and higher disk latency for built-in images compared to custom containers.
Q:: How can you retrieve the current list of supported languages and frameworks for Azure App Service on Linux?
A:: You can retrieve the current list by using the following command in the Cloud Shell: `az webapp list-runtimes --os-type linux`.
Q:: What does an App Service plan define in Azure App Service?
A:: An App Service plan defines a set of compute resources for a web app to run.
Q:: What are the factors defined by each App Service plan?
A:: Each App Service plan defines the operating system, region, number and size of VM instances, and pricing tier.
Q:: What determines the pricing and features of an App Service plan?
A:: The pricing tier of an App Service plan determines the features and cost associated with it.
Q:: What are the categories of pricing tiers for App Service plans?
A:: The categories include Shared compute (Free and Shared), Dedicated compute (Basic, Standard, Premium, PremiumV2, and PremiumV3), and Isolated (Isolated and IsolatedV2) tiers.
Q:: What is the difference between Shared compute and Dedicated compute tiers?
A:: Shared compute tiers run apps on the same Azure VM as other App Service apps, while Dedicated compute tiers run apps on dedicated Azure VMs.
Q:: What capabilities do Isolated tiers provide in App Service plans?
A:: Isolated tiers provide dedicated Azure VMs on dedicated Azure Virtual Networks, offering both compute and network isolation.
Q:: In which scenarios are Free and Shared tiers intended to be used?
A:: Free and Shared tiers are intended for development and testing purposes.
Q:: How does app scaling work in Free and Shared tiers?
A:: Apps in Free and Shared tiers receive CPU minutes on a shared VM instance and cannot scale out.
Q:: Explain how apps run and scale in tiers other than Free and Shared.
A:: In other tiers, apps run on all configured VM instances within the App Service plan and scale out based on the plan's settings.
Q:: What is the scale unit in App Service apps?
A:: The App Service plan serves as the scale unit for all apps within it.
Q:: How can you enhance the capabilities or features of your app in Azure App Service?
A:: By scaling up or down the App Service plan, changing the pricing tier, or isolating the app into a separate plan.
Q:: What considerations should be made before moving an app into a separate App Service plan?
A:: Considerations include the app's resource intensity, need for independent scaling, and geographical requirements.
Q:: When should you isolate your app into a new App Service plan?
A:: You should isolate your app into a new App Service plan when it's resource-intensive, requires independent scaling, or needs resources in a different geographical region.
Q:: What is automated deployment, and why is it beneficial?
A:: Automated deployment, also known as continuous deployment, is a process used to push out new features and bug fixes in a fast and repetitive pattern with minimal effect on end users. It is beneficial because it streamlines the deployment process, making it more efficient and reducing the manual effort required.
Q:: What are the options for automated deployment supported by Azure?
A:: Azure supports automated deployment directly from several sources, including Azure DevOps Services, GitHub, and Bitbucket.
Q:: How does Azure DevOps Services facilitate automated deployment?
A:: Azure DevOps Services allows you to push your code to Azure, build it in the cloud, run tests, generate a release, and finally, push the code to an Azure Web App, all as part of an automated deployment pipeline.
Q:: Explain the process of automated deployment from GitHub to Azure.
A:: When you connect your GitHub repository to Azure for automated deployment, any changes you push to your production branch on GitHub are automatically deployed to Azure, streamlining the deployment process.
Q:: How can you configure automated deployment with Bitbucket?
A:: Similar to GitHub, you can configure automated deployment with Bitbucket, enabling seamless deployment of changes to your Azure Web App directly from your Bitbucket repository.
Q:: What are the options available for manual deployment to Azure?
A:: Manual deployment options to Azure include Git, Azure CLI (`webapp up`), Zip deploy, and FTP/S.
Q:: Describe how Git facilitates manual deployment to App Service web apps.
A:: App Service web apps feature a Git URL that you can add as a remote repository. Pushing changes to this remote repository deploys your application to Azure.
Q:: What is the purpose of the `webapp up` feature in the Azure CLI?
A:: The `webapp up` feature in the Azure CLI packages your application and deploys it to Azure. It can also create a new App Service web app if one hasn't already been created, simplifying the deployment process.
Q:: How does Zip deploy work for manual deployment to App Service?
A:: Zip deploy allows you to use `curl` or a similar HTTP utility to send a ZIP file containing your application files to App Service, which then deploys the application.
Q:: What are FTP and FTPS, and how are they used for manual deployment?
A:: FTP (File Transfer Protocol) and FTPS (FTP Secure) are traditional methods of transferring files over a network. They can be used for manual deployment by pushing code to the App Service environment via FTP or FTPS.
Q:: Why is it recommended to use deployment slots when deploying a new production build?
A:: Using deployment slots allows you to deploy your application to a staging environment first, minimizing the impact on the production environment. It also facilitates seamless swapping of staging and production environments.
Q:: What benefits does using deployment slots offer during the deployment process?
A:: Deployment slots help ensure zero-downtime deployments by allowing you to warm up the necessary worker instances to match your production scale before swapping staging and production environments.
Q:: How does the swap operation in deployment slots eliminate downtime during production deployment?
A:: The swap operation in deployment slots ensures that the necessary worker instances are warmed up to match your production scale before the actual swap occurs, minimizing downtime during the deployment process.
Q:: Why use the built-in authentication?
A:: You're not required to use App Service for authentication and authorization. Many web frameworks are bundled with security features, and you can use them if you like. If you need more flexibility than App Service provides, you can also write your own utilities. The built-in authentication feature for App Service and Azure Functions can save you time and effort by providing out-of-the-box authentication with federated identity providers, allowing you to focus on the rest of your application.
Q:: What identity providers are available by default in App Service?
A:: App Service uses federated identity, offering several default identity providers such as Microsoft identity platform, Facebook, Google, Twitter, Any OpenID Connect provider, and GitHub.
Q:: How does the authentication and authorization module work in Azure App Service?
A:: The authentication and authorization module runs in the same sandbox as your application code. It handles authenticating users and clients with the specified identity providers, validates and stores OAuth tokens, manages authenticated sessions, and injects identity information into HTTP request headers.
Q:: What is the authentication flow in Azure App Service?
A:: The authentication flow involves two approaches: one without provider SDK and the other with provider SDK. Without the provider SDK, the application delegates federated sign-in to App Service, whereas with the provider SDK, the application signs users in to the provider manually and then submits the authentication token to App Service for validation.
Q:: What behaviors can be configured for unauthenticated requests in App Service?
A:: In App Service, you can configure behaviors for unauthenticated requests, including allowing unauthenticated requests, which defers authorization to the application code, or requiring authentication, which rejects any unauthenticated traffic to the application.
Q:: What does the built-in token store in App Service do?
A:: App Service provides a built-in token store, which is a repository of tokens associated with the users of your web apps, APIs, or native mobile apps. This token store is available immediately when you enable authentication with any provider.
Q:: How are authentication and authorization traces handled in Azure App Service?
A:: If you enable application logging, authentication and authorization traces are collected directly in your log files in Azure App Service. These traces can help diagnose authentication errors or unexpected behavior.
Q:: What are the default accessibility characteristics of apps hosted in Azure App Service?
A:: By default, apps hosted in App Service are accessible directly through the internet and can reach only internet-hosted endpoints.
Q:: What are the two main deployment types for Azure App Service?
A:: The two main deployment types for Azure App Service are multitenant public service and single-tenant App Service Environment (ASE).
Q:: What are the roles involved in Azure App Service's distributed system?
A:: The roles involved in Azure App Service's distributed system are _front ends_ and _workers_.
Q:: Why can't you directly connect the App Service network to your network?
A:: You can't directly connect the App Service network to your network because there are many different customers in the same App Service scale unit.
Q:: What are the inbound and outbound features available for Azure App Service networking?
A:: Inbound features include App-assigned address, Access restrictions, Service endpoints, and Private endpoints. Outbound features include Hybrid Connections, Gateway-required virtual network integration, and Virtual network integration.
Q:: Explain the difference between multitenant and single-tenant Azure App Service environments.
A:: Multitenant App Service hosts multiple customers in the same scale unit, while single-tenant App Service Environment (ASE) hosts isolated SKU App Service plans directly in your Azure virtual network.
Q:: How can you restrict access to your app from a set of well-defined addresses?
A:: You can restrict access to your app from a set of well-defined addresses using the Access restrictions feature.
Q:: What determines the outbound addresses used by apps in Azure App Service?
A:: The outbound addresses used by apps in Azure App Service are determined by the worker VM type and the pricing tier of the plan.
Q:: How can you find the outbound IP addresses used by your app in the Azure portal?
A:: You can find the outbound IP addresses used by your app in the Azure portal by selecting **Properties** in your app's left-hand navigation.
Q:: What Azure CLI command can you use to find the outbound IP addresses for your app?
A:: To find the outbound IP addresses for your app using Azure CLI, you can use the `az webapp show` command with the appropriate parameters and query options.

#### Chapter 2 - Configure web app settings

Q:: What are app settings in App Service, and how are they passed to the application code?
A:: App settings in App Service are variables passed as environment variables to the application code. For Linux apps and custom containers, App Service passes app settings to the container using the `--env` flag to set the environment variable in the container.
Q:: How can you access application settings in App Service?
A:: Application settings can be accessed by navigating to your app's management page and selecting **Configuration > Application Settings**.
Q:: Explain how setting app settings in App Service differs for ASP.NET and ASP.NET Core developers compared to Web.config or appsettings.json.
A:: Setting app settings in App Service for ASP.NET and ASP.NET Core developers resembles setting them in `<appSettings>` in Web.config or appsettings.json, but the values in App Service override the ones in Web.config or appsettings.json.
Q:: Why is it recommended to keep production secrets in App Service rather than in Web.config or appsettings.json?
A:: It is recommended to keep production secrets in App Service because the same code can use development settings when debugging locally and production secrets when deployed to Azure.
Q:: How are app settings encrypted when stored in App Service?
A:: App settings are always encrypted when stored (encrypted-at-rest).
Q:: What steps are involved in adding a new app setting?
A:: To add a new app setting, select **New application setting**.
Q:: What options are available when editing a setting?
A:: When editing a setting, you can select the **Edit** button on the right side.
Q:: Explain the configuration requirement for nested JSON key structures in Linux containers.
A:: In Linux containers, any nested JSON key structure in the app setting name needs to be configured in App Service as `ApplicationInsights__InstrumentationKey` for the key name, replacing `:` with `__` (double underscore).
Q:: How can you add or edit app settings in bulk?
A:: To add or edit app settings in bulk, select the **Advanced** edit button.
Q:: How do the values set in App Service for ASP.NET and ASP.NET Core developers differ from those set in Web.config?
A:: Values set in App Service for ASP.NET and ASP.NET Core developers override the ones in Web.config.
Q:: Why might it be preferable to use connection strings instead of app settings for certain Azure database types?
A:: It might be preferable to use connection strings instead of app settings for certain Azure database types because they are backed up along with the app only if you configure a connection string for the database in your App Service app.
Q:: What is the benefit of configuring a connection string for the database in your App Service app?
A:: The benefit of configuring a connection string for the database in your App Service app is that certain Azure database types are backed up along with the app only if you configure a connection string for the database.
Q:: What principles are followed when adding or editing connection strings?
A:: Adding and editing connection strings follow the same principles as other app settings, and they can also be tied to deployment slots.
Q:: Provide an example of connection strings in JSON formatting used for bulk adding or editing.
A:: ```
[
{
"name": "name-1",
"value": "conn-string-1",
"type": "SQLServer",
"slotSetting": false
},
{
"name": "name-2",
"value": "conn-string-2",
"type": "PostgreSQL",
"slotSetting": false
},
...
]
```
Q:: What section of the configuration allows you to adjust general settings for your application?
A:: Configuration > General settings section.
Q:: What are some settings that may require scaling up to higher pricing tiers?
A:: Some settings require you to scale up to higher pricing tiers.
Q:: What options are available under the "Stack settings"?
A:: The software stack to run the app, including the language and SDK versions. For Linux apps and custom container apps, you can also set an optional start-up command or file.
Q:: How can you establish the stack settings for your application?
A:: By configuring the settings in the "Stack settings" section under Configuration > General settings.
Q:: What does the "Platform settings" section allow you to configure?
A:: It allows you to configure settings for the hosting platform, including bitness, WebSocket protocol, Always On, Managed pipeline version, HTTP version, and ARR affinity.
Q:: Explain the purpose of the "Always On" setting.
A:: The "Always On" setting keeps the app loaded even when there's no traffic. It's required for continuous WebJobs or for WebJobs that are triggered using a CRON expression.
Q:: When is the "Always On" feature required?
A:: It is required for continuous WebJobs or for WebJobs that are triggered using a CRON expression.
Q:: What is the significance of the "Managed pipeline version" setting?
A:: It determines the IIS pipeline mode. Set it to Classic if you have a legacy app that requires an older version of IIS.
Q:: When would you set the "HTTP version" to 2.0?
A:: You would set the "HTTP version" to 2.0 to enable support for HTTP/2 protocol.
Q:: What does the "ARR affinity" setting ensure in a multi-instance deployment?
A:: It ensures that the client is routed to the same instance for the life of the session in a multi-instance deployment.
Q:: What does the "Debugging" setting enable?
A:: The "Debugging" setting enables remote debugging for ASP.NET, ASP.NET Core, or Node.js apps. This option turns off automatically after 48 hours.
Q:: Which types of applications does the "Incoming client certificates" setting require mutual authentication for?
A:: It requires mutual authentication for applications utilizing TLS mutual authentication to restrict access to your app by enabling different types of authentication.
Q:: What can you configure in the **Configuration > Path mappings** section?
A:: You can configure handler mappings, and virtual application and directory mappings.
Q:: What options are available for configuring handler mappings and virtual applications and directories?
A:: Options include customizing IIS handler mappings and virtual applications/directories for Windows apps, and adding custom storage for containerized apps.
Q:: What options are displayed on the **Path mappings** page based on the OS type?
A:: Different options are displayed based on the OS type: Windows apps (uncontainerized) and Linux/containerized apps.
Q:: How can you customize IIS handler mappings and virtual applications and directories for Windows apps?
A:: For Windows apps, you can customize IIS handler mappings and virtual applications and directories.
Q:: What is the purpose of handler mappings in Windows apps?
A:: Handler mappings enable adding custom script processors to handle requests for specific file extensions in Windows apps.
Q:: How do you add a custom handler in Windows apps?
A:: To add a custom handler, select **New handler**.
Q:: What parameters do you configure when adding a custom handler in Windows apps?
A:: When adding a custom handler, configure the **Extension**, **Script processor**, and optional **Arguments**.
Q:: What is the default root path for each app in Windows apps?
A:: The default root path is `/` mapped to `D:\home\site\wwwroot` for each app in Windows apps.
Q:: How can you edit or add virtual applications and directories in Windows apps?
A:: You can edit or add virtual applications and directories if your app root is in a different folder or if your repository has more than one application.
Q:: How do you configure virtual applications and directories for Windows apps?
A:: Configure virtual applications and directories by specifying each virtual directory and its corresponding physical path relative to the website root (`D:\home`).
Q:: What types of apps does the option for adding custom storage apply to?
A:: The option for adding custom storage applies to containerized apps, including Linux apps and Windows and Linux custom containers running on App Service.
Q:: What steps are involved in configuring custom storage for containerized apps?
A:: Select **New Azure Storage Mount** and configure the custom storage with options like name, configuration, storage accounts, storage type, container, share name, access key, and mount path.
Q:: What configuration options are available for custom storage?
A:: Configuration options include Basic or Advanced configurations for custom storage.
Q:: What storage types are supported for Windows container apps when configuring custom storage?
A:: Windows container apps only support Azure Files when configuring custom storage.
Q:: What information is required when configuring custom storage for containerized apps?
A:: When configuring custom storage, you need to provide details such as the storage account, storage type, container (or share name), access key, and mount path.
Q:: What are the types of logging available for App Service apps?
A:: The types of logging available for App Service apps include Application logging, Web server logging, Detailed error logging, Failed request tracing, and Deployment logging.
Q:: Where can application logging messages be stored for Windows and Linux platforms?
A:: For Windows and Linux platforms, application logging messages can be stored either in the App Service file system or Azure Storage blobs.
Q:: What information is included in web server logging for Windows apps?
A:: Web server logging for Windows apps includes raw HTTP request data in the W3C extended log file format, containing information like the HTTP method, resource URI, client IP, client port, user agent, response code, etc.
Q:: How does App Service handle detailed error logging for Windows apps?
A:: For Windows apps, App Service saves copies of the .html error pages that would have been sent to the client browser. It saves the error page each time an application error occurs with an HTTP code of 400 or greater.
Q:: What purpose does failed request tracing serve in App Service for Windows?
A:: Failed request tracing in App Service for Windows provides detailed tracing information on failed requests, including a trace of the IIS components used to process the request and the time taken in each component.
Q:: Is deployment logging configurable in App Service?
A:: Deployment logging in App Service happens automatically and there are no configurable settings for deployment logging.
Q:: How can you enable application logging for Windows apps in the Azure portal?
A:: To enable application logging for Windows apps in the Azure portal, navigate to your app and select **App Service logs**.
Q:: What are the options available for application logging in the Azure portal for Windows apps?
A:: The options available for application logging in the Azure portal for Windows apps include **Application Logging (Filesystem)** and **Application Logging (Blob)**.
Q:: What configuration settings can you adjust for application logging levels in Windows apps?
A:: For application logging levels in Windows apps, you can adjust the level of details included in the log, such as **Disabled**, **Error**, **Warning**, **Information**, and **Verbose**.
Q:: How can you enable application logging for Linux/Container apps?
A:: To enable application logging for Linux/Container apps, set the **Application logging** option to **File System** in **App Service logs**.
Q:: What parameters can you set when enabling application logging for Linux/Container apps?
A:: When enabling application logging for Linux/Container apps, you can specify the disk quota for the application logs in **Quota (MB)** and set the retention period for the logs in **Retention Period (Days)**.
Q:: How do you enable web server logging in App Service?
A:: To enable web server logging in App Service, you can select either **Storage** to store logs on blob storage or **File System** to store logs on the App Service file system.
Q:: What storage options are available for web server logs in App Service?
A:: The available storage options for web server logs in App Service include blob storage and the App Service file system.
Q:: How can log messages be added to application code in ASP.NET applications?
A:: In ASP.NET applications, log messages can be added using the `System.Diagnostics.Trace` class or by utilizing the default logging provider, `Microsoft.Extensions.Logging.AzureAppServices`.
Q:: What logging provider does ASP.NET Core use by default?
A:: By default, ASP.NET Core uses the `Microsoft.Extensions.Logging.AzureAppServices` logging provider.
Q:: What package can Python applications use for sending logs to the application diagnostics log?
A:: Python applications can use the OpenCensus package for sending logs to the application diagnostics log.
Q:: What types of log files can be streamed in real-time in App Service?
A:: In App Service, log files ending in .txt, .log, or .htm stored in the `/LogFiles` directory can be streamed in real-time.
Q:: How can you stream logs in the Azure portal?
A:: To stream logs in the Azure portal, navigate to your app and select **Log stream**.
Q:: What Azure CLI command can you use to stream logs live in Cloud Shell?
A:: To stream logs live in Cloud Shell using Azure CLI, you can use the command: `az webapp log tail --name appname --resource-group myResourceGroup`.
Q:: How can you access log files stored in Azure Storage blobs or the App Service file system?
A:: Log files stored in Azure Storage blobs can be accessed using a client tool that works with Azure Storage. For logs stored in the App Service file system, you can download the ZIP file from specific URLs provided for both Linux/container apps and Windows apps.
Q:: What are the options available for adding certificates in Azure App Service?
A:: The options available for adding certificates in Azure App Service include creating a free App Service managed certificate, purchasing an App Service certificate, importing a certificate from Key Vault, uploading a private certificate, and uploading a public certificate.
Q:: What is the difference between a free App Service managed certificate and a purchased App Service certificate?
A:: The free App Service managed certificate is provided at no charge and is fully managed by App Service. It's suitable for securing custom DNS names but has limitations. In contrast, a purchased App Service certificate involves buying a private certificate from Azure. It offers automated management, renewal, and export options.
Q:: What are the requirements for using a private certificate in App Service?
A:: To use a private certificate in App Service, the certificate must be exported as a password-protected PFX file, encrypted using triple DES. It must contain a private key that is at least 2048 bits long and include all intermediate certificates in the certificate chain. Additionally, it must have an Extended Key Usage for server authentication and be signed by a trusted certificate authority.
Q:: What limitations are associated with the free App Service managed certificate?
A:: Limitations of the free App Service managed certificate include lack of support for wildcard certificates, private DNS, exportability, usage as a client certificate using certificate thumbprint, and App Service Environments (ASE). It only supports alphanumeric characters, dashes (-), and periods (.).
Q:: What tasks does Azure manage when you purchase an App Service Certificate?
A:: When you purchase an App Service Certificate from Azure, Azure manages tasks such as the purchase process from the certificate provider, domain verification of the certificate, maintenance of the certificate in Azure Key Vault, certificate renewal, and synchronization of the certificate with imported copies in App Service apps.
Q:: What options are available for managing an already working App Service certificate?
A:: If you already have a working App Service certificate, you can import the certificate into App Service and manage it, including actions such as renewal, rekey, and export.
Q:: What is the process for creating a free managed certificate in App Service?
A:: To create a free managed certificate in App Service, your App Service plan must be in the Basic, Standard, Premium, or Isolated tier. You create the certificate, bind it to a custom domain, and let App Service manage it. The certificate is renewed automatically in six-month increments, 45 days before expiration.
Q:: What tiers must your App Service plan be in to create custom TLS/SSL bindings or enable client certificates for your App Service app?
A:: Your App Service plan must be in the Basic, Standard, Premium, or Isolated tier to create custom TLS/SSL bindings or enable client certificates for your App Service app.
Q:: What are the limitations of the free App Service managed certificate?
A:: The limitations of the free App Service managed certificate include lack of support for wildcard certificates, private DNS, exportability, usage as a client certificate using certificate thumbprint, and App Service Environments (ASE). It only supports alphanumeric characters, dashes (-), and periods (.).
Q:: Are App Service Certificates supported in Azure National Clouds at the present time?
A:: App Service Certificates are not supported in Azure National Clouds at the present time.

#### Chapter 3 - Scale apps in Azure App Service

#### Chapter 4 - Explore Azure App Service deployment slots

### Part II - Implement Azure Functions

#### Chapter 1 - Explore Azure Functions

#### Chapter 2 - Develop Azure Functions

### Part III - Develop solutions that use Blob storage

#### Chapter 1 - Explore Azure Blob storage

#### Chapter 2 - Manage the Azure Blob storage lifecycle

#### Chapter 3 - Work with Azure Blob storage

### Part IV - Develop solutions that use Azure Cosmos DB

#### Chapter 1 - Explore Azure Cosmos DB

#### Chapter 2 - Work with Azure Cosmos DB

### Part V - Implement containerized solutions

#### Chapter 1 - Manage container images in Azure Container Registry

#### Chapter 2 - Run container images in Azure Container Instances

#### Chapter 3 - Implement Azure Container Apps

### Part VI - Implement user authentication and authorization

#### Chapter 1 - Explore the Microsoft identity platform

#### Chapter 2 - Implement authentication by using the Microsoft Authentication Library

#### Chapter 3 - Implement shared access signatures

#### Chapter 4 - Explore Microsoft Graph

### Part VII - Implement secure Azure solutions

#### Chapter 1 - Implement Azure Key Vault

#### Chapter 2 - Implement managed identities

#### Chapter 3 - Implement Azure App Configuration

### Part VIII - Implement API Management

#### Chapter 1 - Explore API Management

### Part IX - Develop event-based solutions

#### Chapter 1 - Explore Azure Event Grid

#### Chapter 2 - Explore Azure Event Hubs

### Part X - Develop message-based solutions

#### Chapter 1 - Discover Azure message queues

### Part XI - Troubleshoot solutions by using Application Insights

#### Chapter 1 - Monitor app performance

### Part XII - Implement caching for solutions

#### Chapter 1 - Develop for Azure Cache for Redis

#### Chapter 2 - Develop for storage on CDNs

---

DECK INFO

TARGET DECK: EXAMPLE::EXAMPLE::MADSF - Az 204 developing solutions for microsoft azure - microsoft learn

FILE TAGS: #EXAMPLE::#EXAMPLE

Tags:

Reference:

Related:

```dataview
LIST
where file.name = this.file.name
```