Order of Playbooks

1. controller playbook to install needed packages on workstation.
2. deploy_haproxy.yml
3. deploy_apache.yml
4. deploy_webapp.yml
5. Run a command to monitor the service on servera (in a different terminal/tab):

[student@workstation ~]$ while true; do
> curl servera
> sleep 0.1
> done

6. webapp_update_rolling.yml


