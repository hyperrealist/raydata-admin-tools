`raydata` tool provides convenience commandline functions for administrating and monitoring raydata-related services.

Example usage:

```sh
raydata start
# this is equivalent to the following set of commands entered in sequence.
#  systemctl start sirepo_job_supervisor.service 
#  systemctl start sirepo@7000.service 
#  systemctl start sirepo@7001.service 
#  systemctl start sirepo@7002.service 
#  systemctl start sirepo@7003.service 
#  systemctl start raydata_scan_monitor.service

raydata stop
# corresponding stop command, issued in reverse order

raydata restart
# shorthand for raydata stop; raydata start

raydata status
# issues a command equivalent to
#  systemctl -n 0 status <all raydata services>

raydata journal
# issues a command equivalent to
#  journalctl -f -u <raydata service 1> -u <raydata service 2> ...
```
