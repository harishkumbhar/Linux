- name: Update NR script crontab timing
  replace:
    path: /var/spool/cron/root  # Use the appropriate user's crontab file
    regexp: '^#?00 02 \* \* 05 (bash /script/host_entry_CBS_change_NR.sh)'
    replace: '00 02 * * 06 \1'
