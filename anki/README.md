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
A:: 
```json
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
  }
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

Q:: What triggers autoscaling in a system?
A:: Autoscaling can be triggered based on factors such as CPU utilization, memory occupancy, incoming request surges, or a combination of these.

Q:: How does autoscaling differ from scaling up and down?
A:: Autoscaling adjusts available resources based on demand by scaling in and out, as opposed to scaling up and down.

Q:: What is Azure App Service Autoscaling, and how does it function?
A:: Azure App Service Autoscaling monitors resource metrics of a web app and adds or removes web servers to handle increasing workloads while balancing the load between them.

Q:: What are autoscaling rules, and how do they function?
A:: Autoscaling rules define thresholds for metrics and trigger autoscale events when thresholds are crossed. These rules can also deallocate resources when workload diminishes.

Q:: When should autoscaling be considered?
A:: Autoscaling should be considered for providing elasticity, improving availability and fault tolerance, and handling short-term workload fluctuations, such as during holidays or sudden spikes in activity.

Q:: What are the limitations of autoscaling?
A:: Autoscaling may not be effective for resource-intensive processing or handling long-term growth. Additionally, it incurs overhead and may not be cost-effective for predictable growth scenarios. The number of instances of a service also affects its effectiveness.

Q:: What is autoscaling, and what does it aim to achieve?
A:: Autoscaling enables the specification of conditions for scaling a web app out and in again based on resource usage, aiming to ensure sufficient resources during peak times while managing costs during lower demand periods.

Q:: How does autoscaling help manage costs?
A:: Autoscaling helps manage costs by dynamically adjusting resource allocation according to demand, preventing over-provisioning and unnecessary expenses.

Q:: What is the significance of autoscaling in handling large volumes of requests?
A:: Autoscaling ensures that a web app can handle large volumes of requests during peak times by dynamically allocating resources to meet the demand.

Q:: What options does Azure provide for autoscaling?
A:: Azure provides options for autoscaling based on metrics like disk queue length or HTTP requests, and also allows scaling according to a schedule.

Q:: Explain how autoscaling based on a metric works.
A:: Autoscaling based on a metric involves defining autoscale rules that specify a metric to monitor and how autoscaling should respond when the metric crosses a defined threshold.

Q:: What are the available metrics for autoscale rules in a web app?
A:: Available metrics for autoscale rules in a web app include CPU Percentage, Memory Percentage, Disk Queue Length, HTTP Queue Length, Data In, and Data Out.

Q:: How does autoscaling analyze metrics over time?
A:: Autoscaling analyzes trends in metric values across all instances over time by aggregating values retrieved for a metric over a period known as the time grain, and further aggregating these values over a longer user-specified period called the Duration.

Q:: Describe autoscale actions and their purposes.
A:: Autoscale actions include scale-out (increasing instance count) and scale-in (reducing instance count), triggered by a metric crossing a threshold, and they help maintain the desired performance level of the web app.

Q:: What is the purpose of the cooldown period in autoscale actions?
A:: The cooldown period in autoscale actions prevents rapid triggering of scale events, allowing the system to stabilize between autoscale events by avoiding premature scaling decisions.

Q:: Why is it recommended to plan for scaling-in when a workload decreases?
A:: Planning for scaling-in when a workload decreases helps optimize resource usage and reduce costs during periods of lower demand.

Q:: How can autoscale rules be paired effectively?
A:: Autoscale rules can be paired effectively by defining both scale-out and scale-in rules in the same autoscale condition, each triggered by different thresholds of the same metric.

Q:: Can you describe how autoscale rules can be combined within an autoscale condition?
A:: Autoscale rules within an autoscale condition can be combined by defining multiple rules for scale-out and scale-in actions, with each rule responding to different metrics or thresholds, ensuring flexibility and efficiency in scaling operations.

Q:: What are the prerequisites for enabling autoscaling in App Service?
A:: Not all pricing tiers support autoscaling. The development pricing tiers are either limited to a single instance or they only provide manual scaling. If you've selected one of these tiers, you must first scale up to the S1 or any of the P level production tiers.

Q:: How do you navigate to enable autoscaling in Azure portal?
A:: To get started with autoscaling, navigate to your App Service plan in the Azure portal and select Scale out (App Service plan) in the Settings group in the left navigation pane.

Q:: What are the limitations regarding pricing tiers and autoscaling?
A:: The development pricing tiers are either limited to a single instance (the F1 and D1 tiers), or they only provide manual scaling (the B1 tier).

Q:: What happens when you select "Custom autoscale" in the App Service Plan settings?
A:: Selecting Custom autoscale reveals condition groups you can use to manage your scale settings.

Q:: What can you do once autoscaling is enabled?
A:: Once autoscaling is enabled, you can edit the automatically created default scale condition, and you can add your own custom scale conditions.

Q:: What is the purpose of the default scale condition in autoscaling?
A:: The Default scale condition is executed when none of the other scale conditions are active.

Q:: How can you create custom scale conditions in autoscaling?
A:: Once autoscaling is enabled, you can add your own custom scale conditions.

Q:: Describe the options available for metric-based scale conditions.
A:: A metric-based scale condition can specify the minimum and maximum number of instances to create. The maximum number can't exceed the limits defined by the pricing tier. Additionally, all scale conditions other than the default may include a schedule indicating when the condition should be applied.

Q:: What are scale rules in autoscaling?
A:: A metric-based scale condition contains one or more scale rules. You use the Add a rule link to add your own custom rules. You define the criteria that indicate when a rule should trigger an autoscale action, and the autoscale action to be performed (scale out or scale in) using the metrics, aggregations, operators, and thresholds described earlier.

Q:: How do you monitor autoscaling activity in the Azure portal?
A:: The Azure portal enables you to track when autoscaling has occurred through the Run history chart.

Q:: What information does the "Run history" chart provide?
A:: The Run history chart shows how the number of instances varies over time, and which autoscale conditions caused each change.

Q:: How can you correlate autoscaling events with resource utilization in App Service?
A:: You can use the Run history chart with the metrics shown on the Overview page to correlate the autoscaling events with resource utilization.

Q:: What are the key components of an autoscale setting?
A:: The key components of an autoscale setting include maximum, minimum, and default values of instances, along with associated metrics to scale by.

Q:: Explain the purpose of an autoscale job.
A:: An autoscale job reads the associated metric to scale by and checks if it has crossed the configured threshold for scale-out or scale-in.

Q:: How are thresholds calculated in autoscale settings? Provide an example.
A:: Thresholds in autoscale settings are calculated at an instance level. For example, "scale out by one instance when average CPU > 80% when instance count is 2" means to scale out when the average CPU across all instances is greater than 80%.

Q:: Why is it important to ensure a difference between the maximum and minimum values in autoscale settings?
A:: Ensuring a difference between the maximum and minimum values prevents situations where no scale action can occur, providing flexibility for autoscale to function effectively.

Q:: Describe the significance of choosing appropriate statistics for diagnostics metrics in autoscale settings.
A:: Choosing appropriate statistics for diagnostics metrics, such as Average, Minimum, Maximum, or Total, ensures accurate scaling decisions based on the nature of the metric being monitored.

Q:: What are the recommended practices for choosing thresholds for scale-out and scale-in in autoscale settings?
A:: Recommended practices include selecting different thresholds for scale-out and scale-in to prevent situations like "flapping" and ensuring an adequate margin between the thresholds.

Q:: Explain the concept of "flapping" in autoscale settings and how it can be avoided.
A:: "Flapping" refers to situations where scale-in and scale-out actions continually oscillate. It can be avoided by selecting thresholds carefully and ensuring a margin between scale-out and scale-in thresholds.

Q:: Provide an example of a recommended rule combination for autoscale settings and explain its functioning.
A:: An example of a recommended rule combination is to increase instances by 1 count when CPU% >= 80 and decrease instances by 1 count when CPU% <= 60. This rule combination allows for effective scaling while avoiding "flapping" situations.

Q:: What considerations should be taken into account when multiple rules are configured in an autoscale profile?
A:: When multiple rules are configured, autoscale runs if any rule is met for scale-out, while for scale-in, autoscale requires all rules to be met.

Q:: Why is selecting a safe default instance count crucial in autoscale settings?
A:: Selecting a safe default instance count ensures that the service can scale appropriately when metrics aren't available, providing stability to the autoscale process.

Q:: What conditions trigger autoscale notifications according to the text?
A:: Autoscale notifications are triggered when autoscale issues a scale operation, successfully completes a scale action, fails to take a scale action, metrics aren't available for scale decisions, or metrics become available again.

Q:: How can one monitor the health of the autoscale engine based on the provided text?
A:: One can monitor the health of the autoscale engine by using Activity Log alerts and configuring email or webhook notifications for successful scale actions via the notifications tab on the autoscale setting.

#### Chapter 4 - Explore Azure App Service deployment slots

Q:: What are deployment slots in Azure App Service, and how do they function in different tiers?
A:: Deployment slots in Azure App Service are live apps with their own host names, allowing you to deploy your web app, web app on Linux, mobile back end, or API app. They function differently depending on the tier of your App Service plan. Specifically, they are available in the Standard, Premium, or Isolated tiers.

Q:: What benefits are associated with deploying an application to a non-production slot before swapping it with the production slot?
A:: Deploying an application to a non-production slot offers several benefits:

1. It allows you to validate app changes in a staging deployment slot before swapping them with the production slot.
2. Deploying to a slot first ensures that all instances of the slot are warmed up before being swapped into production, eliminating downtime.
3. Traffic redirection during swap operations is seamless, and no requests are dropped.

Q:: How does deploying to a staging deployment slot help in validating app changes?
A:: Deploying to a staging deployment slot enables you to validate app changes before swapping them with the production slot. This ensures that potential issues are identified and resolved before impacting the live production environment.

Q:: Explain the process of swapping deployment slots in Azure App Service.
A:: The process of swapping deployment slots involves swapping the content and configuration elements between two deployment slots, including the production slot. This allows you to seamlessly transition changes from a staging slot to the production slot without causing downtime or dropping requests.

Q:: Why is warming up instances of the slot important before swapping it into production?
A:: Warming up instances of the slot before swapping them into production ensures that the application is ready to handle incoming traffic. This helps to prevent performance issues or downtime that may occur if the instances are not warmed up.

Q:: How does Azure App Service handle traffic redirection during swap operations?
A:: Azure App Service handles traffic redirection during swap operations seamlessly, ensuring that no requests are dropped and that the transition between slots is smooth. This allows for uninterrupted service for users accessing the application.

Q:: What is the significance of having the "last known good site" when performing a swap in Azure App Service?
A:: Having the "last known good site" allows you to revert to the previous production app if the changes swapped into the production slot are not as expected. This provides a safety net in case issues arise during the swap process.

Q:: Is there any additional charge for using deployment slots in Azure App Service?
A:: No, there is no extra charge for using deployment slots in Azure App Service. They are included as part of the features offered within the Standard, Premium, or Isolated tiers.

Q:: How can you automate the workflow of swapping deployment slots in Azure App Service?
A:: You can automate the workflow of swapping deployment slots by configuring auto swap. Auto swap automatically swaps the staging slot with the production slot without the need for manual intervention, streamlining the deployment process.

Q:: What limitations should you consider when scaling your app to a different tier in Azure App Service?
A:: When scaling your app to a different tier in Azure App Service, you should consider the limitations regarding the number of deployment slots supported by each tier. For example, if your app has more than five slots, you cannot scale it down to the Standard tier, as the Standard tier supports only five deployment slots.

Q:: What precautions does App Service take to prevent downtime during slot swapping?
A:: App Service ensures that the target slot doesn't experience downtime during slot swapping by applying the target slot's settings to all instances of the source slot, triggering restarts if necessary, and initializing local cache and application initiation.

Q:: How does App Service handle settings during slot swapping, particularly in the case of slot-specific app settings and connection strings?
A:: During slot swapping, App Service applies slot-specific app settings and connection strings from the target slot to all instances of the source slot, triggering restarts as needed to ensure synchronization.

Q:: During a swap with preview, what actions occur after applying the target slot's settings to all instances of the source slot?
A:: After applying the target slot's settings to all instances of the source slot during a swap with preview, the first phase ends, allowing validation of the source slot with the target slot's settings.

Q:: What happens if any instance fails to restart during the slot swapping process?
A:: If any instance fails to restart during the slot swapping process, the swap operation reverts all changes to the source slot and halts the operation.

Q:: Describe the role of local cache initialization in the slot swapping procedure.
A:: Local cache initialization triggers restarts on each instance of the source slot and is performed by making an HTTP request to the application root ("/") on each instance.

Q:: How does App Service handle Application Initiation during slot swapping when auto swap is enabled with custom warm-up?
A:: App Service triggers Application Initiation by making HTTP requests to the application root ("/") on each instance of the source slot, marking instances as warmed up if they return any HTTP response.

Q:: What determines if a slot is considered "warmed up" during the slot swapping process?
A:: During slot swapping, a slot is considered "warmed up" if all instances on the source slot respond successfully to the Application Initiation requests.

Q:: Explain the significance of the routing rules switching during the slot swapping operation.
A:: Switching routing rules during slot swapping directs traffic from the source slot to the target slot, ensuring a seamless transition of apps without downtime.

Q:: How does the configuration differ between swapped and unswapped settings in App Service?
A:: Swapped settings, such as general settings, app settings, and connection strings, are synchronized between slots, while unswapped settings, like custom domain names and non-public certificates, remain specific to their respective slots.

Q:: What measures can be taken to ensure certain settings stick to a specific slot and are not affected by slot swapping?
A:: To ensure certain settings stick to a specific slot, the `WEBSITE_OVERRIDE_PRESERVE_DEFAULT_STICKY_SLOT_SETTINGS` app setting must be added to every slot of the app and set to `0` or `false`.

Q:: How does the presence of the `WEBSITE_OVERRIDE_PRESERVE_DEFAULT_STICKY_SLOT_SETTINGS` app setting affect the swappability of settings in App Service?
A:: The presence of the `WEBSITE_OVERRIDE_PRESERVE_DEFAULT_STICKY_SLOT_SETTINGS` app setting determines whether settings are swappable or not in App Service, affecting the synchronization behavior during slot swapping.

Q:: What options are available to configure app settings or connection strings to stick to a specific slot and not be affected by swapping?
A:: To configure app settings or connection strings to stick to a specific slot, settings should be edited in the Configuration page for that slot, with the "Deployment slot setting" checkbox selected to indicate that the setting isn't swappable.

Q:: What is the purpose of swapping deployment slots?
A:: Swapping deployment slots allows you to move an application from one slot to another, such as from a staging environment to production, with minimal downtime and risk.

Q:: How can you manually swap deployment slots?
A:: To manually swap deployment slots, you need to go to your app's **Deployment slots** page, select **Swap**, choose the desired **Source** and **Target** slots, verify configuration changes, and then initiate the swap.

Q:: What is the advantage of performing a swap with preview?
A:: Performing a swap with preview allows you to validate how your application runs with the swapped settings before completing the swap. It also warms up the source slot, which is beneficial for mission-critical applications.

Q:: How do you configure auto swap?
A:: To configure auto swap, you need to go to your app's resource page, select the deployment slot you want to configure, turn on **Auto swap enabled**, choose the target slot for auto swap deployment, and save the settings.

Q:: What action should you take if errors occur in the target slot after a slot swap?
A:: If errors occur in the target slot after a slot swap, you should immediately swap the same two slots again to restore them to their pre-swap states.

Q:: How can you monitor a swap operation?
A:: To monitor a swap operation, you can access the activity log on your app's resource page in the portal and look for the `Swap Web App Slots` operation. You can expand it to view suboperations or errors for more details.

Q:: What is the default behavior for client requests to an app's production URL in App Service?
A:: By default, all client requests to the app's production URL (`http://<app_name>.azurewebsites.net`) are routed to the production slot.

