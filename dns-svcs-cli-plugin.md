---

copyright:
  years: 2019, 2021
lastupdated: "2021-04-21"

keywords:

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


# {{site.data.keyword.dns_short}} CLI reference
{: #dns-services-cli-commands}

Follow these instructions to use the {{site.data.keyword.dns_full}} command-line interface (CLI).
{: shortdesc}

## Before you begin
{: #cli-ref-prereqs}

Complete these steps to use the {{site.data.keyword.dns_short}} CLI, which is implemented as an {{site.data.keyword.cloud_notm}} CLI plug-in. This plug-in provides you with the means to manage your service instance and its associated resources through a command-line user interface.

1. Install the [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-install-ibmcloud-cli#install-ibmcloud-cli){: external}.
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



## Instances
{: #resource-instance}

Manage DNS Services instances by using the following **instance** commands.

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
   ibmcloud dns instance-create INSTANCE_NAME PLAN [-g, --resource-group RESOURCE_GROUP] [--output FORMAT]
```

### Command options
{: #command-options-create-dns-svcs-instance}

   * **INSTANCE_NAME**<br />The name of the DNS Services instance.
   * **PLAN**<br />The name or ID of a service plan.
   * **-g, --resource-group**<br />The name or ID of a resource group.
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

Manage DNS zones by using the following **zone** commands.

## ibmcloud dns zone-create
{: #create-zone}

Create a DNS zone.

```
   ibmcloud dns zone-create ZONE_NAME [-d, --description DESC] [-l, --label LABEL] [-i, --instance INSTANCE] [--output FORMAT]
```

### Command options
{: #options-create-dns-svcs-zone}

   * **ZONE_NAME**<br />The name of the DNS zone.
   * **-d, --description**<br />The text describing the purpose of a DNS zone.
   * **-l, --label**<br />The label of a DNS zone.
   * **-i, --instance INSTANCE**<br />Instance name or ID. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
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

Get the DNS zone details.

```
   ibmcloud dns zone ZONE_ID [-i, --instance INSTANCE] [--output FORMAT]
```

### Command options
{: #options-get-zone}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **-i, --instance INSTANCE**<br />Instance name or ID. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
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
   ibmcloud dns zone-update ZONE_ID [-d, --description DESC] [-l, --label LABEL] [--instance INSTANCE] [--output FORMAT]
```

### Command options
{: #options-update-zone}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **-d, --description**<br />The text describing the purpose of a DNS zone.
   * **-l, --label**<br />The label of a DNS zone.
   * **-i, --instance INSTANCE**<br />Instance name or ID. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
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
   ibmcloud dns zone-delete ZONE_ID [-i, --instance INSTANCE] [-f,--force]
```

### Command options
{: #options-delete-zone}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **-i, --instance INSTANCE**<br />Instance name or ID. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **-f, --force**<br />Delete a zone without prompting for confirmation.

## ibmcloud dns zones
{: #list-zones}

List all DNS zones for a service instance.

```
   ibmcloud dns zones [-i, --instance INSTANCE] [--output FORMAT]
```

### Command options
{: #options-list-zones}

   * **-i, --instance INSTANCE**<br />Instance name or ID. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.

## Permitted networks
{: #permitted-network}

Manage permitted networks by using the following **permitted-network** commands.

## ibmcloud dns permitted-network-add
{: #add-permitted-network}

Add a permitted network for a DNS zone.

```
   ibmcloud dns permitted-network-add ZONE_ID --vpc-crn VPC_CRN [--type TYPE] [-i, --instance INSTANCE] [--output FORMAT]
```

### Command options
{: #options-add-permitted-network}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **--type**<br />The permitted network type. Valid values: `vpc`.
   * **--vpc-crn**<br />The CRN of VPC instance 
   * **-i, --instance INSTANCE**<br />Instance name or ID. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
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

Get the permitted network details.

```
   ibmcloud dns permitted-network ZONE_ID PERMITTED_NETWORK_ID [-i, --instance INSTANCE] [--output FORMAT]
```

### Command options
{: #options-get-permitted-network}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **PERMITTED_NETWORK_ID**<br />The ID of the permitted network.
   * **-i, --instance INSTANCE**<br />Instance name or ID. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
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
   ibmcloud dns permitted-network-remove ZONE_ID PERMITTED_NETWORK_ID [-i, --instance INSTANCE] [-f,--force]
```

### Command options
{: #options-remove-permitted-network}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **PERMITTED_NETWORK_ID**<br />The ID of the permitted network.
   * **--instance INSTANCE**<br />Instance name or ID. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **-f, --force**<br />Remove a permitted network without prompting for confirmation.


## ibmcloud dns permitted-networks
{: #list-permitted-networks}

List permitted networks for a zone.

```
   ibmcloud dns permitted-networks ZONE_ID [-i, --instance INSTANCE] [--output FORMAT]
```

### Command options
{: #options-list-permitted-networks}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **-i, --instance INSTANCE**<br />Instance name or ID. If not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.

## Resource records
{: #resource-record}

Manage how the resource record performs using the following **resource-record** commands.

## ibmcloud dns resource-record-create
{: #create-resource-record}

Create a resource record for a DNS zone.

```
   ibmcloud dns resource-record-create DNS_ZONE_ID (-r, --record-content @JSON_FILE | JSON_STRING) [-i, --instance INSTANCE] [--output FORMAT]
```
{:pre}

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

Resource record type. Valid values: `A`, `AAAA`, `CNAME`, `PTR`, `TXT`, `MX`, `SRV`.
  * For type A, AAAA: Extra required fields are `name`, `rdata`.
    * `name`: Resource record name.
    * `rdata`: Content of the resource record.
      * `ip`: IPv4/IPv6 address
  *  Extra optional fields are `ttl`.
    * `ttl`: Time to live in second. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

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

  * For type CNAME: Extra required fields are `name`, `rdata`.
    * `name`: Resource record name.
    * `rdata`: The content of type-CNAME resource record.
      * `cname`: Canonical name.
  * Extra optional fields are `ttl`.
    * `ttl`: Time to live in second. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

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

  * For type PTR: Extra required fields are `name`, `rdata`.
    * `name`: Resource record name.
    * `rdata`: The content of type-PTR resource record.
      * `ptrdname`: Hostname of the relevant A or AAAA record.
  * Extra option fields are `ttl`.
    * `ttl`: Time to live in second. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

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

  * For type TXT: Extra required fields are `name`, `rdata`.
    * `name`: Resource record name.
    * `rdata`: The content of type-TXT resource record.
      * `text`: Human readable text.
  * Extra optional fields are `ttl`.
    * `ttl`: Time to live in seconds. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

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


  * For type MX: Extra required fields are `name`, `rdata`.
    * `name`: Resource record name.
    * `rdata`: The content of type-MX resource record.
      * `exchange`: Hostname of Exchange server.
      * `preference`: Preference of the MX record
  * Extra optional fields are `ttl`.
    * `ttl`: Time to live in seconds. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

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

  * For type SRV: Extra required fields are `name`, `rdata`, `service`, `protocol`.
    * `name`: Resource record name.
    * `rdata`: The content of type-SRV resource record.
      * `priority`: Priority of the SRV record.
      * `weight`: Weight of distributing queries among multiple target servers.
      * `port`: Port number of the target server.
      * `target`: Hostname of the target server.
    * `service`: The symbolic name of the desired service, start with an underscore `_`.
    * `protocol`: The symbolic name of the desired protocol.

  * Extra option fields are `ttl`.
    * `ttl`: Time to live in seconds. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

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

Update a resource record for a DNS zone.


```
   dns resource-record-update DNS_ZONE_ID RESOURCE_RECORD_ID (-r, --record-content @JSON_FILE | JSON_STRING) [-i, --instance INSTANCE] [--output FORMAT]
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
   * **--ttl**<br />Time to live, in seconds. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.
   * **-r, --record-content**<br />The JSON file or JSON string used to describe a DNS Resource Record. See [Required fields for -r, --record-content](#r-record-details) for more detail.
   * **-i, --instance INSTANCE**<br />Instance name or ID. If the name is not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format, only JSON is supported.

#### Required fields for -r, --record-content
{:#r-record-details}

The required field in JSON data is **name**. Resource record name.

PTR records _do not_ need this field.
{:note}

  * For type A, AAAA: Extra required fields are `rdata`.
    * `rdata`: Content of the resource record.
      * `ip`: IPv4/IPv6 address
  * Extra option fields are `ttl`.
    * `ttl`: Time to live, in seconds. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

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

  * For type CNAME: Extra required fields are `rdata`.
      * `rdata`: The content of type-PTR resource record.
      * `cname`: Canonical name
  * Extra option fields are `ttl`.
    * `ttl`: Time to live, in seconds. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

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

  * For type PTR: Extra option fields are `ttl`.
    * `ttl`: Time to live, in seconds. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

Sample JSON data:

```
        {
            "ttl": 360,
        }
```
{:codeblock}

  * For type TXT: Extra required fields are `rdata`.
      * `rdata`: The content of type-TXT resource record.
      * `text`: Human readable text.
  * Extra optional fields are `ttl`.
    * `ttl`: Time to live, in seconds. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

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

  * For type MX: Extra required fields are `rdata`.
    * `rdata`: The content of type-MX resource record.
      * `exchange`: Hostname of Exchange server.
      * `preference`: Preference of the MX record
  * Extra optional fields are `ttl`.
    * `ttl`: Time to live, in seconds. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

Sample JSON data:

```
        {
            "name": "testMX",
            "content": "smtp.example.com",
            "priority": 10
        }
```
{:codeblock}

  * For type SRV: Extra required fields are `rdata`, `service`, `protocol`.
    * `rdata`: The content of type-SRV resource record.
      * `priority`: Priority of the SRV record
      * `weight`: Weight of distributing queries among multiple target servers.
      * `port`: Port number of the target server.
      * `target`: Hostname of the target server.
    * `service`: The symbolic name of the desired service, start with an underscore `_`.
    * `protocol`: The symbolic name of the desired protocol.
  * Extra option fields are `ttl`.
    * `ttl`: Time to live, in seconds. Default value is `900`.  Valid values: `60`, `120`, `300`, `600`, `900`, `1800`, `3600`, `7200`, `18000`, `43200`.

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

Get a resource record details for a DNS zone.

```
   ibmcloud dns resource-record ZONE_ID RECORD_ID [-i, --instance INSTANCE] [--output FORMAT]
```

### Command options
{:options-get-resource-records}

   * **ZONE_ID**<br />The ID of the DNS zone.
   * **RECORD_ID**<br />The ID of resource record.
   * **-i, --instance INSTANCE**<br />Instance name or ID. If the name is not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **--output FORMAT**<br />Specify output format. Currently, **json** is the only supported format.


## ibmcloud dns resource-record-delete
{: #delete-resource-record}

Delete a resource record for a DNS zone.

```
   ibmcloud dns resource-record-delete ZONE_ID RECORD_ID [-i, --instance INSTANCE] [-f,--force]
```

### Command options
{: #options-delete-resource-records}
  
   * **ZONE_ID**<br />The ID of the DNS zone.
   * **RECORD_ID**<br />The ID of resource record.
   * **-i, --instance INSTANCE**<br />Instance name or ID. If the name is not set, the context instance specified by `ibmcloud dns instance-target` is used.
   * **-f, --force**<br />Delete resource record without prompting for confirmation.
     

## ibmcloud dns resource-records
{: #list-resource-record}

List all resource records for a DNS zone.

```
   ibmcloud dns resource-records ZONE_ID [-i, --instance INSTANCE] [--output FORMAT]
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

## Global load balancer
{: #glb}

Manage global load balancers by using the following **glb** commands.

## ibmcloud dns glb-create
{: #create-glb}

Create a global load balancer in a zone.

```
ibmcloud dns glb-create DNS_ZONE_ID --name NAME --default-pools POOL_LIST --fallback-pool POOL_ID [--description DESCRIPTION] [--enabled true|false] [--ttl TTL] [--az-pools AZPOOLS1 --az-pools AZPOOLS2] [-i, --instance INSTANCE] [--output FORMAT]

ibmcloud dns glb-create DNS_ZONE_ID (-j, --json @JSON_FILE | JSON_STRING) [-i, --instance INSTANCE] [--output FORMAT]
```
{: pre}

### Command options
{: #create-glb-options}

- **DNS_DOMAIN_ID**<br />The ID of DNS zone. Required.
- **--json**<br />The JSON file or JSON string used to describe a global load balancer. Required.
  - The required fields in JSON data are `name`, `fallback_pool`, `default_pools`:
    - `name`: The DNS hostname to associate with your load balancer.
    - `fallback_pool`: The pool ID to use when all other pools are detected as unhealthy.
    - `default_pools`: A list of pool IDs ordered by their failover priority.
  - The optional fields are `description`, `ttl`, `az_pools`, `enabled`:
    - `description`: The descriptive text of the load balancer.
    - `ttl`: Time to live (TTL) of the DNS entry for the IP address returned by this load balancer.
    - `az_pools`: A mapping of region and country codes to a list of pool IDs (ordered by their failover priority) for the region.
    - `enabled`: Whether the load balancer pool is enabled. Valid values: `true`, `false`. The values `on`, `off` will be deprecated.

Sample JSON data:

```
{
  "name": "glb01",
  "description": "Global load balancer 01",
  "enabled": false,
  "ttl": 300,
  "default_pools": ["cc1deb57-0eb4-45cb-94ce-a3c71c189d12"],
  "fallback_pool": "cc1deb57-0eb4-45cb-94ce-a3c71c189d12",
  "az_pools": [
    {
      "availability_zone": "us-south-1",
      "pools": [
        "0fc0bb7c-2fab-476e-8b9b-40fa14bf8e3d"
      ]
    },
    {
      "availability_zone": "us-south-2",
      "pools": [
        "f46eba57-f08e-4e38-a76c-f3370d457bd2"
      ]
    }
  ]
}
```
{:codeblock}

- **--name** The DNS hostname to associate with your load balancer.
- **--fallback-pool** The pool ID to use when all other pools are detected as unhealthy.
- **--default-pools** A list of pool IDs ordered by their failover priority.
- **--description** The descriptive text of the load balancer.
- **--ttl** Time to live (TTL) of the DNS entry for the IP address returned by this load balancer.
- **--az-pools** A mapping of region and country codes to a list of pool IDs (ordered by their failover priority) for the region.
- **--enabled** Whether the load balancer pool is enabled. Valid values: `true`, `false`.
- **-i, --instance**: Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**: Specify output format. Currently, **json** is the only supported format.

### Examples
{: #create-glb-examples}

Create a global load balancer in zone `demo.com:31984fea73a15b45779fa0df4ef62f9b`.

```
ibmcloud dns glb-create demo.com:31984fea73a15b45779fa0df4ef62f9b --json @glb.json -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-update
{: #update-glb}

Update a global load balancer in a zone.

```
ibmcloud dns glb-update DNS_ZONE_ID GLB_ID (-j, --json @JSON_FILE | JSON_STRING) [-i, --instance INSTANCE] [--output FORMAT]

ibmcloud dns glb-update DNS_ZONE_ID GLB_ID [--name NAME] [--default-pools POOL_LIST] [--fallback-pool POOL_ID] [--description DESCRIPTION] [--enabled true|false] [--ttl TTL] [--az-pools AZPOOLS1 --az-pools AZPOOLS2] [-i, --instance INSTANCE] [--output FORMAT]
```
{: pre}

### Command options
{: #update-glb-options}

- **DNS_DOMAIN_ID**<br />The ID of DNS zone. Required.
- **GLB_ID**<br />The ID of global load balancer. Required.
- **--json**<br />The JSON file or JSON string used to describe a global load balancer. Required.
  - The optional fields are `name`, `fallback_pool`, `default_pools`, `description`, `ttl`, `az_pools`, `enabled`:
    - `name`: The DNS hostname to associate with your load balancer.
    - `fallback_pool`: The pool ID to use when all other pools are detected as unhealthy.
    - `default_pools`: A list of pool IDs ordered by their failover priority.
    - `description`: The descriptive text of the load balancer.
    - `ttl`: Time to live (TTL) of the DNS entry for the IP address returned by this load balancer.
    - `az_pools`: A mapping of region and country codes to a list of pool IDs (ordered by their failover priority) for the region.
    - `enabled`: Whether the load balancer pool is enabled. Valid values: `true`, `false`. The values `on`, `off` will be deprecated.

Sample JSON data:

```
{
  "name": "glb01",
  "description": "Global load balancer 01",
  "enabled": false,
  "ttl": 300,
  "default_pools": ["cc1deb57-0eb4-45cb-94ce-a3c71c189d12"],
  "fallback_pool": "cc1deb57-0eb4-45cb-94ce-a3c71c189d12",
  "az_pools": [
    {
      "availability_zone": "us-south-1",
      "pools": [
        "0fc0bb7c-2fab-476e-8b9b-40fa14bf8e3d"
      ]
    },
    {
      "availability_zone": "us-south-2",
      "pools": [
        "f46eba57-f08e-4e38-a76c-f3370d457bd2"
      ]
    }
  ]
}
```
{:codeblock}

- **--name** The DNS hostname to associate with your load balancer.
- **--fallback-pool** The pool ID to use when all other pools are detected as unhealthy.
- **--default-pools** A list of pool IDs ordered by their failover priority.
- **--description** The descriptive text of the load balancer.
- **--ttl** Time to live (TTL) of the DNS entry for the IP address returned by this load balancer.
- **--az-pools** A mapping of region and country codes to a list of pool IDs (ordered by their failover priority) for the region.
- **--enabled** Whether the load balancer pool is enabled. Valid values: `true`, `false`.
- **-i, --instance**: Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**: Specify output format. Currently, **json** is the only supported format.

### Examples
{: #update-glb-examples}

Update global load balancer `699d98642c564d2e855e9661899b7252` in zone `demo.com:31984fea73a15b45779fa0df4ef62f9b`.

```
ibmcloud dns glb-update demo.com:31984fea73a15b45779fa0df4ef62f9b 699d98642c564d2e855e9661899b7252 --json @glb.json -i "dns-demo"
```
{: pre}

## ibmcloud dns glb
{: #show-glb}

Show a global load balancer in a zone.

```
ibmcloud dns glb DNS_DOMAIN_ID GLB_ID [-i, --instance INSTANCE] [--output FORMAT]
```
{: pre}

### Command options
{: #show-glb-options}

- **DNS_DOMAIN_ID**<br />The ID of DNS zone. Required.
- **GLB_ID**<br />The ID of global load balancer. Required.
- **-i, --instance**<br />Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**<br />Specify output format. Currently, **json** is the only supported format.

### Examples
{: #show-glb-examples}

Show global load balancer `699d98642c564d2e855e9661899b7252` in zone `demo.com:31984fea73a15b45779fa0df4ef62f9b`.

```
ibmcloud dns glb demo.com:31984fea73a15b45779fa0df4ef62f9b 699d98642c564d2e855e9661899b7252 -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-delete
{: #delete-glb}

Delete a global load balancer in a DNS domain.

```
ibmcloud dns glb-delete DNS_DOMAIN_ID GLB_ID [-i, --instance INSTANCE] [-f,--force]
```
{: pre}

### Command options
{: #delete-glb-options}

- **DNS_DOMAIN_ID**<br />The ID of DNS zone. Required.
- **GLB_ID**<br />The ID of global load balancer. Required.
- **-i, --instance**<br />Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **-f, --force**<br />Delete load balancer without prompting for confirmation.

### Examples
{: #delete-glb-examples}

Delete global load balancer `699d98642c564d2e855e9661899b7252` in zone `demo.com:31984fea73a15b45779fa0df4ef62f9b`.

```
ibmcloud dns glb-delete demo.com:31984fea73a15b45779fa0df4ef62f9b 699d98642c564d2e855e9661899b7252 -f -i "dns-demo"
```
{: pre}

## ibmcloud dns glbs
{: #list-glb}

List all load balancers for the zone.

```
ibmcloud dns glbs DNS_ZONE_ID [-i, --instance INSTANCE] [--output FORMAT]
```
{: pre}

### Command options
{: #list-glb-options}

- **DNS_DOMAIN_ID**<br />The ID of DNS zone. Required.
- **-i, --instance**<br />Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**<br />Specify output format. Currently, **json** is the only supported format.

### Examples
{: #list-glb-examples}

List load balancers for zone `demo.com:31984fea73a15b45779fa0df4ef62f9b`.

```
ibmcloud dns glbs demo.com:31984fea73a15b45779fa0df4ef62f9b -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-pool-create
{: #create-glb-pool}

Create a GLB pool for a service instance.

```
ibmcloud dns glb-pool-create (-j, --json @JSON_FILE | JSON_STRING) [-i, --instance INSTANCE] [--output FORMAT]

ibmcloud dns glb-pool-create --name NAME --origins ORIGIN1 --origins ORIGIN2 [--description DESCRIPTION] [--enabled true|false] [--healthy-origins-threshold THRESHOLD] [--monitor MONITOR_ID] [--notification-channel CHANNEL] [--healthcheck-region REGION] [--healthcheck-subnets SUBNETS] [-i, --instance INSTANCE] [--output FORMAT]

```
{: pre}

### Command options
{: #create-glb-pool-options}

- **--json**<br />The JSON file or JSON string used to describe a global load balancer pool. Required.
  - The required fields in JSON data are `name`, `origins`:
    - `name`: The name of the load balancer pool.
    - `origins`: The list of origins within this pool.
  - The optional fields are `description`, `healthy_origins_threshold`, `enabled`, `monitor`, `notification_channel`, `healthcheck_region`, `healthcheck_subnets`:
    - `description`: The descriptive text of the load balancer pool.
    - `healthy_origins_threshold`: The minimum number of origins that must be healthy for this pool to serve traffic.
    - `enabled`: Whether the load balancer pool is enabled. Valid values: `true`, `false`.
    - `monitor`: The ID of the load balancer monitor to be associated to this pool.
    - `notification_channel`: The notification channel.
    - `healthcheck_region`: Health check region of VSIs. Valid values: `us-south`, `us-east`, `eu-gb`, `eu-du`, `au-syd`, `jp-tok`.
    - `healthcheck_subnets`: A list of health check subnet IDs of VSIs.

      When you create a pool by attaching a monitor, DNS Services takes one address from the health check subnet. Ensure this health check subnet has sufficient IP addresses available.
      {:note}

Sample JSON data:

```
{
  "name": "us-pool",
  "description": "application server pool in US",
  "origins": [
    {
      "name": "us-app-dal01",
      "description": "dallas origin 01",
      "address": "1.1.1.1",
      "enabled": true
    },
    {
      "name": "us-app-dal02",
      "description": "dallas origin 02",
      "address": "2.2.2.2",
      "enabled": true
    }
  ],
  "healthy_origins_threshold": 1,
  "monitor": "f1aba936b94213e5b8dca0c0dbf1f9cc",
  "enabled": true,
  "notification_channel": "https://mywebsite.com/dns/webhook",
  "healthcheck_region": "us-south",
  "healthcheck_subnets": ["0716-a4c0c123-594c-4ef4-ace3-a08858540b5e"]
}
```
{:codeblock}

- **--name** The name of the load balancer pool.
- **--description** The descriptive text of the load balancer pool.
- **--healthy-origins-threshold** The minimum number of origins that must be healthy for this pool to serve traffic.
- **--enabled** Whether the load balancer pool is enabled. Valid values: `true`, `false`.
- **--monitor** The ID of the load balancer monitor to be associated to this pool.
- **--notification-channel** The notification channel.
- **healthcheck-region** Health check region of VSIs. Valid values: `us-south`, `us-east`, `eu-gb`, `eu-du`, `au-syd`, `jp-tok`.
- **healthcheck-subnets** A list of health check subnet IDs of VSIs.

- **-i, --instance**: Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**: Specify output format. Currently, **json** is the only supported format.

### Examples
{: #create-glb-pool-examples}

Create a GLB pool for instance `dns-demo`.

```
ibmcloud dns glb-pool-create --json @glb-pool.json -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-pool-update
{: #update-glb-pool}

Update the details of a GLB pool.

```

 ibmcloud dns glb-pool-update GLB_POOL_ID [--name NAME] [--enable-origin ORIGIN_NAME --enable-origin ORIGIN_NAME ...] [--disable-origin ORIGIN_NAME --disable-origin ORIGIN_NAME ...] [--add-origin ORIGIN_PARAMETER --add-origin ORIGIN_PARAMETER ...] [--remove-origin ORIGIN_NAME --remove-origin ORIGIN_NAME ...]  [--description DESCRIPTION] [--enabled true|false] [--healthy-origins-threshold THRESHOLD] [-detach-monitor] [--attach-monitor MONITOR_ID] [--healthcheck-region REGION] [--healthcheck-subnets SUBNETS] [-i, --instance INSTANCE] [--output FORMAT]

ibmcloud dns glb-pool-update GLB_POOL_ID (-j, --json @JSON_FILE | JSON_STRING) [-i, --instance INSTANCE] [--output FORMAT]

```
{: pre}

### Command options
{: #update-glb-pool-options}

- **GLB_POOL_ID**<br />The ID of global load balancer pool. Required.
- **--json**<br />The JSON file or JSON string used to describe a GLB pool. Required.
  - The optional fields are `name`, `origins`, `description`, `healthy_origins_threshold`, `enabled`, `monitor`, `notification_channel`, `healthcheck_region`, `healthcheck_subnets`:
    - `name`: The name of the load balancer pool.
    - `origins`: The list of origins within this pool.
    - `description`: The descriptive text of the load balancer pool.
    - `healthy_origins_threshold`: The minimum number of origins that must be healthy for this pool to serve traffic.
    - `enabled`: Whether the load balancer pool is enabled. Valid values: `true`, `false`.
    - `monitor`: The ID of the load balancer monitor to be associated to this pool.
    - `notification_channel`: The notification channel.
    - `healthcheck_region`: Health check region of VSIs. Valid values: `us-south`, `us-east`, `eu-gb`, `eu-du`, `au-syd`, `jp-tok`.
    - `healthcheck_subnets`: A list of health check subnet IDs of VSIs.

Sample JSON data:

```
{
  "name": "us-pool",
  "description": "application server pool in US",
  "origins": [
    {
      "name": "us-app-dal01",
      "description": "dallas origin 01",
      "address": "1.1.1.1",
      "enabled": true
    },
    {
      "name": "us-app-dal02",
      "description": "dallas origin 02",
      "address": "2.2.2.2",
      "enabled": true
    }
  ],
  "healthy_origins_threshold": 1,
  "monitor": "f1aba936b94213e5b8dca0c0dbf1f9cc",
  "enabled": true,
  "notification_channel": "https://mywebsite.com/dns/webhook",
  "healthcheck_region": "us-south",
  "healthcheck_subnets": ["0716-a4c0c123-594c-4ef4-ace3-a08858540b5e"]
}
```
{:codeblock}

- **--name** The name of the load balancer pool.
- **--description** The descriptive text of the load balancer pool.
- **--enable-origin** Enable the origin within the pool. The value can be ORIGIN_NAME or ORIGIN_ADDRESS.
- **--disable-origin** Disable the origin within the pool. The value can be ORIGIN_NAME or ORIGIN_ADDRESS.
- **--add-origin** Add an origin into the pool. ORIGIN_NAME and ORIGIN_ADDRESS are required.
                   For example: `--add-origin name=example,address=1.2.3.4,enabled=true,description=origin_description`
- **--remove-origin** Remove an origin from the Pool. The value can be ORIGIN_NAME or ORIGIN_ADDRESS.
- **--detach-monitor** Detach monitor from origin pool.
- **--attach-monitor** Attach monitor to origin pool.
- **--healthy-origins-threshold** The minimum number of origins that must be healthy for this pool to serve traffic.
- **--enabled** Whether the load balancer pool is enabled. Valid values: `true`, `false`.
- **healthcheck-region** Health check region of VSIs. Valid values: `us-south`, `us-east`, `eu-gb`, `eu-du`, `au-syd`, `jp-tok`.
- **healthcheck-subnets** A list of health check subnet IDs of VSIs.
- **-i, --instance**: Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**: Specify output format. Currently, **json** is the only supported format.

### Examples
{: #update-glb-pool-examples}

Update a GLB pool `17b5962d775c646f3f9725cbc7a53df4` for instance `dns-demo`.

```
ibmcloud dns glb-pool-update 17b5962d775c646f3f9725cbc7a53df4 --json @glb-pool.json -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-pool
{: #show-glb-pool}

Show the details of a GLB pool.

```
ibmcloud dns glb-pool GLB_POOL_ID [-i, --instance INSTANCE] [--output FORMAT]
```
{: pre}

### Command options
{: #show-glb-pool-options}

- **GLB_POOL_ID**<br />The ID of global load balancer pool. Required.
- **-i, --instance**<br />Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**<br />Specify output format. Currently, **json** is the only supported format.

### Examples
{: #show-glb-pool-examples}

Show the details of GLB pool `17b5962d775c646f3f9725cbc7a53df4`.

```
ibmcloud dns glb-pool 17b5962d775c646f3f9725cbc7a53df4 -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-pool-delete
{: #delete-glb-pool}

Delete a GLB pool.

```
ibmcloud dns glb-pool-delete GLB_POOL_ID [-i, --instance INSTANCE] [-f,--force]
```
{: pre}

### Command options
{: #delete-glb-pool-options}

- **GLB_POOL_ID**<br />The ID of global load balancer pool. Required.
- **-i, --instance**<br />Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **-f, --force**<br />Delete load balancer pool without prompting for confirmation.

### Examples
{: #delete-glb-pool-examples}

Delete GLB pool `17b5962d775c646f3f9725cbc7a53df4`.

```
ibmcloud dns glb-pool-delete 17b5962d775c646f3f9725cbc7a53df4 -f -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-pools
{: #list-glb-pools}

List all GLB pools for a service instance.

```
ibmcloud dns glb-pools [-i, --instance INSTANCE] [--output FORMAT]
```
{: pre}

### Command options
{: #list-glb-pools-options}

- **-i, --instance**<br />Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**<br />Specify output format. Currently, **json** is the only supported format.

### Examples
{: #list-glb-pools-examples}

List all GLB pools for instance `dns-demo`.

```
ibmcloud dns glb-pools -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-monitor-create
{: #create-glb-monitor}

Create a GLB monitor for a service instance.

```
ibmcloud dns glb-monitor-create (-j, --json @JSON_FILE | JSON_STRING) [-i, --instance INSTANCE] [--output FORMAT]

ibmcloud dns glb-monitor-create --name NAME --type TCP [--port PORT] [--description DESCRIPTION] [--interval INTERVAL] [--retries RETRY] [--timeout TIMEOUT] [-i, --instance INSTANCE] [--output FORMAT]

ibmcloud dns glb-monitor-create --name NAME --type (HTTP|HTTPS) --path PATH [--port PORT] [--description DESCRIPTION] [--method GET|HEAD] [--headers HEADER1 --headers HEADER2...] [--interval INTERVAL] [--retries RETRY] [--timeout TIMEOUT] [--allow-insecure true|false] [--expected-body BODY] [--expected-codes CODE] [-i, --instance INSTANCE] [--output FORMAT]

```
{: pre}

### Command options
{: #create-glb-monitor-options}

- **--json**<br />The JSON file or JSON string used to describe a GLB monitor. Required.
   - The required fields in JSON data are `name`, `type`.
     - `name`: The name of the load balancer monitor.
     - `type`: The protocol to use for the health check. Valid values: `HTTP`, `HTTPS`, `TCP`.
   - The optional fields are `description`, `timeout`, `retries`, `interval`.
     - `description`: The descriptive text of the load balancer monitor.
     - `timeout`: The timeout (in seconds) before marking the health check as failed. Valid values: `1-10`.
     - `retries`: The number of retries to attempt in case of a timeout before marking the origin as unhealthy. Valid values: `0-3`.
     - `interval`: The interval between each health check. Valid values: `5-3600`.
   - For `TCP` type health check. Extra required fields are `port`.
     - `port`: The TCP port to use for the health check.
   - For `HTTP/HTTPS` type health check. Extra required fields are `expected_codes`.
     - `expected_codes`: The expected HTTP response code or code range of the health check. Valid values: `200`, `201`, `202`, `203`, `204`, `205`, `206`, `207`, `208`, `226`, `2xx`.
   - Extra option fields are `port`, `expected_body`, `method`, `path`, `header`, `allow_insecure`.
     - `port`: The port number the health check connects to.
     - `expected_body`: A case-insensitive sub-string to look for in the response body.
     - `method`: The method to use for the health check applicable to HTTP/HTTPS based checks. Valid values: `GET`, `HEAD`.
     - `path`: The endpoint path to health check against.
     - `header`: The HTTP request headers to send in the health check.
     - `allow_insecure`: Do not validate the certificate when monitor use HTTPS. Valid values: `true`, `false`.

Sample JSON data:

For HTTP/HTTPS:

```
{
  "name": "glbmonitor",
  "description": "Health monitor of web service",
  "type": "HTTPS",
  "method": "GET",
  "path": "/health",
  "headers": [
    {
      "name": "Host",
      "value": ["glb.example.com"]
    },
    {
      "name": "X-App-ID",
      "value":["abc123"]
    }
  ],
  "port": 443,
  "timeout": 5,
  "retries": 2,
  "interval": 90,
  "allow_insecure": false,
  "expected_codes": "2xx",
  "expected_body": "alive"
}
```
{:codeblock}

For TCP:

```
{
  "name": "glbmonitor",
  "description": "Health monitor of TCP",
  "type": "TCP",
  "port": 80,
  "timeout": 5,
  "retries": 2,
  "interval": 90
}
```
{:codeblock}
- **--name** The name of the load balancer monitor.
- **--type** The protocol to use for the health check. Valid values: `HTTP`, `HTTPS`, `TCP`.
- **--description** The descriptive text of the load balancer monitor.
- **--timeout** The timeout (in seconds) before marking the health check as failed. Valid values: `1-10`.
- **--retries** The number of retries to attempt in case of a timeout before marking the origin as unhealthy. Valid values: `0-3`.
- **--interval** The interval between each health check. Valid values: `5-3600`.
- **--port** The port number the health check connects to.
- **--expected-codes** The expected HTTP response code or code range of the health check. Valid values: `200`, `201`, `202`, `203`, `204`, `205`, `206`, `207`, `208`, `226`, `2xx`
- **--expected-body** A case-insensitive sub-string to look for in the response body.
- **--method** The method to use for the health check applicable to HTTP/HTTPS based checks. Valid values: `GET`, `HEAD`.
- **--path** The endpoint path to health check against.
- **--headers** The HTTP request headers to send in the health check.
- **--allow-insecure** Do not validate the certificate when monitor uses HTTPS. Valid values: `on`, `off`.
- **-i, --instance**: Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**: Specify output format. Currently, **json** is the only supported format.

### Examples
{: #create-glb-monitor-examples}

Create a GLB monitors in instance `dns-demo`.

```
ibmcloud dns glb-monitor-create --json @glb-monitor.json -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-monitor-update
{: #update-glb-monitor}

Update a GLB monitor for a service instance.

```
ibmcloud dns glb-monitor-update GLB_MON_ID (-j, --json @JSON_FILE | JSON_STRING) [-i, --instance INSTANCE] [--output FORMAT]

ibmcloud dns glb-monitor-update GLB_MON_ID [--name NAME] [--type TCP] [--port PORT] [--description DESCRIPTION] [--interval INTERVAL] [--retries RETRY] [--timeout TIMEOUT] [-i, --instance INSTANCE] [--output FORMAT]

ibmcloud dns glb-monitor-update GLB_MON_ID [--name NAME] [--type HTTP|HTTPS] [--expected-codes CODE] [--path PATH] [--port PORT] [--description DESCRIPTION] [--method GET|HEAD] [--headers HEADER1 --headers HEADER2...] [--interval INTERVAL] [--retries RETRY] [--timeout TIMEOUT] [--allow-insecure true|false] [--expected-body BODY] [--expected-codes CODE] [-i, --instance INSTANCE] [--output FORMAT]
```
{: pre}

### Command options
{: #update-glb-monitor-options}

- **GLB_MON_ID**<br />The ID of global load balancer monitor. Required.
- **--json**<br />The JSON file or JSON string used to describe a GLB monitor. Required.
   - The optional fields are `name`, `type`, `description`, `timeout`, `retries`, `interval`.
     - `name`: The name of the load balancer monitor.
     - `type`: The protocol to use for the health check. Valid values: `HTTP`, `HTTPS`, `TCP`.
     - `description`: The descriptive text of the load balancer monitor.
     - `timeout`: The timeout (in seconds) before marking the health check as failed. Valid values: `1-10`.
     - `retries`: The number of retries to attempt in case of a timeout before marking the origin as unhealthy. Valid values: `0-3`.
     - `interval`: The interval between each health check. Valid values: `5-3600`.
   - For `TCP` type health check. Extra option fields are `port`.
     - `port`: The TCP port to use for the health check.
   - For `HTTP/HTTPS` type health check. Extra option fields are `expected_codes`, `port`, `expected_body`, `method`, `path`, `header`, `allow_insecure`.
     - `expected_codes`: The expected HTTP response code or code range of the health check. Valid values: `200`, `201`, `202`, `203`, `204`, `205`, `206`, `207`, `208`, `226`, `2xx`.
     - `port`: The port number the health check connects to.
     - `expected_body`: A case-insensitive sub-string to look for in the response body.
     - `method`: The method to use for the health check applicable to HTTP/HTTPS based checks. Valid values: `GET`, `HEAD`.
     - `path`: The endpoint path to health check against.
     - `header`: The HTTP request headers to send in the health check.
     - `allow_insecure`: Do not validate the certificate when monitor use HTTPS. Valid values: `on`, `off`.

Sample JSON data:

For HTTP/HTTPS:

```
{
  "name": "glbmonitor",
  "description": "Health monitor of web service",
  "type": "HTTPS",
  "method": "GET",
  "path": "/health",
  "headers": [
    {
      "name": "Host",
      "value": ["glb.example.com"]
    },
    {
      "name": "X-App-ID",
      "value":["abc123"]
    }
  ],
  "port": 443,
  "timeout": 5,
  "retries": 2,
  "interval": 90,
  "allow_insecure": false,
  "expected_codes": "2xx",
  "expected_body": "alive"
}
```
{:codeblock}

For TCP:

```
{
  "name": "glbmonitor",
  "description": "Health monitor of TCP",
  "type": "TCP",
  "port": 80,
  "timeout": 5,
  "retries": 2,
  "interval": 90
}
```
{:codeblock}

- **--name** The name of the load balancer monitor.
- **--type** The protocol to use for the health check. Valid values: `HTTP`, `HTTPS`, `TCP`.
- **--description** The descriptive text of the load balancer monitor.
- **--timeout** The timeout (in seconds) before marking the health check as failed. Valid values: `1-10`.
- **--retries** The number of retries to attempt in case of a timeout before marking the origin as unhealthy. Valid values: `0-3`.
- **--interval** The interval between each health check. Valid values: `5-3600`.
- **--port** The port number the health check connects to.
- **--expected-codes** The expected HTTP response code or code range of the health check. Valid values: `200`, `201`, `202`, `203`, `204`, `205`, `206`, `207`, `208`, `226`, `2xx`
- **--expected-body** A case-insensitive sub-string to look for in the response body.
- **--method** The method to use for the health check applicable to HTTP/HTTPS based checks. Valid values: `GET`, `HEAD`.
- **--path** The endpoint path to health check against.
- **--headers** The HTTP request headers to send in the health check.
- **--allow-insecure** Do not validate the certificate when monitor uses HTTPS. Valid values: `on`, `off`.
- **-i, --instance**: Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**: Specify output format. Currently, **json** is the only supported format.

### Examples
{: #update-glb-monitor-examples}

Update GLB monitors `f1aba936b94213e5b8dca0c0dbf1f9cc` in instance `dns-demo`.

```
ibmcloud dns glb-monitor-update f1aba936b94213e5b8dca0c0dbf1f9cc --json @glb-monitor.json -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-monitor
{: #show-glb-monitor}

Show the details of a LB monitor.

```
ibmcloud dns glb-monitor GLB_MON_ID [-i, --instance INSTANCE] [--output FORMAT]
```
{: pre}

### Command options
{: #show-glb-monitor-options}

- **GLB_MON_ID**<br />The ID of global load balancer monitor. Required.
- **-i, --instance**<br />Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**<br />Specify output format. Currently, **json** is the only supported format.

### Examples
{: #show-glb-monitor-examples}

Show the details of GLB monitor `f1aba936b94213e5b8dca0c0dbf1f9cc`.

```
ibmcloud dns glb-monitor f1aba936b94213e5b8dca0c0dbf1f9cc -i "dns-demo"
```
{: pre}


## ibmcloud dns glb-monitor-delete
{: #delete-glb-monitor}

Delete the GLB monitor for a service instance.

```
ibmcloud dns glb-monitor-delete GLB_MON_ID [-i, --instance INSTANCE] [-f,--force]
```
{: pre}

### Command options
{: #delete-glb-monitor-options}

- **GLB_MON_ID**<br />The ID of global load balancer monitor. Required.
- **-i, --instance**<br />Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **-f, --force**<br />Delete load balancer monitor without prompting for confirmation.

### Examples
{: #delete-glb-monitor-examples}

Delete GLB monitor `f1aba936b94213e5b8dca0c0dbf1f9cc`.

```
ibmcloud dns glb-monitor-delete f1aba936b94213e5b8dca0c0dbf1f9cc -f -i "dns-demo"
```
{: pre}

## ibmcloud dns glb-monitors
{: #list-glb-monitors}

List GLB monitors for a service instance.

```
ibmcloud dns glb-monitors [-i, --instance INSTANCE] [--output FORMAT]
```
{: pre}

### Command options
{: #list-glb-monitors-options}

- **-i, --instance**<br />Instance name or ID. If not set, the context instance specified by `dns instance-target INSTANCE` is used.
- **--output**<br />Specify output format. Currently, **json** is the only supported format.

### Examples
{: #list-glb-monitors-examples}

List all GLB monitors for instance `dns-demo`.

```
ibmcloud dns glb-monitors -i "dns-demo"
```
{: pre}

