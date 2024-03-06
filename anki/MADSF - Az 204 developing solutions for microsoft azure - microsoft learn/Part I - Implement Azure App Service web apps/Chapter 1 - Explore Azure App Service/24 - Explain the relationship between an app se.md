========== Question ==========  

### Explain the relationship between an App Service plan and the apps running within it.  

========== Answer ==========  

An app runs on all the VM instances configured in the App Service plan. If
multiple apps are in the same App Service plan, they share the same VM
instances. Deployment slots, diagnostic logs, backups, and WebJobs also utilize
resources from the same VM instances.

========== Id ==========  
24

---

DECK INFO

TARGET DECK: EXAMPLE::EXAMPLE::MADSF - Az 204 developing solutions for microsoft azure - microsoft learn::Part I - Implement Azure App Service web apps::Chapter 1 - Explore Azure App Service

FILE TAGS: #EXAMPLE::#EXAMPLE::#MADSF-Az-204-developing-solutions-for-microsoft-azure-microsoft-learn::#Part-I-Implement-Azure-App-Service-web-apps::#Chapter-1-Explore-Azure-App-Service::#24-Explain-the-relationship-between-an-app-se

Tags:

Reference:

Related:

```dataview
LIST
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