Q:: Why might you want to route a portion of the traffic to another slot in App Service?
A:: This feature is useful if you need user feedback for a new update, but you're not ready to release it to production.

Q:: How can you route production traffic automatically in App Service?
A:: To route production traffic automatically, go to your app's resource page, select **Deployment slots**, and in the **Traffic %** column of the slot you want to route to, specify a percentage (between 0 and 100) to represent the amount of total traffic you want to route. Then select **Save**.

Q:: What does it mean when a client is "pinned" to a specific slot in App Service?
A:: When a client is automatically routed to a specific slot, it's "pinned" to that slot for the life of that client session.

Q:: How can you determine which slot a client session is pinned to in App Service?
A:: You can determine which slot a client session is pinned to by looking at the `x-ms-routing-name` cookie in your HTTP headers.

Q:: What is the purpose of routing production traffic manually in App Service?
A:: The purpose of routing production traffic manually in App Service is to allow users to opt in to or opt out of a beta app.

Q:: How can users opt out of a beta app in App Service using manual traffic routing?
A:: Users can opt out of a beta app in App Service by accessing a link on your webpage that contains the query parameter `x-ms-routing-name=self`.

Q:: How can users opt in to a beta app in App Service using manual traffic routing?
A:: Users can opt in to a beta app in App Service by accessing a link that contains the query parameter `x-ms-routing-name` set to the name of the non-production slot.

Q:: What happens when the `x-ms-routing-name` query parameter is set to `self` in App Service?
A:: When the `x-ms-routing-name` query parameter is set to `self` in App Service, the client browser is redirected to the production slot.

Q:: How can you access the staging slot manually in App Service, even if the routing percentage is set to 0?
A:: By default, new slots are given a routing rule of `0%`. Users can access the staging slot manually by using the `x-ms-routing-name` query parameter, even if the routing percentage is set to 0.

### Part II - Implement Azure Functions

#### Chapter 1 - Explore Azure Functions

Q:: What is Azure Functions and how does it simplify development?
A:: Azure Functions is a serverless solution that allows developers to write less code, maintain less infrastructure, and save on costs. It eliminates the need to worry about deploying and maintaining servers, as the cloud infrastructure provides all the necessary resources to keep applications running.

Q:: What are triggers and bindings in Azure Functions, and how do they help in coding?
A:: Triggers in Azure Functions are ways to start the execution of code, while bindings are ways to simplify coding for input and output data. Triggers enable the execution of code in response to specific events, while bindings simplify the integration of input and output data without requiring complex coding.

Q:: How do Azure Functions and Azure Logic Apps differ in terms of their primary functionalities?
A:: Azure Functions is a serverless compute service focused on executing code in response to events, while Azure Logic Apps is a serverless workflow integration platform used for orchestrating complex tasks through a series of actions.

Q:: Explain the concept of orchestrations in Azure Functions and Azure Logic Apps.
A:: Orchestrations in Azure Functions and Azure Logic Apps refer to the arrangement and coordination of functions or steps to accomplish a complex task. In Azure Functions, orchestrations are developed by writing code and using the Durable Functions extension, while in Azure Logic Apps, orchestrations are created using a GUI or editing configuration files.

Q:: How do you develop orchestrations in Azure Functions compared to Azure Logic Apps?
A:: Orchestrations in Azure Functions are developed by writing code and using the Durable Functions extension, whereas in Azure Logic Apps, orchestrations are created using a graphical user interface (GUI) or by editing configuration files.

Q:: What are the key differences between Azure Functions and Azure Logic Apps regarding development, connectivity, actions, monitoring, and management?
A::
- Development: Azure Functions is code-first (imperative), while Azure Logic Apps is designer-first (declarative).
- Connectivity: Azure Functions has about a dozen built-in binding types, while Azure Logic Apps has a large collection of connectors.
- Actions: Each activity in Azure Functions is an Azure function, whereas Azure Logic Apps offers a large collection of ready-made actions.
- Monitoring: Azure Functions use Azure Application Insights for monitoring, while Azure Logic Apps use the Azure portal and Azure Monitor logs.
- Management: Azure Functions can be managed through the REST API and Visual Studio, while Azure Logic Apps can be managed through the Azure portal, REST API, PowerShell, and Visual Studio.

Q:: Compare Azure Functions with Azure App Service WebJobs with the WebJobs SDK.
A:: Azure Functions and Azure App Service WebJobs with the WebJobs SDK are both code-first integration services designed for developers. They share many features such as source control integration, authentication, and monitoring with Application Insights integration.

