========== Question ==========  

### How does scaling work for apps running in different App Service plans and pricing tiers?  

========== Answer ==========  

In the Free and Shared tiers, apps cannot scale out. In other tiers, all apps in
the same App Service plan run on all the configured VM instances and scale out
together based on the autoscale settings of the plan.

========== Id ==========  
29

---

DECK INFO

TARGET DECK: EXAMPLE::EXAMPLE::MADSF - Az 204 developing solutions for microsoft azure - microsoft learn::Part I - Implement Azure App Service web apps::Chapter 1 - Explore Azure App Service

FILE TAGS: #EXAMPLE::#EXAMPLE::#MADSF-Az-204-developing-solutions-for-microsoft-azure-microsoft-learn::#Part-I-Implement-Azure-App-Service-web-apps::#Chapter-1-Explore-Azure-App-Service::#29-How-does-scaling-work-for-apps-running-in

Tags:

Reference:

Related:

```dataview
LIST
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
