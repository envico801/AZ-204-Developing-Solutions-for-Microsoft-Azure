==================== Question ====================  

### How can you find all possible outbound IP addresses for your app, regardless of pricing tiers, using Azure CLI?  

==================== Answer ====================  

You can find all possible outbound IP addresses for your app, regardless of pricing tiers, using the Azure CLI command: `az webapp show --resource-group <group_name> --name <app_name> --query possibleOutboundIpAddresses --output tsv`.

==================== Id ====================  
70

---

DECK INFO

TARGET DECK: EXAMPLE::EXAMPLE::MADSF - Az 204 developing solutions for microsoft azure - microsoft learn::Part I - Implement Azure App Service web apps::Chapter 1 - Explore Azure App Service

FILE TAGS: #EXAMPLE::#EXAMPLE::#MADSF-Az-204-developing-solutions-for-microsoft-azure-microsoft-learn::#Part-I-Implement-Azure-App-Service-web-apps::#Chapter-1-Explore-Azure-App-Service::#70-How-can-you-find-all-possible-outbound-ip

Tags:

Reference:

Related:

```dataview
LIST
where file.name = this.file.name
```

QUESTION STATUS: Not safe to store