Q:: What are the factors to consider when choosing between Azure Functions and WebJobs with the WebJobs SDK?
A:: Factors to consider include the serverless app model with automatic scaling, the ability to develop and test in the browser, pay-per-use pricing, integration with Logic Apps, and trigger events supported by each service.

Q:: What are the similarities between Azure Functions and WebJobs with the WebJobs SDK?
A:: Both Azure Functions and WebJobs with the WebJobs SDK are built on Azure App Service and support features such as source control integration, authentication, and monitoring with Application Insights integration.

Q:: How do Azure Functions and WebJobs with the WebJobs SDK differ in terms of their serverless app model, development and testing options, pricing, integration with Logic Apps, and trigger events?
A::
- Serverless app model with automatic scaling: Azure Functions support this feature, while WebJobs with the WebJobs SDK do not.
- Develop and test in browser: Azure Functions support this feature, while WebJobs with the WebJobs SDK do not.
- Pay-per-use pricing: Azure Functions offer pay-per-use pricing, while WebJobs with the WebJobs SDK do not.
- Integration with Logic Apps: Azure Functions integrate with Logic Apps, while WebJobs with the WebJobs SDK do not.
- Trigger events: Azure Functions support a variety of trigger events including Timer, Azure Storage queues and blobs, Azure Service Bus queues and topics, Azure Cosmos DB, Azure Event Hubs, and HTTP/WebHook, while WebJobs with the WebJobs SDK support Timer, Azure Storage queues and blobs, Azure Service Bus queues and topics, Azure Cosmos DB, Azure Event Hubs, and the file system.

Q:: What are the three basic hosting plans available for Azure Functions?
A:: The three basic hosting plans available for Azure Functions are the Consumption plan, the Premium plan, and the Dedicated plan.

Q:: How does the Consumption plan scale and what are its benefits?
A:: The Consumption plan scales automatically based on demand, and you only pay for compute resources when your functions are running. Instances of the Functions host are dynamically added and removed based on the number of incoming events.

Q:: Describe the scaling behavior of the Premium plan.
A:: The Premium plan scales automatically based on demand using pre-warmed workers, which run applications with no delay after being idle. It runs on more powerful instances and connects to virtual networks.

Q:: What are the benefits of the Premium plan compared to other hosting options?
A:: The Premium plan offers benefits such as automatic scaling, pre-warmed workers, running on more powerful instances, and connecting to virtual networks.

Q:: What is the Dedicated plan suitable for, and why might you choose it?
A:: The Dedicated plan is suitable for scenarios where Durable Functions can't be used. It runs functions within an App Service plan at regular App Service plan rates, making it best for long-running scenarios.

Q:: Explain the details of the App Service Environment (ASE) as a hosting option.
A:: App Service Environment (ASE) provides a fully isolated and dedicated environment for securely running App Service apps at high scale.

Q:: How does Kubernetes provide isolation and control for running function apps?
A:: Kubernetes provides a fully isolated and dedicated environment running on top of the Kubernetes platform, offering high levels of control and isolation for running function apps.

Q:: Compare the maximum number of instances allowed in different hosting plans.
A:: Consumption plan: Windows - 200, Linux - 100; Premium plan: Windows - 100, Linux - 20-100; Dedicated plan: 10-20; ASE: 100; Kubernetes: Varies by cluster.

Q:: What is the significance of the `functionTimeout` property in the host.json project file?
A:: The `functionTimeout` property specifies the timeout duration for functions in a function app. It determines the maximum time a function has to respond after being triggered.

Q:: What are the default and maximum timeout values for functions in the Consumption plan?
A:: Default: 5 minutes, Maximum: 10 minutes.

Q:: Why is a general Azure Storage account required for a function app?
A:: A general Azure Storage account is required for a function app because Functions rely on Azure Storage for operations such as managing triggers and logging function executions.

Q:: Can the same storage account used by a function app be used by triggers and bindings? If not, why?
A:: Yes, the same storage account used by a function app can also be used by triggers and bindings to store application data.

Q:: When should a separate storage account be considered for storage-intensive operations?
A:: For storage-intensive operations, a separate storage account should be considered to avoid potential performance issues and to better manage application data.

Q:: How does Azure Functions scale CPU and memory resources in the Consumption and Premium plans?
A:: Azure Functions scales CPU and memory resources in the Consumption and Premium plans by adding more instances of the Functions host based on the number of events that trigger a function.

Q:: What determines the number of instances in the Consumption plan?
A:: The number of instances in the Consumption plan is determined by the number of events that trigger a function.

Q:: What are the limitations on memory and CPU for each instance in the Consumption plan?
A:: Each instance of the Functions host in the Consumption plan is limited to 1.5 GB of memory and one CPU.

Q:: Describe the storage of function code files in Azure Functions.
A:: Function code files are stored on Azure Files shares on the function's main storage account.

Q:: What happens to function code files when you delete the main storage account of a function app?
A:: When you delete the main storage account of the function app, the function code files are deleted and can't be recovered.

Q:: What is the role of the scale controller in Azure Functions?
A:: The scale controller in Azure Functions monitors the rate of events and determines whether to scale out or scale in.

Q:: How does the scale controller determine whether to scale out or scale in?
A:: The scale controller uses heuristics for each trigger type, such as queue length and the age of the oldest queue message, to determine whether to scale out or scale in.

Q:: What is the unit of scale for Azure Functions?
A:: The unit of scale for Azure Functions is the function app.

Q:: What is a "cold start" in Azure Functions, and why does it occur?
A:: A "cold start" in Azure Functions refers to the added latency when the platform scales the number of instances from zero to one after the function app has been idle for a number of minutes.

Q:: What factors can cause scaling variations in Azure Functions?
A:: Scaling variations in Azure Functions can be caused by factors such as trigger type and selected language.

Q:: What is the maximum number of instances a single function app can scale out to?
A:: A single function app can scale out to a maximum of 200 instances.

Q:: How often are new instances allocated for HTTP triggers and non-HTTP triggers?
A:: For HTTP triggers, new instances are allocated at most once per second. For non-HTTP triggers, new instances are allocated at most once every 30 seconds.

Q:: Why might you want to limit the scale-out of an Azure Functions app?
A:: You might want to limit the scale-out of an Azure Functions app, especially for cases where downstream components like databases have limited throughput.

Q:: What is the default maximum number of instances for Consumption plan functions?
A:: By default, Consumption plan functions scale out to as many as 200 instances.

Q:: How can you specify a lower maximum for the number of instances in an Azure Functions app?
A:: You can specify a lower maximum for the number of instances in an Azure Functions app by modifying the `functionAppScaleLimit` value, which can be set to `0` or `null` for unrestricted, or a valid value between `1` and the app maximum.

#### Chapter 2 - Develop Azure Functions

Q:: What are the essential components of a function in Azure Functions development?
A:: A function in Azure Functions development consists of two crucial elements: code, which can be written in various languages, and configuration, specified in the _function.json_ file.

Q:: Explain the role of the _function.json_ file in Azure Functions.
A:: The _function.json_ file defines the function's trigger, bindings, and other configuration settings. It guides the runtime on how to monitor events and handle data during function execution.

Q:: How is the _function.json_ file created for compiled languages versus scripting languages?
A:: For compiled languages, the _function.json_ file is generated automatically from annotations in the code. However, for scripting languages, developers must provide the _function.json_ file themselves.

Q:: Describe the contents and purpose of the `bindings` property in the _function.json_ file.
A:: The `bindings` property in the _function.json_ file configures triggers and bindings. Each binding specifies settings such as type, direction, and name, determining data flow into and out of the function.

Q:: What are the mandatory settings required for every binding in the _function.json_ file?
A:: Every binding in the _function.json_ file requires settings for `type`, `direction`, and `name`.

Q:: Define a function app in the context of Azure Functions development.
A:: A function app provides an execution context in Azure for functions to run collectively. It serves as the unit of deployment and management, sharing pricing plans, deployment methods, and runtime versions across functions.

Q:: What is the significance of a function app in managing functions?
A:: Function apps allow for the collective management, deployment, and scaling of functions within Azure. All functions within a function app share common attributes like pricing plans and runtime versions.

Q:: Explain the restriction related to the language used in Functions 2.x within a function app.
A:: In Functions 2.x, all functions within a function app must be authored in the same language, unlike previous versions where language consistency was not required.

Q:: What does the root project folder of a function app typically contain?
A:: The root project folder of a function app typically contains a host configuration file (_host.json_) and a _bin_ folder containing necessary packages and library files.

Q:: Where is the host configuration file (_host.json_) located within a function app?
A:: The host configuration file (_host.json_) resides in the root folder of the function app.

Q:: What purpose does the _bin_ folder serve in a function app?
A:: The _bin_ folder in a function app contains packages and library files necessary for the function app's operation.

Q:: How does the folder structure vary depending on the programming language used in Azure Functions?
A:: The folder structure within a function app varies depending on the programming language being used, with specific guidelines provided for C#, F#, Java, JavaScript, and Python.

Q:: What opportunities does local development environments provide for Azure Functions development?
A:: Local development environments enable developers to use their preferred code editors and tools to create, test, and debug functions on their local computers, with the ability to connect to live Azure services.

Q:: Can local functions interact with live Azure services during development?
A:: Yes, local functions can connect to live Azure services during development, and developers can debug them using the full Functions runtime on their local computers.

Q:: Why is it advised not to mix local development with portal development within the same function app?
A:: It is advised not to mix local development with portal development within the same function app to maintain code consistency and avoid conflicts. Developing and publishing functions from a local project should not coincide with attempts to modify project code in the portal.

Q:: What is the purpose of triggers in Azure Functions?
A:: Triggers cause a function to run. They define how a function is invoked, and each function must have exactly one trigger.

Q:: Describe the concept of bindings in Azure Functions.
A:: Bindings in Azure Functions connect another resource to the function. They can be input bindings, output bindings, or both, and provide data to the function as parameters.

Q:: How are triggers and bindings defined in C# class libraries?
A:: Triggers and bindings in C# class libraries are defined by decorating methods and parameters with C# attributes.

Q:: In JavaScript, how can you define the data type for input data in _function.json_?
A:: In JavaScript, you can define the data type for input data in _function.json_ using the `dataType` property.

