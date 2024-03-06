========== Question ==========  

### How does the storage volume for web content affect the performance of apps hosted on App Service on Linux?  

========== Answer ==========  

When deployed to built-in images, code and content are allocated a storage
volume backed by Azure Storage. The disk latency of this volume is higher and
more variable than the latency of the container filesystem, which may impact
performance for apps that require heavy read-only access to content files.

========== Id ==========  
10

---

DECK INFO

TARGET DECK: EXAMPLE::EXAMPLE::MADSF - Az 204 developing solutions for microsoft azure - microsoft learn::Part I - Implement Azure App Service web apps::Chapter 1 - Explore Azure App Service

FILE TAGS: #EXAMPLE::#EXAMPLE::#MADSF-Az-204-developing-solutions-for-microsoft-azure-microsoft-learn::#Part-I-Implement-Azure-App-Service-web-apps::#Chapter-1-Explore-Azure-App-Service::#10-How-does-the-storage-volume-for-web-conten

Tags:

Reference:

Related:

```dataview
LIST
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
