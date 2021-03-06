---
services: key-vault
platforms: java
author: tiffanyachen
---

# Vnet/IP ACL sample for Azure Key Vault using the Azure Java SDK

This sample repo demonstrates how to create an Azure Key Vault with access limited to specific IP ranges and Azure Virtual Networks.

## Prerequisites
- Java 1.7+
- An Azure Service Principal, through [Azure CLI](http://azure.microsoft.com/documentation/articles/resource-group-authenticate-service-principal-cli/),
[PowerShell](http://azure.microsoft.com/documentation/articles/resource-group-authenticate-service-principal/)
or [Azure Portal](http://azure.microsoft.com/documentation/articles/resource-group-create-service-principal-portal/).

## Running the samples
1. If not installed, install [Java](https://www.java.com/en/download/help/download_options.xml).

2. Clone the repository.
```
git clone https://github.com/Azure-Samples/key-vault-java-authentication.git
```
3. Create an Azure service principal, using
[Azure CLI](http://azure.microsoft.com/documentation/articles/resource-group-authenticate-service-principal-cli/),
[PowerShell](http://azure.microsoft.com/documentation/articles/resource-group-authenticate-service-principal/)
or [Azure Portal](http://azure.microsoft.com/documentation/articles/resource-group-create-service-principal-portal/).
Note that if you wish to authenticate with the certificate authenticator the certificate should be saved locally.

4. Add the following values to the pom.xml in the configurations for the exec-maven-plugin.
```
<systemProperties>
        <systemProperty>
                <key>AZURE_TENANT_ID</key>
                <value>{AZURE_TENANT_ID}</value>
        </systemProperty>
        <systemProperty>
                <key>AZURE_CLIENT_ID</key>
                <value>{AZURE_CLIENT_ID}</value>
        </systemProperty>
        <systemProperty>
                <key>AZURE_CLIENT_SECRET</key>
                <value>{AZURE_CLIENT_SECRET}</value>
        </systemProperty>
        <systemProperty>
                <key>AZURE_OBJECT_ID</key>
                <value>{AZURE_OBJECT_ID}</value>
        </systemProperty>
<systemProperties>
```

AZURE_TENANT_ID, AZURE_CLIENT_ID, and AZURE_CLIENT_SECRET must be set for general Azure authentication.

5. Run ```mvn clean compile exec:java``` for a full run-through.

## More information

* [What is Key Vault?](https://docs.microsoft.com/en-us/azure/key-vault/key-vault-whatis)
* [Get started with Azure Key Vault](https://docs.microsoft.com/en-us/azure/key-vault/key-vault-get-started)
* [Azure Key Vault General Documentation](https://docs.microsoft.com/en-us/azure/key-vault/)
* [Azure Key Vault REST API Reference](https://docs.microsoft.com/en-us/rest/api/keyvault/)
* [Azure SDK for Java Documentation](https://docs.microsoft.com/en-us/java/api/overview/azure/keyvault)
* [Azure Active Directory Documenation](https://docs.microsoft.com/en-us/azure/active-directory/)