Q:: What are the possible values for the `dataType` property in _function.json_ for JavaScript functions?
A:: The possible values for the `dataType` property in _function.json_ for JavaScript functions include `binary`, `stream`, and `string`.

Q:: Explain the concept of binding direction in Azure Functions.
A:: Binding direction indicates whether a binding is used for input (`in`), output (`out`), or both. Triggers always have a direction of `in`, while input and output bindings use `in` and `out` respectively.

Q:: How is the direction property specified for triggers and bindings in the _function.json_ file?
A:: The direction property for triggers and bindings is specified in the _function.json_ file as part of the binding configuration.

Q:: Provide an example scenario where Azure Table storage is updated based on a new message in Azure Queue storage.
A:: An example scenario involves using an Azure Queue storage trigger and an Azure Table storage output binding to write a new row to Azure Table storage whenever a new message appears in Azure Queue storage.

Q:: What elements are defined in the `bindings` array within the _function.json_ file for the Azure Table storage output binding?
A:: The `bindings` array for the Azure Table storage output binding includes properties such as `type`, `direction`, `name`, `tableName`, and `connection`.

Q:: How is the parameter that receives the queue message content identified in the C# script example?
A:: In the C# script example, the parameter that receives the queue message content is identified by the name `order`, which corresponds to the `name` property value in _function.json_.

Q:: In the JavaScript example, how is the partition key generated for the Azure Table storage output binding?
A:: In the JavaScript example, the partition key is generated by calling the `generateRandomId()` function.

Q:: How does a class library define triggers and bindings differently compared to other languages like JavaScript?
A:: In a class library, triggers and bindings are defined using attributes instead of a _function.json_ file as in languages like JavaScript.

Q:: Where can you find more detailed examples of triggers and bindings for Azure Functions?
A:: More detailed examples of triggers and bindings for Azure Functions can be found in resources such as Azure Blob storage bindings, Azure Cosmos DB bindings, Timer triggers, and Azure Functions HTTP triggers and bindings documentation.

Q:: How does a function project reference connection information?
A:: The function project references connection information by name from its configuration provider. It doesn't directly accept the connection details, allowing them to be changed across environments.

Q:: Explain how the default configuration provider handles environment variables.
A:: The default configuration provider uses environment variables that are set in Application Settings when running in the Azure Functions service, or from the local settings file when developing locally.

Q:: What is the alternative to setting the connection string directly in a `function.json` file?
A:: Instead of setting the connection string directly in a `function.json` file, you would set `connection` to the name of an environment variable that contains the connection string.

Q:: Describe the usage of identity-based connections in Azure Functions.
A:: Some connections in Azure Functions are configured to use an identity instead of a secret. Support depends on the extension using the connection. Identity-based connections use a managed identity when hosted in the Azure Functions service.

Q:: What is the limitation associated with identity-based connections in Durable Functions?
A:: Identity-based connections are not supported with Durable Functions.

Q:: How does Azure Functions service handle identity-based connections?
A:: When hosted in the Azure Functions service, identity-based connections use a managed identity. The system-assigned identity is used by default, although a user-assigned identity can be specified with the `credential` and `clientID` properties.

Q:: What options are available for specifying the identity in Azure Functions service?
A:: The options available for specifying the identity in Azure Functions service include the system-assigned identity used by default, and the possibility of specifying a user-assigned identity with the `credential` and `clientID` properties.

Q:: How can permissions be granted to the identity used in Azure Functions?
A:: Permissions can be granted to the identity used in Azure Functions by assigning a role in Azure RBAC or specifying the identity in an access policy, depending on the service to which you're connecting.

Q:: What principle should be followed when granting permissions to identities in Azure Functions?
A:: When granting permissions to identities in Azure Functions, adhere to the principle of least privilege, granting the identity only required privileges.

Q:: Mention some considerations regarding permissions granted to identities in Azure Functions.
A:: Some permissions might be exposed by the target service that are not necessary for all contexts. Where possible, adhere to the principle of least privilege, granting the identity only required privileges.

### Part III - Develop solutions that use Blob storage

#### Chapter 1 - Explore Azure Blob storage

Q:: What is Azure Blob storage optimized for?
A:: Azure Blob storage is optimized for storing massive amounts of unstructured data, which includes data that doesn't adhere to a particular data model or definition, such as text or binary data.

Q:: Can you name some examples of unstructured data?
A:: Examples of unstructured data include serving images or documents directly to a browser, storing files for distributed access, streaming video and audio, writing to log files, and storing data for backup, restore, disaster recovery, and archiving.

Q:: What are the purposes for which Blob storage is designed?
A:: Blob storage is designed for serving images or documents directly to a browser, storing files for distributed access, streaming video and audio, writing to log files, storing data for backup and restore, disaster recovery, and archiving, as well as storing data for analysis by on-premises or Azure-hosted services.

Q:: How can users or client applications access objects in Blob storage?
A:: Objects in Blob storage can be accessed via HTTP/HTTPS, from anywhere in the world. Access is possible through the Azure Storage REST API, Azure PowerShell, Azure CLI, or an Azure Storage client library.

Q:: What is an Azure Storage account, and what does it provide?
A:: An Azure Storage account is the top-level container for all Azure Blob storage data. It provides a unique namespace for Azure Storage data that is accessible from anywhere in the world over HTTP or HTTPS.

Q:: How many performance levels of storage accounts does Azure Storage offer?
A:: Azure Storage offers two performance levels of storage accounts: standard and premium.

Q:: What are the types of storage accounts offered by Azure Storage?
A:: The types of storage accounts offered by Azure Storage are General-purpose v2 (Standard), Block blob (Premium), and Page blobs (Premium).

Q:: What distinguishes Premium storage accounts from Standard storage accounts?
A:: Premium storage accounts offer higher performance by using solid-state drives. Standard storage accounts, specifically General-purpose v2, are recommended for most scenarios using Azure Storage.

Q:: Which access tiers are available for block blob data in Azure Storage?
A:: The available access tiers for block blob data in Azure Storage are Hot, Cool, Cold, and Archive.

Q:: What is the Hot access tier optimized for?
A:: The Hot access tier is optimized for frequent access of objects in the storage account. It has the highest storage costs but the lowest access costs.

Q:: How long must data be stored in the Cool access tier before it becomes cost-effective?
A:: Data must be stored in the Cool access tier for at least 30 days before it becomes cost-effective.

Q:: What is the main advantage of the Archive access tier?
A:: The Archive access tier is the most cost-effective option for storing data, but accessing that data is more expensive than accessing data in the Hot or Cool tiers. It is optimized for data that can tolerate several hours of retrieval latency and remains in the Archive tier for at least 180 days.

Q:: Can you switch between different access tiers in Azure Storage?
A:: Yes, you can switch between different access tiers in Azure Storage at any time based on the change in the usage pattern of your data.

Q:: What are the three types of resources offered by Azure Blob storage?
A:: The three types of resources offered by Azure Blob storage are the storage account, a container in the storage account, and a blob in a container.

Q:: What does a storage account provide in Azure?
A:: A storage account provides a unique namespace in Azure for your data.

Q:: How does the combination of account name and Azure Storage blob endpoint form the base address for objects in a storage account?
A:: The combination of the account name and the Azure Storage blob endpoint forms the base address for the objects in your storage account by providing a unique address for each stored object.

Q:: Provide an example of a default endpoint for Blob storage.
A:: For example, if your storage account is named _mystorageaccount_, then the default endpoint for Blob storage is: `http://mystorageaccount.blob.core.windows.net`.

Q:: What is the purpose of a container in Azure Blob storage?
A:: A container organizes a set of blobs, similar to a directory in a file system.

Q:: How does a container organize data in Azure Blob storage?
A:: A container organizes data in Azure Blob storage by grouping together a set of blobs.

Q:: What are the rules for naming a container in Azure Blob storage?
A:: Container names can be between 3 and 63 characters long, must start with a letter or number, and can contain only lowercase letters, numbers, and the dash (-) character.

Q:: What is the URI format for a container in Azure Blob storage?
A:: The URI format for a container in Azure Blob storage is similar to: `https://myaccount.blob.core.windows.net/mycontainer`.

Q:: What are the three types of blobs supported by Azure Storage?
A:: The three types of blobs supported by Azure Storage are block blobs, append blobs, and page blobs.

Q:: What is the maximum size that block blobs can store?
A:: Block blobs can store up to about 190.7 TiB.

Q:: How are append blobs optimized compared to block blobs?
A:: Append blobs are optimized for append operations, making them ideal for scenarios such as logging data from virtual machines.

Q:: What types of files do page blobs store, and what is their maximum size?
A:: Page blobs store random access files up to 8 TB in size, serving as disks for Azure virtual machines.

Q:: Provide the URI format for a blob in Azure Blob storage.
A:: The URI format for a blob in Azure Blob storage is similar to: `https://myaccount.blob.core.windows.net/mycontainer/myblob`.

Q:: Can you provide an example of a URI for a blob that includes a virtual directory?
A:: An example of a URI for a blob that includes a virtual directory is: `https://myaccount.blob.core.windows.net/mycontainer/myvirtualdirectory/myblob`.

Q:: What are the primary security features provided by Azure Storage?
A:: Azure Storage provides a comprehensive set of security capabilities, including automatic encryption of all data, Role-Based Access Control (RBAC) support, Client-Side Encryption for securing data in transit, Azure Disk Encryption for OS and data disks used by Azure virtual machines, and delegated access using shared access signatures.

Q:: How does Azure Storage handle encryption of data at rest?
A:: Azure Storage automatically encrypts data when persisting it to the cloud using 256-bit AES encryption, ensuring strong security measures. This encryption is transparent to users and applications and is similar to BitLocker encryption on Windows.

Q:: Describe the encryption process used by Azure Storage.
A:: Azure Storage uses 256-bit AES encryption to encrypt data at rest, ensuring strong security measures. This encryption is transparent to users and applications and is FIPS 140-2 compliant.

Q:: Can the encryption feature in Azure Storage be disabled? Explain.
A:: No, the encryption feature in Azure Storage cannot be disabled. It is enabled by default for all new and existing storage accounts, ensuring data security without requiring modifications to code or applications.

