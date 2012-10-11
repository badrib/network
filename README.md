cloudflash-network
==================


*List of APIs*
=============

<table>
  <tr>
    <th>Verb</th><th>URI</th><th>Description</th>
  </tr>
  <tr>
    <td>GET</td><td>/network/interfaces</td><td>List summary of network interfaces configured</td>
  </tr>
  <tr>
    <td>POST</td><td>/network/interfaces</td><td>Create network interfaces configuration</td>
  </tr>
  <tr>
    <td>GET</td><td>/network/interfaces/:id</td><td>Describes an configured network by ID</td>
  </tr>
  <tr>
    <td>DELETE</td><td>/network/interfaces/:id</td><td>Delete an configured network by ID</td>
  </tr>
  <tr>     
    <td>POST</td><td>/network/dhcp/subnet</td><td>Update the DHCP configuration with subnet details in VCG</td>
  </tr>
  <tr>
      <td>GET</td><td>/network/dhcp/subnet/:id</td><td>Get subnet config from DHCP configuration by id</td>  
  </tr>
  <tr>
      <td>DELETE</td><td>/network/dhcp/subnet/:id</td><td>Delete subnet config from DHCP configuration by id</td>  
  </tr>
  <tr>
      <td>POST</td><td>/network/dhcp/router</td><td>Update the DHCP configuration with router details in VCG</td>
  </tr>
  <tr>
      <td>GET</td><td>/network/dhcp/router/:id</td><td>Get router config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>DELETE</td><td>/network/dhcp/router/:id</td><td>Delete router config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>POST</td><td>/network/dhcp/timesvr</td><td>Update the DHCP configuration with time server details in VCG</td>
  </tr>
  <tr>
      <td>GET</td><td>/network/dhcp/timesvr/:id</td><td>Get time server config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>DELETE</td><td>/network/dhcp/timesvr/:id</td><td>Delete time server config from DHCP configuration by id</td>
  </tr>  
  <tr>
      <td>POST</td><td>/network/dhcp/namesvr</td><td>Update the DHCP configuration with name server details in VCG</td>
  </tr>
  <tr>
      <td>GET</td><td>/network/dhcp/namesvr/:id</td><td>Get name server config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>DELETE</td><td>/network/dhcp/namesvr/:id</td><td>Delete name server config from DHCP configuration by id</td>
  </tr>
  
  <tr>
      <td>POST</td><td>/network/dhcp/dns</td><td>Update the DHCP configuration with DNS details in VCG</td>
  </tr>
  <tr>
      <td>GET</td><td>/network/dhcp/dns/:id</td><td>Get dns config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>DELETE</td><td>/network/dhcp/dns/:id</td><td>Delete dns config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>POST</td><td>/network/dhcp/logsvr</td><td>Update the DHCP configuration with  log server details in VCG</td>
  </tr>
  <tr>
      <td>GET</td><td>/network/dhcp/logsvr/:id</td><td>Get log server config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>DELETE</td><td>/network/dhcp/logsvr/:id</td><td>Delete log server config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>POST</td><td>/network/dhcp/cookiesvr</td><td>Update the DHCP configuration with cookie server details in VCG</td>
  </tr>
  <tr>
      <td>GET</td><td>/network/dhcp/cookiesvr/:id</td><td>Get cookie server config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>DELETE</td><td>/network/dhcp/cookiesvr/:id</td><td>Delete cookie server config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>POST</td><td>/network/dhcp/lprsvr</td><td>Update the DHCP configuration with lprsvr details in VCG</td>
  </tr>
  <tr>
      <td>GET</td><td>/network/dhcp/lprsvr/:id</td><td>Get lpr server config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>DELETE</td><td>/network/dhcp/lprsvr/:id</td><td>Delete lpr server config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>POST</td><td>/network/dhcp/ntpsrv</td><td>Update the DHCP configuration with NTP server details in VCG</td>
  </tr>
  <tr>
      <td>GET</td><td>/network/dhcp/ntpsrv/:id</td><td>Get ntp server config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>DELETE</td><td>/network/dhcp/ntpsrv/:id</td><td>Delete ntp server config from DHCP configuration by id</td>
  </tr>
  <tr>
      <td>POST</td><td>/network/dhcp/wins</td><td>Update the DHCP configuration with WINS details in VCG</td>
  </tr>
  <tr>
      <td>GET</td><td>/network/dhcp/wins/:id</td><td>Get win server config from DHCP configuration by id</td>
  </tr>

  <tr>
      <td>DELETE</td><td>/network/dhcp/wins/:id</td><td>Delete win server config from DHCP configuration by id</td>
  </tr>

  <tr>
      <td>GET</td><td>/network/dhcp/:id</td><td>Show DHCP config info in VCG specified by ID</td>
  </tr>

