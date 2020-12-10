ASBRL-ALERTMANAGER
=========

Deploy a Prometheus as a Docker container.

Requirements
------------

Need to be Docker engine installed.

Role Variables
--------------

- SLACK_WEBHOOK_URL: "{{ ALERT_MANAGER_SLACK_WEBHOOK_URL }}" # Webhook of Slack
- SLACK_RECIPIENT: "{{ ALERT_MANAGER_SLACK_RECIPIENT }}" # Slack group or user id
- PORT: "{{ PROM_ALERT_MANAGER_PORT }}" # Port where Alermanager will run
- EXTERNAL_URL: "http://{{ TRAEFIK_HOSTNAME }}:{{ PROM_ALERT_MANAGER_PORT }}"  # External URL to access Alertmanager, for example this URL wibe attached in the Notifications

Dependencies
------------

None

Example Playbook
----------------

      - name: Deploy alertmanager
        include_role:
          name: asbrl-alertmanager
        vars:
            SLACK_WEBHOOK_URL: "{{ ALERT_MANAGER_SLACK_WEBHOOK_URL }}" # Webhook of Slack
            SLACK_RECIPIENT: "{{ ALERT_MANAGER_SLACK_RECIPIENT }}" # Slack group or user id
            PORT: "{{ PROM_ALERT_MANAGER_PORT }}" # Port where Alermanager will run
            EXTERNAL_URL: "http://{{ TRAEFIK_HOSTNAME }}:{{ PROM_ALERT_MANAGER_PORT }}"  # External URL to access Alertmanager, for example this URL will be attached in the Notifications
        tags:
        - asbrl-alertmanager

License
-------

BSD

Author Information
------------------

Moegui.com