Q:: What is FIPS 140-2 compliance, and how does it relate to Azure Storage encryption?
A:: FIPS 140-2 compliance is a standard for cryptographic modules, ensuring they meet specific security requirements. Azure Storage encryption adheres to FIPS 140-2 compliance by using 256-bit AES encryption, providing a high level of data security.

Q:: What types of data objects in Azure Storage are encrypted?
A:: All Azure Storage resources are encrypted, including blobs, disks, files, queues, tables, and object metadata.

Q:: Explain the options available for encryption key management in Azure Storage.
A:: Encryption key management in Azure Storage can be handled using Microsoft-managed keys or customer-managed keys. Customers can also provide their own keys for granular control over encryption and decryption operations.

Q:: What is the difference between customer-managed keys and customer-provided keys?
A:: Customer-managed keys are used to encrypt all data in all services within a storage account, while customer-provided keys offer granular control over encryption and decryption operations at the blob level.

Q:: Which Azure Storage services support customer-managed keys?
A:: Customer-managed keys are supported for Blob storage and Azure Files within Azure Storage.

Q:: What responsibilities does the customer have regarding key rotation when using customer-managed keys?
A:: Customers are responsible for key rotation when using customer-managed keys, ensuring the security and integrity of their data encryption.

Q:: How does the Azure portal compare to Azure Storage REST API in terms of key usage for customer-managed keys?
A:: The Azure portal provides a user-friendly interface for managing customer-managed keys, while the Azure Storage REST API offers programmatic access for key management operations.

Q:: Who has access to Microsoft-managed keys, customer-managed keys, and customer-provided keys respectively?
A:: Microsoft-managed keys are accessible only to Microsoft, customer-managed keys can be accessed by both Microsoft and the customer, and customer-provided keys are accessible only to the customer.

Q:: Is there any additional cost associated with Azure Storage encryption?
A:: No, there is no additional cost associated with Azure Storage encryption. It is enabled by default for all storage accounts without any extra charges.

Q:: How does Azure Storage encryption impact performance?
A:: Azure Storage encryption does not impact performance, ensuring that data remains secure without compromising system efficiency.

Q:: Can you explain the options for securing data in transit between an application and Azure Storage?
A:: Data in transit between an application and Azure Storage can be secured using Client-Side Encryption, HTTPS, or SMB 3.0, providing multiple layers of security for communication.

Q:: What types of content can be served directly from a storage container named _$web_?
A:: HTML, CSS, JavaScript, and image files can be served directly from a storage container named _$web_.

Q:: What are the advantages of hosting content in Azure Storage?
A:: Hosting content in Azure Storage enables the use of serverless architectures, including Azure Functions and other Platform as a service (PaaS) services.

Q:: What are the limitations of static websites in Azure Storage?
A:: Static websites in Azure Storage have limitations such as the inability to configure headers and lack of support for authentication and authorization (AuthN and AuthZ) features.

Q:: If you need to configure headers for a static website, what Azure service do you need to use?
A:: If you need to configure headers for a static website, you need to use Azure Content Delivery Network (Azure CDN).

Q:: What alternative service is recommended if authentication and authorization features are required for your scenario?
A:: If authentication and authorization features are required, consider using Azure Static Web Apps.

Q:: How do you enable static website hosting on a storage account?
A:: To enable static website hosting on a storage account, locate the storage account in the Azure portal, display the account overview, select **Static website**, enable static website hosting for the account, specify the default index and error pages, and save the configuration.

Q:: What container is automatically created when you enable static website hosting?
A:: When you enable static website hosting, Azure Storage automatically creates a container named _$web_.

Q:: What configuration options are available when enabling static website hosting?
A:: When enabling static website hosting, you can specify the default index document name and error document path.

Q:: What is the impact of modifying the public access level of the _$web_ container?
A:: Modifying the public access level of the _$web_ container does not impact the primary static website endpoint, but it does impact the primary blob service endpoint.

Q:: How does changing the public access level of the _$web_ container affect the primary static website endpoint?
A:: Changing the public access level of the _$web_ container does not change the level of public access to the primary static website endpoint.

Q:: Does disabling public access on a storage account affect static websites hosted in that storage account?
A:: Disabling public access on a storage account does not affect static websites hosted in that storage account.

Q:: What is the process for mapping a custom domain to a static website URL?
A:: The process involves enabling HTTP access for the custom domain, and for HTTPS, using Azure CDN as Azure Storage does not natively support HTTPS with custom domains.

Q:: What type of access does Azure Storage natively support for custom domains?
A:: Azure Storage natively supports HTTP access for custom domains.

Q:: What service is required to enable HTTPS for custom domains with Azure Storage?
A:: To enable HTTPS for custom domains with Azure Storage, Azure CDN needs to be used as Azure Storage does not natively support HTTPS with custom domains.

#### Chapter 2 - Manage the Azure Blob storage lifecycle

Q:: What are the different access tiers offered by Azure Blob storage?
A:: The different access tiers offered by Azure Blob storage are Hot, Cool, Cold, and Archive.

Q:: How does the Cool access tier differ from the Cold tier in Azure Blob storage?
A:: The Cool access tier is optimized for storing data that is infrequently accessed and stored for a minimum of 30 days, while the Cold tier is optimized for storing data that is infrequently accessed and stored for a minimum of 90 days.

Q:: Can you set the access tier for a blob after it has been uploaded?
A:: Yes, the access tier can be set for a blob during or after upload in Azure Blob storage.

Q:: What are the considerations for data stored in the Archive access tier?
A:: Data stored in the Archive access tier is stored offline and offers the lowest storage costs but also the highest access costs and latency in Azure Blob storage.

Q:: How do storage limits work in Azure Blob storage across different access tiers?
A:: Storage limits in Azure Blob storage are set at the account level and not per access tier. Users can choose to use all of their limit in one tier or across all three tiers.

Q:: What options does Azure Blob storage lifecycle management offer for managing data lifecycles?
A:: Azure Blob storage lifecycle management offers options to transition blobs to cooler storage tiers, delete blobs at the end of their lifecycles, define rules to be run at the storage account level, and apply rules to containers or a subset of blobs.

Q:: Can you describe a scenario where different access tiers might be used in Azure Blob storage?
A:: In a scenario where data gets frequent access during the early stages of the lifecycle but only occasionally after two weeks, and beyond the first month, the data set is rarely accessed, hot storage is suitable during the early stages, cool storage is appropriate for occasional access, and archive storage is best after the data ages over a month.

Q:: What limitations exist when trying to transition data in a premium block blob storage account to different tiers?
A:: Data stored in a premium block blob storage account cannot be tiered to Hot, Cool, or Archive using Set Blob Tier or Azure Blob Storage lifecycle management directly.

Q:: How can you move data from a premium block blob storage account to other tiers in Azure Blob storage?
A:: To move data from a premium block blob storage account to other tiers in Azure Blob storage, you must synchronously copy blobs from the block blob storage account to the Hot tier in a different account using the Put Block From URL API or a version of AzCopy that supports this API.

Q:: Why might you want to adjust storage tiers based on the age of data in Azure Blob storage?
A:: Adjusting storage tiers based on the age of data in Azure Blob storage allows users to optimize storage costs by using the least expensive storage options for their needs as data ages.

Q:: What constitutes a lifecycle management policy in Blob storage?
A:: A lifecycle management policy in Blob storage is a collection of rules in a JSON document that define actions to be taken on certain objects within a container based on specified conditions.

Q:: Describe the components of a rule within a lifecycle management policy.
A:: A rule within a lifecycle management policy consists of a name, an optional boolean to enable or disable the rule, a type (such as "Lifecycle"), and a definition that includes filter sets and action sets.

Q:: What does a rule definition consist of in a Blob storage lifecycle management policy?
A:: A rule definition in Blob storage lifecycle management policy includes filter sets and action sets. Filter sets restrict rule actions to specific objects within a container, while action sets apply tier or delete actions to the filtered objects.

Q:: How are rules organized within a policy in Blob storage lifecycle management?
A:: Rules within a policy in Blob storage lifecycle management are organized as an array of rule objects under the `rules` parameter.

Q:: Explain the significance of the `rules` parameter in a Blob storage lifecycle management policy.
A:: The `rules` parameter in a Blob storage lifecycle management policy is where the collection of rules defining actions on objects within a container is specified. At least one rule is required, and up to 100 rules can be defined in a policy.

Q:: What are the parameters associated with each rule in a Blob storage lifecycle management policy?
A:: Parameters associated with each rule in a Blob storage lifecycle management policy include `name`, `enabled`, `type`, and `definition`.

Q:: What is the purpose of the `enabled` parameter within a rule definition?
A:: The `enabled` parameter within a rule definition allows for the temporary disabling of a rule. Its default value is true if not set explicitly.

Q:: Identify the valid types that can be assigned to a rule in a Blob storage lifecycle management policy.
A:: The valid type that can be assigned to a rule in a Blob storage lifecycle management policy is "Lifecycle".

Q:: Describe the structure of a rule definition in Blob storage lifecycle management.
A:: A rule definition in Blob storage lifecycle management consists of filter sets and action sets. Filters limit rule actions to specific objects, while actions define the tier or delete actions to be applied to the filtered objects.

Q:: What are the functions of rule filters in Blob storage lifecycle management?
A:: Rule filters in Blob storage lifecycle management limit rule actions to a subset of blobs within the storage account based on specified criteria.

Q:: Enumerate the types of filters available for rule definition in Blob storage lifecycle management.
A:: Types of filters available for rule definition in Blob storage lifecycle management include `blobTypes`, `prefixMatch`, and `blobIndexMatch`.

Q:: How do filters impact rule actions within a Blob storage lifecycle management policy?
A:: Filters in Blob storage lifecycle management restrict rule actions to specific subsets of blobs within the storage account, ensuring that actions are applied only to relevant objects.

Q:: What actions can be applied to filtered blobs within a Blob storage lifecycle management policy?
A:: Actions that can be applied to filtered blobs within a Blob storage lifecycle management policy include tiering blobs to different storage tiers and deleting blobs or blob snapshots based on specified conditions.

Q:: Explain the conditions under which actions are executed in Blob storage lifecycle management.
A:: Actions in Blob storage lifecycle management are executed based on specified conditions, such as the age of the blob or blob snapshot, as defined in the action sets of the rule definitions.

