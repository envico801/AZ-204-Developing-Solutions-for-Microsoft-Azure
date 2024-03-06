========== Question ==========  

### What are the potential benefits of using custom containers in App Service on Linux?  

========== Answer ==========  

If the runtime required by the application is not supported in the built-in
images, you can deploy it with a custom container. Custom containers place files
in the container filesystem instead of the content volume, potentially
benefiting apps that require heavy read-only access to content files.

========== Id ==========  
9

---

DECK INFO

TARGET DECK: EXAMPLE::EXAMPLE::MADSF - Az 204 developing solutions for microsoft azure - microsoft learn::Part I - Implement Azure App Service web apps::Chapter 1 - Explore Azure App Service

FILE TAGS: #EXAMPLE::#EXAMPLE::#MADSF-Az-204-developing-solutions-for-microsoft-azure-microsoft-learn::#Part-I-Implement-Azure-App-Service-web-apps::#Chapter-1-Explore-Azure-App-Service::#9-What-are-the-potential-benefits-of-using-c

Tags:

Reference:

Related:

```dataview
LIST
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
