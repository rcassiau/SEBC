```
[root@ip-172-31-43-15 ~]# cat /etc/krb5.conf
[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = RCASSIAU.IBM
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 udp_preference_limit = 1
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac 

[realms] 
  RCASSIAU.IBM = {
  kdc = ip-172-31-39-234.eu-west-1.compute.internal
  admin_server = ip-172-31-39-234.eu-west-1.compute.internal
 }

[domain_realm]
   .eu-west-1.compute.internal = RCASSIAU.IBM
   eu-west-1.compute.internal = RCASSIAU.IBM
```