Q:: How does Blob storage lifecycle management determine the age of blobs for action execution?
A:: Blob storage lifecycle management determines the age of blobs for action execution based on factors like the last modified time for base blobs and the snapshot creation time for blob snapshots.

Q:: Discuss the conditions under which different actions are applied to blobs in Blob storage lifecycle management.
A:: Different actions in Blob storage lifecycle management are applied to blobs based on conditions such as the number of days after modification or creation, as specified in the action sets of the rule definitions.

Q:: Can multiple actions be defined for the same blob in Blob storage lifecycle management? If so, how are they prioritized?
A:: Yes, multiple actions can be defined for the same blob in Blob storage lifecycle management. In such cases, the least expensive action is applied to the blob, considering factors like deletion being cheaper than tiering.

Q:: Describe the conditions associated with the `daysAfterLastTierChangeGreaterThan` parameter in Blob storage lifecycle management.
A:: The `daysAfterLastTierChangeGreaterThan` parameter in Blob storage lifecycle management applies only to `tierToArchive` actions and specifies the number of days after the last blob tier change time. This condition can be used in conjunction with the `daysAfterModificationGreaterThan` condition.

Q:: How can you implement Blob storage lifecycle policies in Azure?
A:: You can implement Blob storage lifecycle policies in Azure through methods such as the Azure portal, Azure PowerShell, Azure CLI, and REST APIs.

Q:: What are the methods available for adding, editing, or removing a policy in Blob storage?
A:: The methods available for adding, editing, or removing a policy in Blob storage include Azure portal, Azure PowerShell, Azure CLI, and REST APIs.

Q:: Describe the steps to add a policy through the Azure portal List view.
A:: To add a policy through the Azure portal List view, sign in to the Azure portal, select All resources, choose your storage account, navigate to Data management, select Lifecycle management, choose the List view tab, add a rule, fill out the Action set form fields, add an optional filter, review the policy settings, and finally, add the new policy.

Q:: Explain the steps involved in adding a policy through the Azure portal Code view.
A:: To add a policy through the Azure portal Code view, follow similar steps as the List view, but instead, select the Code view tab, provide a JSON example of the policy, and save the configuration.

Q:: How do you add a lifecycle management policy using Azure CLI?
A:: To add a lifecycle management policy using Azure CLI, you need to write the policy to a JSON file and then call the `az storage account management-policy create` command, specifying the storage account, policy file, and resource group.

Q:: What is required before calling the `az storage account management-policy create` command in Azure CLI?
A:: Before calling the `az storage account management-policy create` command in Azure CLI, you need to write the policy to a JSON file.

Q:: Can you perform partial updates when working with a lifecycle management policy?
A:: No, partial updates aren't supported when working with a lifecycle management policy.

Q:: Provide an example of a policy JSON used to move a block blob to the cool tier after a certain duration.
A:: 
```JSON
{
  "rules": [
    {
      "enabled": true,
      "name": "move-to-cool",
      "type": "Lifecycle",
      "definition": {
        "actions": {
          "baseBlob": {
            "tierToCool": {
              "daysAfterModificationGreaterThan": 30
            }
          }
        },
        "filters": {
          "blobTypes": [
            "blockBlob"
          ],
          "prefixMatch": [
            "sample-container/log"
          ]
        }
      }
    }
  ]
}
```

Q:: What are the criteria specified in the JSON example for moving blobs to the cool tier?
A:: Blobs are moved to the cool tier if they are block blobs and if their name begins with "sample-container/log" and they haven't been modified for 30 days.

Q:: What happens if blobs haven't been modified for 30 days according to the provided JSON example?
A:: According to the provided JSON example, if blobs haven't been modified for 30 days, they are moved to the cool tier.

Q:: What happens to a blob in the archive access tier?
A:: While a blob is in the archive access tier, it's considered to be offline and can't be read or modified.

Q:: Why is it necessary to rehydrate a blob from the archive tier?
A:: In order to read or modify data in an archived blob, you must first rehydrate the blob to an online tier, either the hot or cool tier.

Q:: What are the two options for rehydrating a blob stored in the archive tier?
A:: The two options for rehydrating a blob stored in the archive tier are:
1. Copy an archived blob to an online tier.
2. Change a blob's access tier to an online tier.

Q:: How can you rehydrate an archived blob by copying it to an online tier?
A:: You can rehydrate an archived blob by copying it to a new blob in the hot or cool tier using the Copy Blob or Copy Blob from URL operation.

Q:: What operation can you use to change a blob's access tier from archive to an online tier?
A:: You can change a blob's access tier from archive to an online tier using the Set Blob Tier operation.

Q:: How long can rehydrating a blob from the archive tier take?
A:: Rehydrating a blob from the archive tier can take several hours to complete.

Q:: What does Microsoft recommend regarding rehydrating larger blobs?
A:: Microsoft recommends rehydrating larger blobs for optimal performance.

Q:: What is the purpose of the `x-ms-rehydrate-priority` header?
A:: The purpose of the `x-ms-rehydrate-priority` header is to set the priority for the rehydration operation.

Q:: What are the priority options for rehydration?
A:: The priority options for rehydration are:
1. Standard priority
2. High priority

Q:: How can you check the rehydration priority while the operation is underway?
A:: You can check the rehydration priority while the operation is underway by calling Get Blob Properties to return the value of the `x-ms-rehydrate-priority` header.

Q:: What happens to the source blob when you copy an archived blob to an online tier?
A:: When you copy an archived blob to a new blob in an online tier, the source blob remains unmodified in the archive tier.

Q:: What restrictions apply when copying an archived blob to an online destination tier?
A:: You can only copy an archived blob to a destination within the same storage account, and you can't copy to a destination blob that is also in the archive tier.

Q:: Can you overwrite the source blob by copying to the same blob?
A:: No, you can't overwrite the source blob by copying to the same blob.

Q:: What are the supported destinations for copying an archived blob?
A:: The supported destinations for copying an archived blob include the hot tier, the cool tier, and within the same account, but they require blob rehydration.

Q:: What happens once a Set Blob Tier request is initiated?
A:: Once a Set Blob Tier request is initiated, it can't be canceled, and during the rehydration operation, the blob's access tier setting continues to show as archived until the rehydration process is complete.

Q:: What caution should you be aware of when changing a blob's tier?
A:: When changing a blob's tier, be aware that it doesn't affect its last modified time.

Q:: How does changing a blob's tier affect its last modified time?
A:: Changing a blob's tier doesn't affect its last modified time.

Q:: What potential scenario might occur if there's a lifecycle management policy in effect for the storage account after rehydration?
A:: If there is a lifecycle management policy in effect for the storage account, rehydrating a blob with Set Blob Tier can result in a scenario where the lifecycle policy moves the blob back to the archive tier after rehydration because the last modified time is beyond the threshold set for the policy.

#### Chapter 3 - Work with Azure Blob storage

Q:: What is the recommended version of the Azure Storage client library for new applications?
A:: Version 12.x is recommended for new applications.

Q:: What are the basic classes provided by the Azure Storage client library?
A:: The basic classes are: `BlobServiceClient`, `BlobContainerClient`, `BlobClient`, `AppendBlobClient`, and `BlockBlobClient`.

Q:: What does the `BlobServiceClient` class represent, and what operations does it provide?
A:: `BlobServiceClient` represents the storage account and provides operations to retrieve and configure account properties, and to work with blob containers in the storage account.

Q:: Describe the functionality of the `BlobContainerClient` class.
A:: `BlobContainerClient` represents a specific blob container and provides operations to work with the container and the blobs within it.

Q:: Explain the purpose of the `BlobClient` class and its operations.
A:: `BlobClient` represents a specific blob and provides general operations to work with the blob, including operations to upload, download, delete, and create snapshots.

Q:: What is the role of the `AppendBlobClient` class, and what operations does it support?
A:: `AppendBlobClient` represents an append blob and provides operations specific to append blobs, such as appending log data.

Q:: How does the `BlockBlobClient` class differ from other blob types, and what operations does it offer?
A:: `BlockBlobClient` represents a block blob and provides operations specific to block blobs, such as staging and then committing blocks of data.

Q:: Which packages contain classes for working with Blob Storage data resources?
A:: The packages are: `Azure.Storage.Blobs`, `Azure.Storage.Blobs.Specialized`, and `Azure.Storage.Blobs.Models`.

Q:: What is the purpose of the `Azure.Storage.Blobs` package?
A:: It contains the primary classes (client objects) for operating on the service, containers, and blobs.

Q:: What does the `Azure.Storage.Blobs.Specialized` package offer?
A:: It contains classes for performing operations specific to a blob type, such as block blobs.

Q:: What types of classes are included in the `Azure.Storage.Blobs.Models` package?
A:: `Azure.Storage.Blobs.Models` includes utility classes, structures, and enumeration types.

Q:: What is the initial step in working with any Azure resource using the SDK?
A:: Creating a client object.

Q:: How do you create a client object to interact with Azure storage service resources?
A:: By passing a URI referencing the endpoint to the client constructor.

Q:: What are the three types of resources you can interact with in the storage service?
A:: Storage accounts, containers, and blobs.

Q:: How is the endpoint passed to the client constructor when creating a client object?
A:: The endpoint can be constructed manually or queried for at runtime.

