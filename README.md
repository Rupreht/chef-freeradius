Description
====

Installs Freeradius

Requirements
====



Usage
====

{
    "clients": [
        {
            "name": "host1",
            "shortname": "local",
            "ipaddr": "127.0.0.1",
            "netmask": "255.0.0.0",
            "login": "!root",
            "secret": "remote1234",
            "nastype": "other",
            "req_msg": "no"
        }
    ],
    "per_socket_clients": [
        {
            "ip": "192.168.0.1",
            "secret": "remote1234",
            "shortname": "private-network"
        }
    ],
    "users": [
        {
            "name": "DEFAULT",
            "checkItem": "User-Group == \"bb\", Huntgroup-Name == \"ASR3001\"",
            "replyItem": "Cisco-AVPair == \"ip:addr-pool=3\",Cisco-AVPair == \"lcp:interface-config=ip policy route-map net172-proxy\",Fall-Through = no"
        }
    ],
    "huntgroups": [
        {
            "name": "ASR3001",
            "checkItem": "NAS-IP-Address == 127.0.0.2",
            "replyItem": ""
        }
    }

License and Author
====

Author:: Nicholas Maloney (<ngmaloney@gmail.com>)

Copyright:: 2012 NM Consulting

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
