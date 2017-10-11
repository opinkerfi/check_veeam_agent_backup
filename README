# check_veeam_agent_backup

Simple Nagios plugin that checks the status of veeam agent backup for last 24 hours

## How to use with okconfig

```shell
mkdir -p /etc/nagios/okconfig/templates/veeam

cat << EOF > /etc/nagios/okconfig/templates/veeam/commands.cfg
# Plugin info
# https://github.com/opinkerfi/check_veeam_agent_backup
#
define command {
  command_name okc-veeam-check_veeam_agent_backup
  command_line $USER1$/check_nrpe -H $HOSTADDRESS$ -c check_veeam_agent_backup
}

EOF

cat << EOF > /etc/nagios/okconfig/templates/veeam/services.cfg
# Plugin info
# https://github.com/opinkerfi/check_veeam_agent_backup
#

define service {
        name                    okc-veeam-service
        use                     generic-service
        icon_image              signal.png
        register                0
}

define service {
        name                    okc-veeam-check_veeam_agent_backup
        service_description     Veeam agent backup status
        use                     okc-veeam-service
        check_command           okc-veeam-check_veeam_agent_backup
        register                0
}

EOF

```

