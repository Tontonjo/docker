
## Sources:  
https://hub.docker.com/r/ahaen/azuread-ldap-wrapper  
https://github.com/ahaenggli/AzureAD-LDAP-wrapper  
https://ahaenggli.github.io/AzureAD-LDAP-wrapper/installation/create-azuread-application/  

```shell
docker run -d \
--name=ldap-wrapper \
--restart=unless-stopped \
-p 389:13389 \
-v /path/to/data:/app/.cache \
-e TZ="Europe/Zurich" \
-e AZURE_TENANTID="tenantid" \
-e AZURE_APP_ID="appid" \
-e AZURE_APP_SECRET="appsecret" \
-e LDAP_DOMAIN="domain.tld" \
-e LDAP_BASEDN="dc=domain,dc=tld" \
-e LDAP_BINDUSER="ldapsearch|*secretldapsearch123*||root|*secretroot*" \
-e LDAP_DEBUG="false" \
-e GRAPH_IGNORE_MFA_ERRORS="false" \
-e LDAP_SAMBANTPWD_MAXCACHETIME="0" \
-e DSM7="true" \
ahaen/azuread-ldap-wrapper:latest
```