</table>



*Network API*
==============

 List Network
--------------

    Verb   URI                 Description
    GET  /network/interfaces   List summary of network interfaces configured.


Note: The request does not require a message body.
Success: Returns JSON data with list of network configured.


*Response*

```

    {
        "static": [
            {
                "device": "eth0:0",
                "inetaddr": "192.168.8.139",
                "netmask": "255.255.255.0",
                "gateway": ""
            }
        ]
    }

```

Configure Network
------------------


    Verb	URI	                Description
    POST	/network/interfaces      Create network interfaces configuration.

**Example Request and Response**

### Request JSON
         
    {
        "static": [
            {
                "device": "eth0",
                "inetaddr": "10.1.15.1",
                "netmask": "255.255.255.0",
                "broadcast": "169.254.255.255",
                "network": "169.254.255.255",
                "vlan": "vlan4",
                "hwaddress": "8c:89:a5:3d:f1:69",
                "gateway": "10.2.56.1",
                "up": {
                    "add": [
                        {
                            "net": "10.1.15.2",
                            "netmask": "255.255.255.0",
                            "gw": "10.1.15.1"
                         }
                    ]
                },
                "down": {
                    "del": [
                        {
                            "net": "10.1.15.3",
                            "netmask": "255.255.255.0",
                            "gw": "10.1.15.4"
                        }
                    ]
                }
            }
        ]
    }

### Response JSON

    {
        "result": "success"
    }


List a Network 
--------------

    Verb	URI	                   Description
    GET	/network/interfaces/:id	 Describes an configured network by name.


Note: The request does not require a message body.
Success: Returns JSON data with list of network configured.


*Response*

```

    {
        "device": "eth0",
        "status": "active",
        "txbytes": "72013",
        "rxbytes": "72013"
    }

```



Delete a network
----------------

    Verb	  URI	                     Description
    DELETE /network/interfaces/:id	   Delete an configured network by name.

On Success returns 200 with JSON data

*TODO: Return appropriate error code and description in case of failure.*

**Example Request and Response**

### Request Headers

    DELETE /network/interfaces/eth0

### Response JSON

    {
        "result": "success"
    }


Post DHCP subnet Configuration
-------------------------------

    Verb  URI	      		 Description
    POST	/network/dhcp/subnet	 Update the dhcp udhcpd.conf file in VCG.

On success it returns JSON data with the service-id, config success.

*TODO: Define JSON format for error codes and description.*

**Example Request and Response**

### Request Headers


### Request JSON

    {
           "start": "192.168.0.20",
           "end": "192.168.0.254",
           "interface": "eth0",
           "max_leases": 254,
           "remaining": "yes",
           "auto_time": 7200,
           "decline_time": 3600,
           "conflict_time": 3600,
           "offer_time": 60,
           "min_lease": 60,
           "lease_file": "/var/lib/misc/udhcpd.leases",
           "pidfile": "/var/run/udhcpd.pid",
           "notify_file": "dumpleases",
           "siaddr": "192.168.0.22",
           "sname": "zorak",
           "boot_file": "/var/lib/misc/udhcpd.leases",
           "option": ["subnet 192.168.0.25",
                      "timezone IST"]     
    }

### Response JSON


    {
      "id": "85108146-6233-42d9-8f1c-2c8fca63f236",
      "config":
      {
           "start": "192.168.0.20",
           "end": "192.168.0.254",
           "interface": "eth0",
           "max_leases": 254,
           "remaining": "yes",
           "auto_time": 7200,
           "decline_time": 3600,
           "conflict_time": 3600,
           "offer_time": 60,
           "min_lease": 60,
           "lease_file": "/var/lib/misc/udhcpd.leases",
           "pidfile": "/var/run/udhcpd.pid",
           "notify_file": "dumpleases",
           "siaddr": "192.168.0.22",
           "sname": "zorak",
           "boot_file": "/var/lib/misc/udhcpd.leases",
           "option": ["subnet 192.168.0.25",
                      "timezone IST"]     
      }      
    }

