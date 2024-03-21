========== Question ==========  

### What command can you use in Azure CLI to retrieve the outbound IP addresses of your app?  

========== Answer ==========  

You can use the following Azure CLI command to retrieve outbound IP addresses:
`az webapp show --resource-group <group_name> --name <app_name> --query outboundIpAddresses --output tsv`.

========== Id ==========  
68

---

DECK INFO

TARGET DECK: EXAMPLE::EXAMPLE::MADSF - Az 204 developing solutions for microsoft azure - microsoft learn::Part I - Implement Azure App Service web apps::Chapter 1 - Explore Azure App Service

FILE TAGS: #EXAMPLE::#EXAMPLE::#MADSF-Az-204-developing-solutions-for-microsoft-azure-microsoft-learn::#Part-I-Implement-Azure-App-Service-web-apps::#Chapter-1-Explore-Azure-App-Service::#68-What-command-can-you-use-in-azure-cli-to-r

Tags:

Reference:

Related:

```dataview
LIST
where file.name = this.file.name
```

QUESTION STATUS: Not safe to store
