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