Upon error, error code 500 will be returned


Post DHCP router Configuration
-------------------------------

    Verb        URI	   		 Description
    POST	/network/dhcp/router	 Update the dhcp udhcpd.conf file in VCG.

On success it returns JSON data with the service-id, service-name, config success.

*TODO: Define JSON format for error codes and description.*

**Example Request and Response**

### Request Headers


### Request JSON

    {
        "optionparam": "router",
        "address": [
        "192.10.0.40",
        "192.10.0.41"
        ]
    }

### Response JSON


    {
        "id": "85108146-6233-42d9-8f1c-2c8fca63f236",
        "config":
        {
           "optionparam": "router",
           "address": [
           "192.10.0.40",
           "192.10.0.41"
         ]
        } 
    }


Upon error, error code 500 will be returned


Post DHCP time server  Configuration
-------------------------------------

    Verb    URI        		         Description
    POST    /network/dhcp/timesvr	 Update the dhcp udhcpd.conf file in VCG.

On success it returns JSON data with the service-id, service-name, config success.

*TODO: Define JSON format for error codes and description.*

**Example Request and Response**

### Request Headers


### Request JSON

    {
        "optionparam": "timesvr",
        "address": [
        "192.10.0.40",
        "192.10.0.41"
         ]
    }

### Response JSON


    {
        "id": "85108146-6233-42d9-8f1c-2c8fca63f236",
         "config":
         {
            "optionparam": "timesvr",
            "address": [
            "192.10.0.40",
            "192.10.0.41"
            ]
        }
    }


Upon error, error code 500 will be returned



Post DHCP name server Configuration
-----------------------------------

    Verb    URI        		         Description
    POST    /network/dhcp/namesvr	 Update the dhcp udhcpd.conf file in VCG.

On success it returns JSON data with the service-id, service-name, config success.

*TODO: Define JSON format for error codes and description.*

**Example Request and Response**

### Request Headers


### Request JSON

    {
        "optionparam": "namesvr",
        "address": [
        "192.10.0.40",
        "192.10.0.41"
        ]
    }

### Response JSON


    {
        "id": "85108146-6233-42d9-8f1c-2c8fca63f236",
        "config":
        {
            "optionparam": "namesvr",
            "address": [
            "192.10.0.40",
            "192.10.0.41"
           ]
        }
    }


Upon error, error code 500 will be returned



Post DHCP dns Configuration
----------------------------

    Verb    URI      		      Description
    POST    /network/dhcp/dns  	      Update the dhcp udhcpd.conf file in VCG.

On success it returns JSON data with the service-id, service-name, config success.

*TODO: Define JSON format for error codes and description.*

**Example Request and Response**

### Request Headers


### Request JSON

    {
        "optionparam": "dns",
        "address": [
        "192.10.0.40",
        "192.10.0.41"
        ]
    }

### Response JSON


    {
        "id": "85108146-6233-42d9-8f1c-2c8fca63f236",
        {
            "optionparam": "dns",
            "address": [
            "192.10.0.40",
            "192.10.0.41"
            ]
        }

    }


Upon error, error code 500 will be returned


Post DHCP log server Configuration
-----------------------------------

    Verb    URI        		         Description
    POST    /network/dhcp/logsvr	 Update the dhcp udhcpd.conf file in VCG.

On success it returns JSON data with the service-id, service-name, config success.

*TODO: Define JSON format for error codes and description.*

**Example Request and Response**

### Request Headers


### Request JSON

    {
        "optionparam": "logsvr",
        "address": [
        "192.10.0.40",
        "192.10.0.41"
        ]
    }

### Response JSON


    {
        "id": "85108146-6233-42d9-8f1c-2c8fca63f236",
        "config":
        {
            "optionparam": "logsvr",
            "address": [
            "192.10.0.40",
            "192.10.0.41"
            ]
        }

    }


Upon error, error code 500 will be returned


Post DHCP cookie server Configuration
--------------------------------------

    Verb    URI        		         Description
    POST    /network/dhcp/cookiesvr	 Update the dhcp udhcpd.conf file in VCG.

On success it returns JSON data with the service-id, service-name, config success.

