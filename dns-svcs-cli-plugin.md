---

copyright:
  years: 2019, 2020
lastupdated: "2020-04-22"

keywords: command line interface, cli, dns services

subcollection: dns-svcs-cli-plugin

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:term: .term}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:external: target="_blank" .external}
{:generic: data-hd-programlang="generic"}
{:download: .download}
{:DomainName: data-hd-keyref="DomainName"}


# {{site.data.keyword.dns_short}} CLI commands
{: #dns-services-cli-commands}

Follow these instructions to use the {{site.data.keyword.dns_full}} command-line interface (CLI).
{: shortdesc}

## Before you begin
{: #cli-ref-prereqs}

Complete these steps to use the {{site.data.keyword.dns_short}} CLI, which is implemented as an {{site.data.keyword.cloud_notm}} CLI plug-in. This plug-in provides you with the means to manage your service instance and its associated resources through a command-line user interface.

1. Install the [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli){: external}.
1. Install or update the **cloud-dns-services** plug-in to the {{site.data.keyword.cloud_notm}} CLI.

   To install the plug-in, enter the following command.

   ```
   ibmcloud plugin install cloud-dns-services
   ```
   {: pre}

   To update:

  ```
  ibmcloud plugin update cloud-dns-services
  ```
  {: pre}

  To view installed plugins and versions:

  ```
  ibmcloud plugin list
  ```
  {: pre}

---

## Instances
{: #resource-instance}

Manipulate DNS Services instances by using the following **instance** commands.

## ibmcloud dns instances
{: #list-dns-services-instances}

List all DNS Services instances.

```
   ibmcloud dns instances [--output FORMAT]
```

### Command option
{: #command-options-list-dns-services-instances}

  * **--output**<br />Specify output format. Currently, **json** is the only supported format.

## ibmcloud dns instance-target
{: #set-context-DNS-service-instance}

Set context service instance to operate.

```
   ibmcloud dns instance-target [INSTANCE] [--unset]
```

### Command options
{: #command-options-set-context-dns-service-instance}

* **INSTANCE**<br />The name or ID of a DNS Services instance. If it is present, set the context instance to operate; if not, show the current context instance.  
* **--unset**<br />Unset context instance.


## ibmcloud dns instance-create
{: #create-DNS-services-instance}

Create a DNS Services instance.

   Use `ibmcloud target -g RESOURCE_GROUP` to set the target resource group before creating DNS Services instance. Use `ibmcloud resource groups` to view the list of available resource groups.
   {: note}


```
   ibmcloud dns instance-create INSTANCE_NAME PLAN [--output FORMAT]
```

### Command options
{: #command-options-create-dns-svcs-instance}

   * **INSTANCE_NAME**<br />The name of the DNS Services instance.
   * **PLAN**<br />The name or ID of a service plan.
   * **--output**<br />Specify output format. Currently, **json** is the only supported format.

## ibmcloud dns instance-update
{: #update-DNS-services-instance}

Update a DNS Services instance.

```
   ibmcloud dns instance-update INSTANCE [--name NAME] [--plan PLAN] [--output FORMAT]
```

### Command options
{: #command-options-update-dns-svcs-instance}

   * **INSTANCE**<br />The name or ID of a DNS Services instance.
   * **--name**<br />The DNS Services instance name.
   * **--plan**<br />The name or ID of a DNS Services plan. Use `ibmcloud dns plans` to get available plans.
   * **--output**<br />Specify output format. Currently, **json** is the only supported format.


## ibmcloud dns instance-delete
{: #delete-DNS-services-instance}

Delete a DNS Services instance.

```
   ibmcloud dns instance-delete INSTANCE [--force] 
```

### Command options
{: #command-options-delete-dns-svcs-instance}

   * **INSTANCE**<br />The name or ID of a DNS Services instance.
   * **--force**<br />Delete an instance without prompting for confirmation.


## ibmcloud dns instance
{: #get-DNS-service-instance}

Show details of a DNS Services instance.

```
   ibmcloud dns instance INSTANCE [--output FORMAT]
```

### Command options
{: #command-options-get-dns-svcs-instance}

   * **INSTANCE**<br />The name or ID of a DNS Services instance.
   * **--output**<br />Specify output format, only JSON is supported.


## ibmcloud dns plans
{: #list-DNS-services-plans}

List all DNS Services instances.

```
   ibmcloud dns plans
```

## Zones
{: #zone}

Manipulate DNS zones by using the following **zone** commands.

## ibmcloud dns zone-create
{: #create-zone}

Create a DNS zone.

```
   ibmcloud dns zone-create ZONE_NAME [-d, --description DESC] [-l, --label LABEL] [-i, --instance INSTANCE_NAME] [--output FORMAT]
```

### Command options
{: #options-create-dns-svcs-zone}

   * **ZONE_NAME**<br />The name of the DNS zone.
   * **-d, --description**<br />The text describing the purpose of a DNS zone.
   * **-l, --label**<br />The label of a DNS zone.
   * **-i, --instance INSTANCE_NAME**<br />Instance name. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.

### Command output
{: #output-create-dns-svcs-zone}

  * ID                     
  * Created On         
  * Modified On
  * Instance ID  
  * Name                   
  * Description
  * State                
  * Label        

## ibmcloud dns zone
{: #get-zone}

Get the given DNS zone details.

```
   ibmcloud dns zone ZONE_ID [-i, --instance INSTANCE_NAME] [--output FORMAT]
```

### Command options
{: #options-get-zone}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **-i, --instance INSTANCE_NAME**<br />Instance name. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.

### Command output
{: #output-get-zone}
  * ID                     
  * Created On         
  * Modified On
  * Instance ID  
  * Name                   
  * Description
  * State                
  * Label     
  
## ibmcloud dns zone-update
{: #update-zone}

Update a DNS zone's description and label.

```
   ibmcloud dns zone-update ZONE_ID [-d, --description DESC] [-l, --label LABEL] [--instance INSTANCE_NAME] [--output FORMAT]
```

### Command options
{: #options-update-zone}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **-d, --description**<br />The text describing the purpose of a DNS zone.
   * **-l, --label**<br />The label of a DNS zone.
   * **-i, --instance INSTANCE_NAME**<br />Instance name. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.

### Command output
{: #output-update-zone}

  * ID                     
  * Created On         
  * Modified On
  * Instance ID  
  * Name                   
  * Description
  * State                
  * Label    

## ibmcloud dns zone-delete
{: #delete-zone}

Delete a DNS zone.

```
   ibmcloud dns zone-delete ZONE_ID [--force] [-i, --instance INSTANCE_NAME]
```

### Command options
{: #options-delete-zone}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **--force**<br />Delete a zone without prompting for confirmation.
   * **-i, --instance INSTANCE_NAME**<br />Instance name. If not set, the context instance specified by `ibmcloud dns instance-target` is used.

## ibmcloud dns zones
{: #list-zones}

List all DNS zones for a given service instance.

```
   ibmcloud dns zones [-i, --instance INSTANCE_NAME] [--output FORMAT]
```

### Command options
{: #options-list-zones}

   * **-i, --instance INSTANCE_NAME**<br />Instance name. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.

## Permitted networks
{: #permitted-network}

Manipulate permitted networks by using the following **permitted-network** commands.

## ibmcloud dns permitted-network-add
{: #add-permitted-network}

Add a permitted network for a given DNS zone.

```
   ibmcloud dns permitted-network-add ZONE_ID --vpc-crn VPC_CRN [--type TYPE] [-i, --instance INSTANCE_NAME] [--output FORMAT]
```

### Command options
{: #options-add-permitted-network}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **--type**<br />The permitted network type. Valid values: "vpc".
   * **--vpc-crn**<br />The CRN of VPC instance 
   * **-i, --instance INSTANCE_NAME**<br />Instance name. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.

### Command output
{: #output-add-permitted-network}

  * ID                     
  * Created On         
  * Modified On
  * Permitted Network data  
  * Type    

## ibmcloud dns permitted-network
{: #get-permitted-network}

Get the given permitted network details.

```
   ibmcloud dns permitted-network ZONE_ID PERMITTED_NETWORK_ID [-i, --instance INSTANCE_NAME] [--output FORMAT]
```

### Command options
{: #options-get-permitted-network}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **PERMITTED_NETWORK_ID**<br />The ID of the permitted network.
   * **-i, --instance INSTANCE_NAME**<br />Instance name. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.

### Command output
{: #output-get-permitted-network}

  * ID                     
  * Created On         
  * Modified On
  * Permitted Network data  
  * Type    
  

## ibmcloud dns permitted-network-remove
{: #Remove-permitted-network}

Remove a permitted network.

```
   ibmcloud dns permitted-network-remove ZONE_ID PERMITTED_NETWORK_ID [--force] [-i, --instance INSTANCE_NAME]
```

### Command options
{: #options-remove-permitted-network}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **PERMITTED_NETWORK_ID**<br />The ID of the permitted network.
   * **--force**<br />Remove a permitted network without prompting for confirmation.
   * **--instance INSTANCE_NAME**<br />Instance name. If not set, the context instance specified by `ibmcloud dns instance-target` is used.


## ibmcloud dns permitted-networks
{: #list-permitted-networks}

List permitted networks for a given zone.

```
   ibmcloud dns permitted-networks ZONE_ID [-i, --instance INSTANCE_NAME] [--output FORMAT]
```

### Command options
{: #options-list-permitted-networks}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **-i, --instance INSTANCE_NAME**<br />Instance name. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.

## Resource records
{: #resource-record}

Manipulate how the resource record performs using the following **resource-record** commands.

## ibmcloud dns resource-record-create
{: #create-resource-record}

Create a resource record for a given DNS zone.

```
   ibmcloud dns resource-record-create DNS_ZONE_ID (-r, --record-content @JSON_FILE | JSON_STRING) [-i, --instance INSTANCE_NAME | INSTANCE_ID] [--output FORMAT]
```
```sh
   ibmcloud dns resource-record-create DNS_ZONE_ID --type A --name NAME --ipv4 IP_ADDRESS [--ttl TTL]
   ibmcloud dns resource-record-create DNS_ZONE_ID --type AAAA --name NAME --ipv6 IP_ADDRESS [--ttl TTL]
   ibmcloud dns resource-record-create DNS_ZONE_ID --type CNAME --name NAME --cname CNAME [--ttl TTL]
   ibmcloud dns resource-record-create DNS_ZONE_ID --type PTR --name NAME --ptrdname PTRDNAME [--ttl TTL]
   ibmcloud dns resource-record-create DNS_ZONE_ID --type TXT --name NAME --text TEXT [--ttl TTL]
   ibmcloud dns resource-record-create DNS_ZONE_ID --type MX --name NAME --exchange EXCHANGE --preference PREFERENCE [--ttl TTL]
   ibmcloud dns resource-record-create DNS_ZONE_ID --type SRV --name NAME --service SERVICE --protocol PROTOCOL --priority PRIORITY --weight WEIGHT --port PORT --target TARGET  [--ttl TTL]
```
{: codeblock}

### Command options
{: #options-create-resource-record}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **--name**<br />Resource record name.
   * **--type**<br />Resource record type.
   * **--ipv4**<br />IPv4 address.
   * **--ipv6**<br />IPv6 address.
   * **--cname**<br />Canonical name.
   * **--ptrdname**<br />Hostname of the relevant A or AAAA record.
   * **--text**<br />Human readable text.
   * **--exchange**<br />Hostname of Exchange server.
   * **--preference**<br />Preference of the MX record
   * **--service**<br />The symbolic name of the desired service, beginning with an underscore `_`.
   * **--protocol**<br />The symbolic name of the desired protocol.
   * **--port**<br />Port number of the target server.
   * **--weight**<br />Weight of distributing queries among multiple target servers.
   * **--priority**<br />Priority of the SRV record.
   * **--target**<br />Hostname of the target server.
   * **--ttl**<br />Time to live, in seconds. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.
   * **-r, --record-content**<br /> The JSON file or JSON string used to describe a DNS Resource Record. See [Required fields for `-r --record-content`](#required-fields-r-record-content) for more detail.
   * **-i, --instance value**<br />Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
   * **--output value**<br />Specify output format. Currently, **json** is the only supported format.

#### Required fields for `-r --record-content`
{: #required-fields-r-record-content}

The required field in JSON data is **type**.

Resource record type. Valid values: "A", "AAAA", "CNAME", "PTR", "TXT", "MX", "SRV".
  * For type A, AAAA: Extra required fields are "name", "rdata".
    * "name": Resource record name.
    * "rdata": Content of the resource record.
      * "ip": IPv4/IPv6 address
  *  Extra optional fields are "ttl".
    * "ttl": Time to live in second. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

Sample JSON data:
```
        {
             "name": "testA",
             "type": "A",
             "rdata": {
                 "ip": "1.2.3.4"
                }
        }
```
{:codeblock}

```
        {
            "name": "testAAAA",
            "type": "AAAA",
            "rdata": {
                "ip": "2001:0db8:0012:0001:3c5e:7354:0000:5db1"
            }
        }
```
{:codeblock}

  * For type CNAME: Extra required fields are "name", "rdata".
    * "name": Resource record name.
    * "rdata": The content of type-CNAME resource record.
      * "cname": Canonical name.
  * Extra optional fields are "ttl".
    * "ttl": Time to live in second. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

Sample JSON data:

```
        {
            "name": "testCNAME",
            "type": "CNAME",
            "rdata": {
                "cname": "example.com"
            }
        }
```
{: codeblock}

  * For type PTR: Extra required fields are "name", "rdata".
    * "name": Resource record name.
    * "rdata": The content of type-PTR resource record.
      * "ptrdname": Hostname of the relevant A or AAAA record.
  * Extra option fields are "ttl".
    * "ttl": Time to live in second. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

Sample JSON data:

```
        {
            "name": "1.2.3.4",
            "type": "PTR",
            "rdata": {
                "ptrdname": "testA.example.com"
            }
        }
```
{: codeblock}

  * For type TXT: Extra required fields are "name", "rdata".
    * "name": Resource record name.
    * "rdata": The content of type-TXT resource record.
      * "text": Human readable text.
  * Extra optional fields are "ttl".
    * "ttl": Time to live in second. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

Sample JSON data:

```
        {
            "name": "testTXT",
            "type":"TXT",
            "rdata": {
                "text": "text information"
            }
        }
```
{:codeblock}


  * For type MX: Extra required fields are "name", "rdata".
    * "name": Resource record name.
    * "rdata": The content of type-MX resource record.
      * "exchange": Hostname of Exchange server.
      * "preference": Preference of the MX record
  * Extra optional fields are "ttl".
    * "ttl": Time to live in second. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

Sample JSON data:

```
        {
           "name": "testMX",
           "type": "MX",
           "rdata": {
                "preference": 10,
                "exchange": "mailserver.example.com"
            }
        }
```
{:codeblock}

  * For type SRV: Extra required fields are "name", "rdata", "service", "protocol".
    * "name": Resource record name.
    * "rdata": The content of type-SRV resource record.
      * "priority": Priority of the SRV record.
      * "weight": Weight of distributing queries among multiple target servers.
      * "port": Port number of the target server.
      * "target": Hostname of the target server.
    * "service": The symbolic name of the desired service, start with an underscore `_`.
    * "protocol": The symbolic name of the desired protocol.

  * Extra option fields are "ttl".
    * "ttl": Time to live in seconds. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

       Sample JSON data:

```
        {
            "type": "SRV",
            "name": "testSRV",
            "rdata": {
                "priority": 100,
                "weight": 100,
                "port": 8000,
                "target": "siphost.com"
            },
            "service": "_sip",
            "protocol": "udp"
        }
```
{:codeblock}



## ibmcloud dns resource-record-update
{: #update-resource-record}

Update a resource record for a given DNS zone.


```
   dns resource-record-update DNS_ZONE_ID RESOURCE_RECORD_ID (-r, --record-content @JSON_FILE | JSON_STRING) [-i, --instance INSTANCE_NAME | INSTANCE_ID] [--output FORMAT]
```

```sh
   ibmcloud dns resource-record-update DNS_ZONE_ID RESOURCE_RECORD_ID --name NAME --ipv4 IP_ADDRESS [--ttl TTL]
   ibmcloud dns resource-record-update DNS_ZONE_ID RESOURCE_RECORD_ID --name NAME --ipv6 IP_ADDRESS [--ttl TTL]
   ibmcloud dns resource-record-update DNS_ZONE_ID RESOURCE_RECORD_ID --name NAME --cname CNAME [--ttl TTL]
   ibmcloud dns resource-record-update DNS_ZONE_ID RESOURCE_RECORD_ID [--ttl TTL]
   ibmcloud dns resource-record-update DNS_ZONE_ID RESOURCE_RECORD_ID --name NAME --text TEXT [--ttl TTL]
   ibmcloud dns resource-record-update DNS_ZONE_ID RESOURCE_RECORD_ID --name NAME --exchange EXCHANGE --preference PREFERENCE [--ttl TTL]
   ibmcloud dns resource-record-update DNS_ZONE_ID RESOURCE_RECORD_ID --name NAME --priority PRIORITY --weight WEIGHT --port PORT --target TARGET  [--service SERVICE] [--protocol PROTOCOL] [--ttl TTL]
```
{:codeblock}

### Command options
{: #options-update-resource-record}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **RECORD_ID**<br />The ID of the record.
   * **--name**<br />Resource record name.
   * **--type**<br />Resource record type.
   * **--ipv4**<br />IPv4 address.
   * **--ipv6**<br />IPv6 address.
   * **--cname**<br />Canonical name.
   * **--ptrdname**<br />Hostname of the relevant A or AAAA record.
   * **--text**<br />Human readable text.
   * **--exchange**<br />Hostname of Exchange server.
   * **--preference**<br />Preference of the MX record
   * **--service**<br />The symbolic name of the desired service, start with an underscore `_`.
   * **--protocol**<br />The symbolic name of the desired protocol.
   * **--port**<br />Port number of the target server.
   * **--weight**<br />Weight of distributing queries among multiple target servers.
   * **--priority**<br />Priority of the SRV record.
   * **--target**<br />Hostname of the target server.
   * **--ttl**<br />Time to live, in seconds. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.
   * **-r, --record-content**<br />The JSON file or JSON string used to describe a DNS Resource Record. See [Required fields for -r, --record-content](#r-record-details) for more detail.
   * **-i, --instance INSTANCE_NAME**<br />Instance name. If the name is not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format, only JSON is supported.

#### Required fields for -r, --record-content
{:#r-record-details}

The required field in JSON data is **name**. Resource record name.

PTR records DO NOT need this field.
{:note}

  * For type A, AAAA: Extra required fields are "rdata".
    * "rdata": Content of the resource record.
      * "ip": IPv4/IPv6 address
  * Extra option fields are "ttl".
    * "ttl": Time to live, in seconds. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

       Sample JSON data:

```
        {
             "name": "testA",
             "rdata": {
                 "ip": "1.2.3.4"
            }
        }
```
{:codeblock}

```
        {
            "name": "testAAAA",
            "rdata": {
                "ip": "2001:0db8:0012:0001:3c5e:7354:0000:5db1"
            }
        }
```
{:codeblock}

  * For type CNAME: Extra required fields are "rdata".
      * "rdata": The content of type-PTR resource record.
      * "cname": Canonical name
  * Extra option fields are "ttl".
    * "ttl": Time to live, in seconds. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

        Sample JSON data:

```
        {
            "name": "testCNAME",
            "rdata": {
                "cname": "example.com"
            }
        }
```
{:codeblock}

  * For type PTR: Extra option fields are "ttl".
    * "ttl": Time to live, in seconds. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

        Sample JSON data:

```
        {
            "ttl": 360,
        }
```
{:codeblock}

  * For type TXT: Extra required fields are "rdata".
      * "rdata": The content of type-TXT resource record.
      * "text": Human readable text.
  * Extra optional fields are "ttl".
    * "ttl": Time to live, in seconds. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

        Sample JSON data:

```
        {
            "name": "testTXT",
            "rdata": {
                "text": "text information"
            }
        }
```
{:codeblock}

  * For type MX: Extra required fields are "rdata".
    * "rdata": The content of type-MX resource record.
      * "exchange": Hostname of Exchange server.
      * "preference": Preference of the MX record
  * Extra optional fields are "ttl".
    * "ttl": Time to live, in seconds. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

        Sample JSON data:

```
        {
            "name": "testMX",
            "content": "smtp.example.com",
            "priority": 10
        }
```
{:codeblock}

  * For type SRV: Extra required fields are "rdata", "service", "protocol".
    * "rdata": The content of type-SRV resource record.
      * "priority": Priority of the SRV record
      * "weight": Weight of distributing queries among multiple target servers.
      * "port": Port number of the target server.
      * "target": Hostname of the target server.
    * "service": The symbolic name of the desired service, start with an underscore `_`.
    * "protocol": The symbolic name of the desired protocol.
  * Extra option fields are "ttl".
    * "ttl": Time to live, in seconds. Default value is 900.  Valid values: 60, 120, 300, 600, 900, 1800, 3600, 7200, 18000, 43200.

        Sample JSON data:

```
        {
            "name": "testSRV"
            "rdata": {
                "priority": 100,
                "weight": 100,
                "port": 8000,
                "target": "siphost.com"
            },
            "service": "_sip",
            "protocol": "udp"
        }
```
{:codeblock}


## ibmcloud dns resource-record
{: #get-resource-record}

Get a resource record details for a given DNS zone.

```
   ibmcloud dns resource-record ZONE_ID RECORD_ID [-i, --instance INSTANCE_NAME] [--output FORMAT]
```

### Command options
{:options-get-resource-records}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **RECORD_ID**<br />The ID of resource record.
   * **-i, --instance INSTANCE_NAME**<br />Instance name. If the name is not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.


## ibmcloud dns resource-record-delete
{: #delete-resource-record}

Delete a resource record for a given DNS zone.

```
   ibmcloud dns resource-record-delete ZONE_ID RECORD_ID [--force] [-i, --instance INSTANCE_NAME]
```

### Command options
{: #options-delete-resource-records}
  
   * **ZONE_ID**<br />The ID of the DNS zone.
   * **RECORD_ID**<br />The ID of resource record.
   * **--force**<br />Delete resource record without prompting for confirmation.
   * **-i, --instance INSTANCE_NAME**<br />Instance name. If the name is not set, the context instance specified by `ibmcloud dns instance-target` is used.
     

## ibmcloud dns resource-records
{: #list-resource-record}

List all resource records for a given DNS zone.

```
   ibmcloud dns resource-records ZONE_ID [-i, --instance INSTANCE_NAME] [--output FORMAT]
```

### Command options
{: #options-list-resource-records}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **--page**<br />Page number of paginated results. (default 1)
   * **--per-page**<br />Number of resource records per page. Min: 50. Max: 1000. (default 200)
   * **-i, --instance**<br />Instance name or ID. If not set, the context instance specified by `ibmcloud instance-target INSTANCE` is used.
   * **--output**<br />Specify output format. Currently, **json** is the only supported format.
  
### Command example  
{: #list-resource-record-pagination}

List resource records with pagination:

  ```
  ibmcloud dns resource-records ZONE_ID --per-page 1000 --page 1
  ```
  {: pre}

### Command output
{: #output-list-resource-records}

Table columns:

   * ID
   * Name
   * Type
   * Rdata
   * TTL

### Example command to list resource records with pagination
{: #list-resource-rec-pagination-example}

  ```
  ibmcloud dns resource-records ZONE_ID --per-page 1000 --page 1
  ```
  {: pre}
