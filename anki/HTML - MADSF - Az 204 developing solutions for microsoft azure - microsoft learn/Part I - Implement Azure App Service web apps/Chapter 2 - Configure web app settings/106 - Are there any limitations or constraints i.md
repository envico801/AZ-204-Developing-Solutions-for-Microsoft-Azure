==================== Question ====================  

### Are there any limitations or constraints in the way application settings are configured or accessed in App Service?  

==================== Answer ====================  

For Linux apps and custom containers, any nested JSON key structure in the app setting name (e.g., ApplicationInsights:InstrumentationKey) needs to be configured as ApplicationInsights\_\_InstrumentationKey, with colons replaced by double underscores.

==================== Id ====================  
106

---

DECK INFO

TARGET DECK: EXAMPLE::EXAMPLE::MADSF - Az 204 developing solutions for microsoft azure - microsoft learn::Part I - Implement Azure App Service web apps::Chapter 2 - Configure web app settings

FILE TAGS: #EXAMPLE::#EXAMPLE::#MADSF-Az-204-developing-solutions-for-microsoft-azure-microsoft-learn::#Part-I-Implement-Azure-App-Service-web-apps::#Chapter-2-Configure-web-app-settings::#106-Are-there-any-limitations-or-constraints-i

Tags:

Reference:

Related:

```dataview
LIST
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
