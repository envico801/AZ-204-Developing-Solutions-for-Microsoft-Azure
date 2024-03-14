========== Question ==========  

### How does the disk latency compare for files allocated on the **built-in content volume (Azure Storage)** versus the **container filesystem (custom container)** in App Service on Linux?  

========== Answer ==========  

There is higher disk latency for files allocated on **content volume** compared
to the **container filesystem**.

========== Id ==========  
16

---

DECK INFO

TARGET DECK: EXAMPLE::EXAMPLE::MADSF - Az 204 developing solutions for microsoft azure - microsoft learn::Part I - Implement Azure App Service web apps::Chapter 1 - Explore Azure App Service

FILE TAGS: #EXAMPLE::#EXAMPLE::#MADSF-Az-204-developing-solutions-for-microsoft-azure-microsoft-learn::#Part-I-Implement-Azure-App-Service-web-apps::#Chapter-1-Explore-Azure-App-Service::#16-How-does-the-disk-latency-compare-for-file

Tags:

Reference:

Related:

```dataview
LIST
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