*TODO: Define JSON format for error codes and description.*

**Example Request and Response**

### Request Headers


### Request JSON

    {
        "optionparam": "cookiesvr",
        "address": [
        "192.10.0.40",
        "192.10.0.41"
         ]
    }

### Response JSON


    {
        "id": "85108146-6233-42d9-8f1c-2c8fca63f236",
        "config": 
        {
            "optionparam": "cookiesvr",
            "address": [
            "192.10.0.40",
            "192.10.0.41"
            ]
        }
    }


Upon error, error code 500 will be returned


Post DHCP lpr server Configuration
--------------------------------------

    Verb    URI          	         Description
    POST    /network/dhcp/lprsvr	 Update the dhcp udhcpd.conf file in VCG.

On success it returns JSON data with the service-id, service-name, config success.

*TODO: Define JSON format for error codes and description.*

**Example Request and Response**

### Request Headers


### Request JSON

    {
        "optionparam": "lprsvr",
        "address": [
        "192.10.0.40",
        "192.10.0.41"
        ]
    }

### Response JSON


    {
        "id": "85108146-6233-42d9-8f1c-2c8fca63f236",
        "config":
        {
            "optionparam": "lprsvr",
            "address": [
            "192.10.0.40",
            "192.10.0.41"
            ]
        }
    }


Upon error, error code 500 will be returned


Post DHCP ntp server Configuration
--------------------------------------

    Verb    URI          	        Description
    POST    /network/dhcp/ntpsrv	Update the dhcp udhcpd.conf file in VCG.

On success it returns JSON data with the service-id, service-name, config success.

*TODO: Define JSON format for error codes and description.*

**Example Request and Response**

### Request Headers


### Request JSON

    {
        "optionparam": "ntpsrv",
        "address": [
        "192.10.0.40",
        "192.10.0.41"
        ]
    }

### Response JSON


    {
        "id": "85108146-6233-42d9-8f1c-2c8fca63f236",
        "config:
        {
            "optionparam": "ntpsrv",
            "address": [
            "192.10.0.40",
            "192.10.0.41"
            ]
        }

    }


Upon error, error code 500 will be returned

Post DHCP wins server Configuration
------------------------------------

    Verb    URI          	    Description
    POST    /network/dhcp/wins	    Update the dhcp udhcpd.conf file in VCG.

On success it returns JSON data with the service-id, service-name, config success.

*TODO: Define JSON format for error codes and description.*

**Example Request and Response**

### Request Headers


### Request JSON

    {
        "optionparam": "wins",
        "address": [
        "192.10.0.40",
        "192.10.0.41"
        ]
    }

### Response JSON

    {
        "id": "85108146-6233-42d9-8f1c-2c8fca63f236",
        "config:
        {
            "optionparam": "wins",
            "address": [
            "192.10.0.40",
            "192.10.0.41"
            ]
        }

    }

Upon error, error code 500 will be returned




Delete subnet config from DHCP configuration
---------------------------------------------

    Verb	URI	                          Description
    DELETE      /network/dhcp/subnet/:id 	  Delete subnet config from udhcpd.conf file


On Success returns 200 with JSON data

**Example Request and Response**

### Request Headers

    DELETE  /network/dhcp/subnet/85108146-6233-42d9-8f1c-2c8fca63f236
    
### Response JSON

    { "deleted": "success" }
    

Delete router config from DHCP configuration
---------------------------------------------

    Verb    URI	                          Description
    DELETE  /network/dhcp/router/:id 	  Delete router config from udhcpd.conf file


On Success returns 200 with JSON data

**Example Request and Response**

### Request Headers

    DELETE  /network/dhcp/router/85108146-6233-42d9-8f1c-2c8fca63f236
    
### Response JSON

    { "deleted": "success" }


Delete time server config from DHCP configuration
--------------------------------------------------

    Verb    URI	                          Description
    DELETE  /network/dhcp/timesvr/:id 	  Delete time server config from udhcpd.conf file


On Success returns 200 with JSON data

**Example Request and Response**

### Request Headers

    DELETE  /network/dhcp/timesvr/85108146-6233-42d9-8f1c-2c8fca63f236
    
### Response JSON

    { "deleted": "success" }



