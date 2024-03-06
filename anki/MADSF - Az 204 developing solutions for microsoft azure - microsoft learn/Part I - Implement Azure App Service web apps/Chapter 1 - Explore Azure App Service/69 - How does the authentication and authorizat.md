========== Question ==========  

### How does the authentication and authorization process differ between client-directed and server-directed flows?  

========== Answer ==========  

In the server-directed flow, the application delegates federated sign-in to App
Service, which redirects the client to the provider's login page. In the
client-directed flow, the application signs users in directly using the
provider's SDK and submits the authentication token to App Service for
validation.

========== Id ==========  
69

---

DECK INFO

TARGET DECK: EXAMPLE::EXAMPLE::MADSF - Az 204 developing solutions for microsoft azure - microsoft learn::Part I - Implement Azure App Service web apps::Chapter 1 - Explore Azure App Service

FILE TAGS: #EXAMPLE::#EXAMPLE::#MADSF-Az-204-developing-solutions-for-microsoft-azure-microsoft-learn::#Part-I-Implement-Azure-App-Service-web-apps::#Chapter-1-Explore-Azure-App-Service::#69-How-does-the-authentication-and-authorizat

Tags:

Reference:

Related:

```dataview
LIST
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
