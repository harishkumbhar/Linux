
---
- name: Update NR script crontab timing
  hosts: cbs
  become: yes
  tasks:
    - name: change time
      replace:
        path: /var/spool/cron/root
        regexp: '^#?00 02 \* \* 05 (bash /script/host_entry_CBS_change_NR.sh)'
        replace: '00 02 * * 06 \1'