Delete name server config from DHCP configuration
--------------------------------------------------

    Verb    URI	                          Description
    DELETE  /network/dhcp/namesvr/:id 	  Delete name server config from udhcpd.conf file


On Success returns 200 with JSON data

**Example Request and Response**

### Request Headers

    DELETE  /network/dhcp/namesvr/85108146-6233-42d9-8f1c-2c8fca63f236
    
### Response JSON

    { "deleted": "success" }



Delete dns config from DHCP configuration
------------------------------------------

    Verb    URI	                          Description
    DELETE  /network/dhcp/dns/:id 	  Delete dns config from udhcpd.conf file


On Success returns 200 with JSON data

**Example Request and Response**

### Request Headers

    DELETE  /network/dhcp/dns/85108146-6233-42d9-8f1c-2c8fca63f236
    
### Response JSON

    { "deleted": "success" }


Delete log server config from DHCP configuration
-------------------------------------------------

    Verb    URI	                          Description
    DELETE  /network/dhcp/logsvr/:id 	  Delete log server config from udhcpd.conf file


On Success returns 200 with JSON data

**Example Request and Response**

### Request Headers

    DELETE  /network/dhcp/logsvr/85108146-6233-42d9-8f1c-2c8fca63f236
    
### Response JSON

    { "deleted": "success" }



Delete cookie server config from DHCP configuration
----------------------------------------------------

    Verb    URI	                                  Description
    DELETE  /network/dhcp/cookiesvr/:id 	  Delete cookie server config from udhcpd.conf file


On Success returns 200 with JSON data

**Example Request and Response**

### Request Headers

    DELETE  /network/dhcp/cookiesvr/85108146-6233-42d9-8f1c-2c8fca63f236
    
### Response JSON

    { "deleted": "success" }



Delete lpr server config from DHCP configuration
-------------------------------------------------

    Verb    URI	                          Description
    DELETE  /network/dhcp/lprsvr/:id 	  Delete lpr server config from udhcpd.conf file


On Success returns 200 with JSON data

**Example Request and Response**

### Request Headers

    DELETE  /network/dhcp/lprsvr/85108146-6233-42d9-8f1c-2c8fca63f236
    
### Response JSON

    { "deleted": "success" }


Delete ntp server config from DHCP configuration
-------------------------------------------------

    Verb    URI	                          Description
    DELETE  /network/dhcp/ntpsrv/:id 	  Delete ntp server config from udhcpd.conf file


On Success returns 200 with JSON data

**Example Request and Response**

### Request Headers

    DELETE  /network/dhcp/ntpsrv/85108146-6233-42d9-8f1c-2c8fca63f236
    
### Response JSON

    { "deleted": "success" }


Delete wins config from DHCP configuration
-------------------------------------------

    Verb    URI	                          Description
    DELETE  /network/dhcp/wins/:id 	  Delete win server config from udhcpd.conf file


On Success returns 200 with JSON data

**Example Request and Response**

### Request Headers

    DELETE  /network/dhcp/wins/85108146-6233-42d9-8f1c-2c8fca63f236
    
### Response JSON

    { "deleted": "success" }





Describe DHCP 
--------------

    Verb    URI	                  Description
    GET	    /network/dhcp/:id	  Show DHCP config info in VCG specified by service-ID

**Example Request and Response**

### Request Headers

    GET /network/dhcp/2da8f435-42c1-45d2-9fad-04fdf7298c80

### Response JSON

    {
            "key":"2da8f435-42c1-45d2-9fad-04fdf7298c80",
            "val":
              {
                   "start":"192.168.0.20",
                    "end":"192.168.0.254",
                    "interface":"eth0",
                    "max_leases":254,
                    "remaining":"yes",
                    "auto_time":7200,
                    "decline_time":3600,
                    "conflict_time":3600,
                    "offer_time":60,
                    "min_lease":60,
                    "lease_file":"/var/lib/misc/udhcpd.leases",
                    "pidfile":"/var/run/udhcpd.pid",
                    "notify_file":"dumpleases",
                    "siaddr":"192.168.0.22",
                    "sname":"zorak",
                    "boot_file":"/var/lib/misc/udhcpd.leases",
                    "option":
                    [
                      "subnet 192.168.0.25",
                      "timezone IST"
                    ]
                }
    }
    

Please note that the top-level `id` returned above refers to the service-ID.

Upon error, error code 500 will be returned

