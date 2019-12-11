---

copyright:
  years: 2019
lastupdated: "2019-12-03"

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


# DNS Services CLI commands
{: #dns-services-cli-commands}

Follow these instructions to use DNS Services Command Line Interface.
{: shortdesc}

## Install DNS Services CLI plugin
{: #install-dns-services-cli-plugin}
  
1. Install the [IBM Cloud CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli).
1. Install or update the `cloud-dns-services` CLI plugin to the IBM Cloud CLI.

To install:

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

## Resource instance
{: #resource-instance}

Manipulate DNS Services instances by using the following `instance` commands.

### List DNS Services instances
{: #list-dns-services-instances}

**NAME**

   `instances` - List all DNS Services instances.

**USAGE**

   `ibmcloud dns instances [--output FORMAT]`

**OPTIONS**

   `--output`  Specify output format, only JSON is supported.


### Set Context DNS Services instance
{: #set-context-DNS-service-instance}

**NAME**

   `instance-target` - Set context service instance to operate.

**USAGE**

   `dns instance-target [INSTANCE] [--unset]`

**ARGUMENTS**

   INSTANCE is the name or ID of a DNS Services instance. If it is present, set the context instance to operate; if not, show the current context instance.

**OPTIONS**

   `--unset`  Unset context instance.


### Create DNS Services instance
{: #create-DNS-services-instance}

**NAME**

   `instance-create` - Create a DNS Services instance

**USAGE**

   `ibmcloud dns instance-create INSTANCE_NAME PLAN [--output FORMAT]`

**ARGUMENTS**

   INSTANCE_NAME is the name of the DNS Services instance.

   PLAN is the name or ID of a service plan.

**OPTIONS**

   `--output`  Specify output format, only JSON is supported.


### Delete DNS Service instance
{: #delete-DNS-services-instance}

**NAME**

   `instance-delete` - Delete a DNS Services instance.

**USAGE**

   `ibmcloud dns instance-delete INSTANCE [--force]` 

**ARGUMENTS**

   INSTANCE is the name or ID of a DNS Services instance.

**OPTIONS**

   `--force`  Delete instance without prompting for confirmation.


### Get DNS Service instance
{: #get-DNS-service-instance}

**NAME**

   `instance` - Show details of a DNS Services instance.

**USAGE**

   `ibmcloud dns instance INSTANCE [--output FORMAT]` 

**ARGUMENTS**

   INSTANCE is the name or ID of a DNS Services instance.

**OPTIONS**

   `--output`  Specify output format, only JSON is supported.


### List DNS Services plans
{: #list-DNS-services-plans}

**NAME**

   `plans` - List all DNS Services instances.

**USAGE**

   `ibmcloud dns plans` 


## Zone
{: #zone}

Manipulate DNS zones by using the following `zone` commands.

### Create DNS Zone
{: #create-zone}

**NAME**

   `zone-create` - Create a DNS zone.

**USAGE**

   `ibmcloud dns zone-create ZONE_NAME [-d, --description DESC] [-l, --label LABEL] [-i, --instance INSTANCE_NAME] [--output FORMAT]`

**ARGUMENTS**

   `ZONE_NAME` is the name of the DNS zone.

**OPTIONS**

   `-d, --description` The text describing the purpose of a DNS zone.

   `-l, --label` The label of a DNS zone.

   `-i, --instance INSTANCE_NAME`  Instance name. If not set, the context instance specified by `ibmcloud dns instance-set` is used.

   `--output FORMAT`    Specify output format, only JSON is supported.

**Output**
  * ID                     
  * Created On         
  * Modified On
  * Instance ID  
  * Name                   
  * Description
  * State                
  * Label        

### Get zone details
{: #get-zone}

**NAME**

   `zone` - Get the given DNS zone details.

**USAGE**

   `ibmcloud dns zone ZONE_ID [-i, --instance INSTANCE_NAME] [--output FORMAT]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

**OPTIONS**

   `-i, --instance INSTANCE_NAME`  Instance name. If not set, the context instance specified by `ibmcloud dns instance-set` is used.

   `--output FORMAT`    Specify output format, only JSON is supported.

**Output**
  * ID                     
  * Created On         
  * Modified On
  * Instance ID  
  * Name                   
  * Description
  * State                
  * Label     
  

### Update zone
{: #update-zone}

**NAME**

   `zone-update` - Update a DNS zone's description and label.

**USAGE**

   `ibmcloud dns zone-update ZONE_ID [-d, --description DESC] [-l, --label LABEL] [--instance INSTANCE_NAME] [--output FORMAT]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

**OPTIONS**

   `-d, --description` The text describing the purpose of a DNS zone.

   `-l, --label` The label of a DNS zone.

   `-i, --instance INSTANCE_NAME`  Instance name. If not set, the context instance specified by `ibmcloud dns instance-set` is used.

   `--output FORMAT`    Specify output format, only JSON is supported.

**Output**
  * ID                     
  * Created On         
  * Modified On
  * Instance ID  
  * Name                   
  * Description
  * State                
  * Label    

### Delete zone
{: #delete-zone}

**NAME**

   `zone-delete` - Delete a DNS zone.

**USAGE**

   `ibmcloud dns zone-delete ZONE_ID [--force] [-i, --instance INSTANCE_NAME]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

**OPTIONS**
   
   `--force`  Delete zone without prompting for confirmation.

   `-i, --instance INSTANCE_NAME`  Instance name. If not set, the context instance specified by `ibmcloud dns instance-set` is used.



### List zones
{: #list-zones}

**NAME**

   `zones` - List all DNS zones for a given service instance.

**USAGE**

   `ibmcloud dns zones [-i, --instance INSTANCE_NAME] [--output FORMAT]`

**OPTIONS**

   `-i, --instance INSTANCE_NAME`  Instance name. If not set, the context instance specified by `ibmcloud dns instance-set` is used.

   `--output FORMAT`    Specify output format, only JSON is supported.


**Output**

    List of DNS zones


## Permitted network
{: #permitted-network}

Manipulate permitted networks by using the following `permitted-network` commands.

### Add permitted network
{: #add-permitted-network}

**NAME**

   `permitted-network-add` - Add a permitted network for a given DNS zone.

**USAGE**

   `ibmcloud dns permitted-network-add ZONE_ID --type TYPE --vpc-crn VPC_CRN [-i, --instance INSTANCE_NAME] [--output FORMAT]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

**OPTIONS**

   `--type`   The permitted network type. Valid values: "vpc".

   `--vpc-crn`  The CRN of VPC instance 

   `-i, --instance INSTANCE_NAME`  Instance name. If not set, the context instance specified by `ibmcloud dns instance-set` is used.

   `--output FORMAT`    Specify output format, only JSON is supported.

**Output**
  * ID                     
  * Created On         
  * Modified On
  * Permitted Network data  
  * Type    

### Get Permitted network details
{: #get-permitted-network}

**NAME**

   `permitted-network` - Get the given permitted network details.

**USAGE**

   `ibmcloud dns permitted-network ZONE_ID PERMITTED_NETWORK_ID [-i, --instance INSTANCE_NAME] [--output FORMAT]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

   `PERMITTED_NETWORK_ID` is the ID of the permitted network.

**OPTIONS**

   `-i, --instance INSTANCE_NAME`  Instance name. If not set, the context instance specified by `ibmcloud dns instance-set` is used.

   `--output FORMAT`    Specify output format, only JSON is supported.

**Output**
  * ID                     
  * Created On         
  * Modified On
  * Permitted Network data  
  * Type    
  

### Remove permitted network
{: #Remove-permitted-network}

**NAME**

   `permitted-network-remove` - Remove a permitted network.

**USAGE**

   `ibmcloud dns permitted-network-remove ZONE_ID PERMITTED_NETWORK_ID [--force] [-i, --instance INSTANCE_NAME]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

   `PERMITTED_NETWORK_ID` is the ID of the permitted network.

**OPTIONS**

   `--force`  Remove permitted network without prompting for confirmation.

   `--instance INSTANCE_NAME`  Instance name. If not set, the context instance specified by `ibmcloud dns instance-set` is used.

**Output**


### List permitted networks
{: #list-permitted-networks}

**NAME**

  permitted-networks - List permitted networks for a given zone.

**USAGE**

   `ibmcloud dns permitted-networks ZONE_ID [-i, --instance INSTANCE_NAME] [--output FORMAT]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

**OPTIONS**

   `-i, --instance INSTANCE_NAME`  Instance name. If not set, the context instance specified by `ibmcloud dns instance-set` is used.

   `--output FORMAT`    Specify output format, only JSON is supported.


**Output**

  List of permitted networks


## Resource record
{: #resource-record}

Manipulate how the resource record performs using the following `resource-record` commands:

### Create resource record
{: #create-resource-record}

**NAME**

   `resource-record-create` - Create a resource record for a given DNS zone.

**USAGE**

   `ibmcloud dns resource-record-create ZONE_ID (-s, --json-str JSON_STR | -j, --json-file JSON_FILE) [-i, --instance INSTANCE_NAME] [--output FORMAT]`

**ARGUMENTS**

   * `ZONE_ID` is the ID of the DNS zone.

**OPTIONS**

   `-s, --json-str`  The JSON data used to describe a resource record.

   Supported Resource Record types are: `A`, `AAAA`, `CNAME`, `PTR`, `TXT`, `MX`, `SRV`.

   * For type `A`, `AAAA`, `CNAME`, `PTR`, `TXT`:
     * The required fields in JSON data are `name`, `type`, `rdata`
     * The optional field is `ttl`

   Sample JSON data:


                   {
                       "name": "testA",
                       "type": "A",
                       "rdata": {
                           "ip": "1.2.3.4"
                         }
                   }

                   {
                       "name": "testAAAA",
                       "type": "AAAA",
                       "rdata": {
                           "ip": "2001:0db8:0012:0001:3c5e:7354:0000:5db1"
                       }                       
                   }

                   {
                       "name": "testCNAME",
                       "type": "CNAME",
                       "rdata": {
                           "cname": "example.com"
                       }
                   }

                   {
                       "name": "1.2.3.4",
                       "type": "PTR",
                       "rdata": {
                           "ptrdname": "testA.example.com"
                       }
                   }

                   {
                       "name": "testTXT",
                       "type":"TXT",
                       "rdata": {
                           "text": "text information" t
                       }
                   }

   * For type `MX`:
     * The required fields in JSON data are `name`, `type`, `rdata`:

        "rdata":

            `preference`: Preference of the MX record

            `exchange`: Hostname of Exchange server

     * The optional field is `ttl`

   Sample JSON data:

                    {
                       "name": "testMX",
                       "type": "MX",
                       "rdata": {
                            "preference": 10,
                            "exchange": "mailserver.example.com"
                        }
                    }

   * For type `SRV`:
     * The required fields in JSON data are `type`, `name`, `service`, `protocol`, `rdata`

        "rdata":

            `priority`: Priority of the record.

            `weight`: Weight of distributing queries among multiple target servers.

            `port`: Port number of the target server.

            `target`: Hostname of the target server.

     * The optional field is `ttl`.

   Sample JSON data:

                    {
                       "type": "SRV",
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

   `-j, --json-file`  A file contains input JSON data.

   `-i, --instance INSTANCE_NAME`   Instance name. If the name is not set, the context instance specified by `ibmcloud dns instance-set` is used.

   `--output FORMAT`     Specify output format, only JSON is supported.


### Update resource record
{: #update-resource-record}

**NAME**

   `resource-record-update` - Update a resource record for a given DNS zone.

**USAGE**

   `ibmcloud dns resource-record-update ZONE_ID RECORD_ID (-s, --json-str JSON_STR | -j, --json-file JSON_FILE) [-i, --instance INSTANCE_NAME] [--output FORMAT]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

   `RECORD_ID` is the ID of the record.

**OPTIONS**

    `-s, --json-str`  The JSON data used to describe a DNS Record.

    The required fields in JSON data are "name".

        "name": Resource record name. 
        PTR records DO NOT need this field.
        {: note}

    * For type A, AAAA:

        Extra required fields are "rdata".

            "rdata": Content of the resource record.
                "ip": IPv4/IPv6 address

        Extra option fields are "ttl".

            "ttl": Time to live for DNS record. Default value is 60.

        Sample JSON data:


        {
             "name": "testA",
             "rdata": {
                 "ip": "1.2.3.4"
            }
        }

        {
            "name": "testAAAA",
            "rdata": {
                "ip": "2001:0db8:0012:0001:3c5e:7354:0000:5db1"
            }
        }

    * For type CNAME:

        Extra required fields are "rdata".

            "rdata": The content of type-PTR resource record.
                "cname": Canonical name

        Extra option fields are "ttl".

            "ttl": Time to live for DNS record. Default value is 60.

        Sample JSON data:


        {
            "name": "testCNAME",
            "rdata": {
                "cname": "example.com"
            }
        }


    * For type PTR:

        Extra option fields are "ttl".

            "ttl": Time to live for DNS record. Default value is 60.

        Sample JSON data:


        {
            "ttl": 360,
        }


    * For type TXT:

        Extra required fields are "rdata".

            "rdata": The content of type-TXT resource record.
                "text": Human readable text.

        Extra option fields are "ttl".

            "ttl": Time to live for DNS record. Default value is 60.

        Sample JSON data:


        {
            "name": "testTXT",
            "rdata": {
                "text": "text information"
            }
        }


    * For type MX:

        Extra required fields are "rdata".

            "rdata": The content of type-MX resource record.
                "exchange": Hostname of Exchange server.
                "preference": Preference of the MX record

        Extra option fields are "ttl".

            "ttl": Time to live for DNS record. Default value is 60.

        Sample JSON data:


        {
            "name": "testMX",
            "content": "smtp.example.com",
            "priority": 10
        }


    * For type SRV:

        Extra required fields are "rdata", "service", "protocol".

            "rdata": The content of type-SRV resource record.
                "priority": Priority of the SRV record
                "weight": Weight of distributing queries among multiple target servers.
                "port": Port number of the target server.
                "target": Hostname of the target server.
            "service": The symbolic name of the desired service, start with an underscore (_).
            "protocol": The symbolic name of the desired protocol.

        Extra option fields are "ttl".

            "ttl": Time to live for DNS record. Default value is 60.

        Sample JSON data:


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
                   
   `-j, --json-file`   A file contains input JSON data.

   `-i, --instance INSTANCE_NAME`   Instance name. If the name is not set, the context instance specified by `ibmcloud dns instance-set` is used.

   `--output FORMAT`     Specify output format, only JSON is supported.


### Get resource record
{: #get-resource-record}

**NAME**

   `resource-record` - Get a resource record details for a given DNS zone.

**USAGE**

   `ibmcloud dns resource-record ZONE_ID RECORD_ID [-i, --instance INSTANCE_NAME] [--output FORMAT]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

   `RECORD_ID` is the ID of resource record.

**OPTIONS**

   `-i, --instance INSTANCE_NAME`  Instance name. If the name is not set, the context instance specified by `ibmcloud dns instance-set` is used.

   `--output FORMAT`    Specify output format, only JSON is supported.


### Delete resource record
{: #delete-resource-record}

**NAME**

   `resource-record-delete` - Delete a resource record for a given DNS zone.

**USAGE**

   `ibmcloud dns resource-record-delete ZONE_ID RECORD_ID [--force] [-i, --instance INSTANCE_NAME]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

   `RECORD_ID` is the ID of resource record.

**OPTIONS**

   `--force`  Delete resource record without prompting for confirmation.

   `-i, --instance INSTANCE_NAME`  Instance name. If the name is not set, the context instance specified by `ibmcloud dns instance-set` is used.
   
   

### List resource records
{: #list-resource-record}

**NAME**

   `resource-records` - List all resource records for a given DNS zone.

**USAGE**

   `ibmcloud dns resource-records ZONE_ID (-s, --json-str JSON_STR | -j, --json-file JSON_FILE) [-i, --instance INSTANCE_NAME] [--output FORMAT]`

**ARGUMENTS**

   `ZONE_ID` is the ID of the DNS zone.

**OPTIONS**

   `-s, --json-str`  The JSON data to query resource records.

**Output table columns**
   * ID
   * Name
   * Type
   * Rdata
   * TTL