Q:: What is the purpose of using [DefaultAzureCredential](https://learn.microsoft.com/en-us/dotnet/api/azure.identity.defaultazurecredential) in the code samples?
A:: [DefaultAzureCredential](https://learn.microsoft.com/en-us/dotnet/api/azure.identity.defaultazurecredential) is used for authentication to Azure via a Microsoft Entra security principal.

Q:: What does a `BlobServiceClient` object allow your application to do?
A:: It allows interaction with resources at the storage account level.

Q:: How do you create a `BlobServiceClient` object in C#?
A:: By instantiating it with a URI and [DefaultAzureCredential](https://learn.microsoft.com/en-us/dotnet/api/azure.identity.defaultazurecredential).

Q:: What functionalities does a `BlobContainerClient` object provide?
A:: It allows interaction with a specific container resource, including methods to create, delete, or configure a container, and to list, upload, and delete blobs within it.

Q:: How can you create a `BlobContainerClient` object in C#?
A:: By either using a `BlobServiceClient` object or directly creating it with the container name appended to the URI.

Q:: When might you choose to create a `BlobContainerClient` object directly without using `BlobServiceClient`?
A:: When your work is narrowly scoped to a single container.

Q:: What functionalities does a `BlobClient` object provide?
A:: It allows interaction with a specific blob resource.

Q:: How can you create a `BlobClient` object in C#?
A:: By obtaining it from a service client or container client using the appropriate methods.

Q:: What are system properties in Blob storage, and how are they managed in .NET?
A:: System properties in Blob storage represent properties existing on each Blob storage resource. In .NET, the Azure Storage client library maintains these properties. Some system properties can be read or set, while others are read-only. Under the covers, certain system properties correspond to standard HTTP headers.

Q:: Explain the concept of user-defined metadata in Blob storage and its relevance in .NET.
A:: User-defined metadata in Blob storage consists of one or more name-value pairs specified for a Blob storage resource. In .NET, you can use metadata to store additional values with the resource. Metadata values are for your own purposes and do not affect how the resource behaves.

Q:: How can you retrieve container properties using the `BlobContainerClient` class in .NET?
A:: To retrieve container properties in .NET, you can call either the `GetProperties` or `GetPropertiesAsync` method of the `BlobContainerClient` class.

Q:: Provide a code example demonstrating the retrieval of container properties asynchronously in .NET.
A::
```csharp
private static async Task ReadContainerPropertiesAsync(BlobContainerClient container)
{
    try
    {
        // Fetch some container properties and write out their values.
        var properties = await container.GetPropertiesAsync();
        Console.WriteLine($"Properties for container {container.Uri}");
        Console.WriteLine($"Public access level: {properties.Value.PublicAccess}");
        Console.WriteLine($"Last modified time in UTC: {properties.Value.LastModified}");
    }
    catch (RequestFailedException e)
    {
        Console.WriteLine($"HTTP error code {e.Status}: {e.ErrorCode}");
        Console.WriteLine(e.Message);
        Console.ReadLine();
    }
}
```

Q:: How do you set metadata on a container in Blob storage using .NET?
A:: To set metadata on a container in Blob storage using .NET, you add name-value pairs to an `IDictionary` object and then call either the `SetMetadata` or `SetMetadataAsync` method of the `BlobContainerClient` class to write the values.

Q:: Explain the requirements for metadata names and values in Blob storage when using .NET.
A:: Metadata names in Blob storage must conform to the naming conventions for C# identifiers. Names must be valid HTTP header names and valid C# identifiers, may contain only ASCII characters, and should be treated as case-insensitive. Metadata values containing non-ASCII characters should be Base64-encoded or URL-encoded.

Q:: Describe the behavior of Blob storage when multiple metadata headers with the same name are submitted for a resource.
A:: Blob storage comma-separates and concatenates the values of metadata headers with the same name if two or more headers with the same name are submitted for a resource. The HTTP response code returned is `200 (OK)`.

Q:: What methods are used to retrieve metadata along with properties from a container in .NET?
A:: In .NET, the `GetProperties` and `GetPropertiesAsync` methods are used to retrieve metadata along with properties from a container.

Q:: Provide a code example illustrating the retrieval of metadata from a container asynchronously in .NET.
A::
```csharp
public static async Task ReadContainerMetadataAsync(BlobContainerClient container)
{
    try
    {
        var properties = await container.GetPropertiesAsync();

        // Enumerate the container's metadata.
        Console.WriteLine("Container metadata:");
        foreach (var metadataItem in properties.Value.Metadata)
        {
            Console.WriteLine($"\tKey: {metadataItem.Key}");
            Console.WriteLine($"\tValue: {metadataItem.Value}");
        }
    }
    catch (RequestFailedException e)
    {
        Console.WriteLine($"HTTP error code {e.Status}: {e.ErrorCode}");
        Console.WriteLine(e.Message);
        Console.ReadLine();
    }
}
```

Q:: Discuss the importance of error handling when working with container properties and metadata in .NET, including handling `RequestFailedException`.
A:: Error handling is crucial when working with container properties and metadata in .NET. The `RequestFailedException` class helps capture exceptions that may occur during operations like fetching properties or metadata. Proper error handling ensures graceful degradation of application behavior and enhances overall reliability and resilience.

Q:: What are metadata headers in the context of containers and blobs?
A:: Metadata headers in the context of containers and blobs are custom metadata represented as HTTP headers.

Q:: Describe the format for metadata headers.
A:: Metadata headers are represented as name/value pairs in the format: x-ms-meta-name:string-value.

Q:: What rules must metadata names adhere to, starting from version 2009-09-19?
A:: Starting from version 2009-09-19, metadata names must adhere to the naming rules for C# identifiers.

Q:: Explain the case sensitivity of metadata names.
A:: Metadata names are case-insensitive when set or read, although they preserve the case with which they were created.

Q:: What happens if multiple metadata headers with the same name are submitted for a resource?
A:: If multiple metadata headers with the same name are submitted for a resource, the Blob service returns status code 400 (Bad Request).

Q:: What is the maximum size limit for all metadata pairs?
A:: The total size of all metadata pairs can be up to 8KB in size.

Q:: How are metadata name/value pairs treated in terms of HTTP headers?
A:: Metadata name/value pairs are treated as valid HTTP headers and adhere to all restrictions governing HTTP headers.

Q:: What operations can be performed on metadata for blob or container resources?
A:: Metadata for blob or container resources can be retrieved or set directly, without altering the content of the resource.

Q:: What is the difference between the GET and HEAD operations concerning metadata retrieval?
A:: Both GET and HEAD operations retrieve metadata headers for the specified container or blob. However, they do not return a response body.

Q:: What URI syntax is used to retrieve metadata headers for a container?
A:: The URI syntax for retrieving metadata headers on a container is: GET/HEAD https://myaccount.blob.core.windows.net/mycontainer?restype=container.

Q:: Explain how metadata headers are set using the PUT operation.
A:: The PUT operation sets metadata headers on the specified container or blob, overwriting any existing metadata on the resource.

Q:: What happens when the PUT operation is called without any headers on the request?
A:: Calling PUT without any headers on the request clears all existing metadata on the resource.

Q:: What are the standard HTTP properties supported on containers?
A:: The standard HTTP properties supported on containers include: ETag and Last-Modified.

Q:: List the standard HTTP headers supported on blobs.
A:: The standard HTTP headers supported on blobs include: ETag, Last-Modified, Content-Length, Content-Type, Content-MD5, Content-Encoding, Content-Language, Cache-Control, Origin, and Range.

Q:: Differentiate between metadata headers and property headers in terms of naming conventions.
A:: Metadata headers are named with the prefix x-ms-meta- and a custom name, while property headers use standard HTTP header names specified in the HTTP/1.1 protocol specification.

### Part IV - Develop solutions that use Azure Cosmos DB

#### Chapter 1 - Explore Azure Cosmos DB

Q:: What is Azure Cosmos DB designed to provide?
A:: Azure Cosmos DB is designed to provide low latency, elastic scalability of throughput, well-defined semantics for data consistency, and high availability.

Q:: How can you configure your databases with Azure Cosmos DB?
A:: You can configure your databases to be globally distributed and available in any of the Azure regions. To lower the latency, place the data close to where your users are. Choosing the required regions depends on the global reach of your application and where your users are located.

Q:: What benefits does global distribution offer with Azure Cosmos DB?
A:: Global distribution offers benefits such as unlimited elastic write and read scalability, 99.999% read and write availability worldwide, and guaranteed reads and writes served in less than 10 milliseconds at the 99th percentile.

Q:: Explain the multi-master replication protocol in Azure Cosmos DB.
A:: With its novel multi-master replication protocol, every region supports both writes and reads. The multi-master capability enables near real-time reads and writes against all the regions chosen for the database, with Azure Cosmos DB internally handling the data replication between regions with consistency level guarantees.

Q:: What are some advantages of running a database in multiple regions worldwide with Azure Cosmos DB?
A:: Running a database in multiple regions worldwide increases the availability of a database. If one region is unavailable, other regions automatically handle application requests. Azure Cosmos DB offers 99.999% read and write availability for multi-region databases.

Q:: How does Azure Cosmos DB handle data replication between regions?
A:: Azure Cosmos DB internally handles the data replication between regions with consistency level guarantees of the level you've selected.

Q:: What level of read and write availability does Azure Cosmos DB offer for multi-region databases?
A:: Azure Cosmos DB offers 99.999% read and write availability for multi-region databases.

Q:: Can you add or remove regions associated with your Azure Cosmos DB account without pausing or redeploying your application?
A:: Yes, with Azure Cosmos DB, you can add or remove the regions associated with your account at any time without pausing or redeploying your application.

Q:: What is the fundamental unit of global distribution and high availability in Azure Cosmos DB?
A:: The Azure Cosmos DB account is the fundamental unit of global distribution and high availability.

Q:: How can you manage an Azure Cosmos DB account?
A:: You can manage an account by using the Azure portal or the Azure CLI, or by using different language-specific SDKs.

Q:: How can you globally distribute your data and throughput in Azure Cosmos DB?
A:: You can add and remove Azure regions to your account at any time for globally distributing your data and throughput across multiple Azure regions.

Q:: What is the maximum number of Azure Cosmos DB accounts you can create under an Azure subscription by default?
A:: You can create a maximum of 50 Azure Cosmos DB accounts under an Azure subscription by default.

Q:: What are the elements in an Azure Cosmos DB account?
A:: The elements include databases, containers, and items.

Q:: Describe the hierarchy of different entities in an Azure Cosmos DB account.
A:: Azure Cosmos DB accounts are at the top, databases are grouped under accounts, and containers are grouped under databases.

Q:: What is the fundamental unit of scalability in Azure Cosmos DB?
A:: An Azure Cosmos DB container is the fundamental unit of scalability.

Q:: How does Azure Cosmos DB transparently partition containers?
A:: Azure Cosmos DB transparently partitions containers using the logical partition key specified to elastically scale provisioned throughput and storage.

Q:: How many Azure Cosmos DB databases can you create under your account?
A:: You can create one or multiple Azure Cosmos DB databases under your account.

Q:: What is an Azure Cosmos DB container analogous to?
A:: A database is analogous to a namespace in Azure Cosmos DB.

Q:: How are items added to an Azure Cosmos DB container grouped?
A:: Items added to a container are automatically grouped into logical partitions, which are distributed across physical partitions based on the partition key.

Q:: What are the two modes of throughput configuration when creating a container in Azure Cosmos DB?
A:: The two modes are dedicated provisioned throughput mode and shared provisioned throughput mode.

Q:: Describe the dedicated provisioned throughput mode.
A:: In the dedicated provisioned throughput mode, the throughput provisioned on a container is exclusively reserved for that container and backed by SLAs.

Q:: Explain the shared provisioned throughput mode.
A:: In the shared provisioned throughput mode, containers share the provisioned throughput with others in the same database, excluding containers with dedicated provisioned throughput.

Q:: What is a schema-agnostic container of items in Azure Cosmos DB?
A:: A container is a schema-agnostic container of items in Azure Cosmos DB.

Q:: How are items indexed by default in an Azure Cosmos DB container?
A:: By default, all items added to a container are automatically indexed without requiring explicit index or schema management.

Q:: What can an Azure Cosmos DB item represent, depending on the API used?
A:: Depending on the API used, an Azure Cosmos DB item can represent either a document in a collection, a row in a table, or a node or edge in a graph.

Q:: How does Azure Cosmos DB approach data consistency?
A:: Azure Cosmos DB approaches data consistency as a spectrum of choices instead of two extremes.

Q:: What are the extremes of the consistency spectrum in Azure Cosmos DB?
A:: The extremes of the consistency spectrum in Azure Cosmos DB are strong consistency and eventual consistency.

Q:: How does Azure Cosmos DB offer consistency levels?
A:: Azure Cosmos DB offers five well-defined levels of consistency.

Q:: Can you name the five well-defined consistency levels in Azure Cosmos DB from strongest to weakest?
A:: The five well-defined consistency levels in Azure Cosmos DB from strongest to weakest are: Strong, Bounded staleness, Session, Consistent prefix, and Eventual.

Q:: What tradeoffs do developers make when choosing different consistency levels in Azure Cosmos DB?
A:: Developers make availability and performance tradeoffs when choosing different consistency levels in Azure Cosmos DB.

Q:: What does the image in the text illustrate?
A:: The image in the text illustrates the different consistency levels as a spectrum.

Q:: Are the consistency levels in Azure Cosmos DB region-agnostic?
A:: Yes, the consistency levels in Azure Cosmos DB are region-agnostic.

Q:: What is the scope of read consistency in Azure Cosmos DB?
A:: Read consistency in Azure Cosmos DB applies to a single read operation scoped within a partition-key range or a logical partition.

Q:: Who can issue a read operation in Azure Cosmos DB?
A:: A read operation in Azure Cosmos DB can be issued by a remote client or a stored procedure.

Q:: Is consistency guaranteed for all operations regardless of various factors in Azure Cosmos DB?
A:: Yes, consistency is guaranteed for all operations regardless of the region from which the reads and writes are served, the number of regions associated with your Azure Cosmos DB account, or whether your account is configured with a single or multiple write regions.

Q:: How can you configure the default consistency level in Azure Cosmos DB?
A:: You can configure the default consistency level on your Azure Cosmos DB account at any time.

Q:: What is the scope of read consistency in Azure Cosmos DB?
A:: Read consistency applies to a single read operation scoped within a logical partition.

Q:: What guarantees does Azure Cosmos DB provide for read requests based on the chosen consistency level?
A:: Azure Cosmos DB guarantees that 100 percent of read requests meet the consistency guarantee for the consistency level chosen.

Q:: Define strong consistency in Azure Cosmos DB.
A:: Strong consistency offers a linearizability guarantee.

Q:: What is the key guarantee provided by strong consistency?
A:: The reads are guaranteed to return the most recent committed version of an item.

Q:: Describe bounded staleness consistency in Azure Cosmos DB.
A:: In bounded staleness consistency, the reads are guaranteed to honor the consistent-prefix guarantee.

Q:: What are the configurable parameters for staleness in bounded staleness consistency?
A:: The number of versions (K) of the item and The time interval (T) reads might lag behind the writes.

Q:: What are the minimum values for K and T in bounded staleness consistency for a single region account?
A:: For a single region account, the minimum value of K and T is 10 write operations or 5 seconds.

Q:: How does session consistency work in Azure Cosmos DB?
A:: In session consistency, within a single client session reads are guaranteed to honor the consistent-prefix, monotonic reads, monotonic writes, read-your-writes, and write-follows-reads guarantees.

Q:: List the guarantees provided by session consistency within a single client session.
A:: Consistent-prefix, monotonic reads, monotonic writes, read-your-writes, and write-follows-reads guarantees.

Q:: Explain the concept of consistent prefix consistency in Azure Cosmos DB.
A:: In consistent prefix, updates made as single document writes see eventual consistency.

Q:: What is the behavior of write operations within a transaction in consistent prefix consistency?
A:: Write operations within a transaction of multiple documents are always visible together.

Q:: What is eventual consistency in Azure Cosmos DB?
A:: In eventual consistency, there's no ordering guarantee for reads.

Q:: Describe the characteristics of eventual consistency.
A:: Eventual consistency is the weakest form of consistency because a client may read the values that are older than the ones it read before.

Q:: When is eventual consistency considered ideal in an application?
A:: Eventual consistency is ideal where the application doesn't require any ordering guarantees.

Q:: What are the supported APIs in Azure Cosmos DB?
A:: Azure Cosmos DB offers multiple database APIs, which include: Azure Cosmos DB for NoSQL, Azure Cosmos DB for MongoDB, Azure Cosmos DB for PostgreSQL, Azure Cosmos DB for Apache Cassandra, Azure Cosmos DB for Table, Azure Cosmos DB for Apache Gremlin.

Q:: What are the considerations when choosing an API other than NoSQL?
A:: Considerations for choosing an API other than NoSQL include having existing MongoDB, PostgreSQL, Cassandra, or Gremlin applications, not wanting to rewrite the entire data access layer, and wanting to utilize the open-source developer ecosystem, client-drivers, expertise, and resources for your database.

Q:: What features does the API for NoSQL offer?
A:: The Azure Cosmos DB API for NoSQL stores data in document format and provides full control over the interface, service, and SDK client libraries. New features rolled out to Azure Cosmos DB are first available on API for NoSQL accounts, which also support querying items using the Structured Query Language (SQL) syntax.

Q:: How does the API for MongoDB store data?
A:: The Azure Cosmos DB API for MongoDB stores data in a document structure via BSON format. While it's compatible with MongoDB wire protocol, it doesn't use any native MongoDB related code.

Q:: Why would someone choose the API for PostgreSQL in Azure Cosmos DB?
A:: The API for PostgreSQL in Azure Cosmos DB is a managed service for running PostgreSQL at any scale, with the Citus open source superpower of distributed tables. It stores data either on a single node or distributed in a multi-node configuration.

Q:: How does the API for Apache Cassandra store data?
A:: The Azure Cosmos DB API for Cassandra stores data in a column-oriented schema. It aligns with the distributed, horizontally scaling approach of Apache Cassandra while being wire protocol compatible with native Apache Cassandra.

Q:: What are the scenarios suitable for using the API for Apache Gremlin?
A:: The API for Apache Gremlin is suitable for scenarios involving dynamic data, complex relations, data too complex to be modeled with relational databases, and for utilizing the existing Gremlin ecosystem and skills.

Q:: In what format does the API for Table store data?
A:: The Azure Cosmos DB API for Table stores data in key/value format.

Q:: What are the limitations of using Azure Table storage compared to the API for Table in Azure Cosmos DB?
A:: Azure Table storage may have limitations in latency, scaling, throughput, global distribution, index management, and low query performance compared to the API for Table in Azure Cosmos DB, which overcomes these limitations. The API for Table only supports OLTP scenarios.

Q:: Which API is native to Azure Cosmos DB?
A:: The API for NoSQL is native to Azure Cosmos DB.

Q:: What are request units (RUs) in Azure Cosmos DB?
A:: Request units (RUs) in Azure Cosmos DB represent the system resources such as CPU, IOPS, and memory required to perform the database operations supported by Azure Cosmos DB.

Q:: How are database operations costed in Azure Cosmos DB?
A:: All database operations in Azure Cosmos DB are normalized and expressed in terms of request units (RUs), which represent the cost of the system resources needed to perform those operations.

Q:: What does 1RU represent in Azure Cosmos DB?
A:: In Azure Cosmos DB, 1RU represents the cost to perform a point read operation, which involves fetching a single item by its ID and partition key value for a 1-KB item.

Q:: How does Azure Cosmos DB measure the cost of database operations?
A:: Azure Cosmos DB measures the cost of database operations in request units (RUs). Whether the operation is a write, point read, or query, costs are measured in RUs.

Q:: Describe the three modes in which you can create an Azure Cosmos DB account.
A:: The three modes for creating an Azure Cosmos DB account are: Provisioned throughput mode, Serverless mode, and Autoscale mode.

Q:: What is provisioned throughput mode in Azure Cosmos DB?
A:: Provisioned throughput mode in Azure Cosmos DB requires you to provision the number of RUs for your application on a per-second basis in increments of 100 RUs per second. You can scale the provisioned throughput at any time programmatically or using the Azure portal.

Q:: Explain serverless mode in Azure Cosmos DB.
A:: Serverless mode in Azure Cosmos DB allows you to create resources without provisioning any throughput. At the end of your billing period, you get billed for the number of request units consumed by your database operations.

Q:: What is autoscale mode in Azure Cosmos DB used for?
A:: Autoscale mode in Azure Cosmos DB allows you to automatically and instantly scale the throughput (RU/s) of your database or container based on its usage. This mode is suitable for mission-critical workloads with variable or unpredictable traffic patterns.

Q:: How do you scale provisioned throughput in Azure Cosmos DB?
A:: In Azure Cosmos DB, you can scale provisioned throughput by increasing or decreasing the number of RUs at any time in increments or decrements of 100 RUs. This can be done programmatically or through the Azure portal.

Q:: What is the billing model for serverless mode in Azure Cosmos DB?
A:: In serverless mode, you don't have to provision any throughput upfront. Instead, at the end of your billing period, you get billed for the number of request units consumed by your database operations.

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
