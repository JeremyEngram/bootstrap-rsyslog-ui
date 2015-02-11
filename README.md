#bootstrap-rsyslog-ui

Screenshot: https://raw.githubusercontent.com/hmsdao/bootstrap-rsyslog-ui/master/images/main.PNG

Installation
---
* Configure rsyslog according to (you can skip installation of LogAnalyzer): http://tecadmin.net/setup-rsyslog-with-mysql-and-loganalyzer/
* git clone "https://github.com/hmsdao/bootstrap-rsyslog-ui.git" /var/www/html/bootstrap-rsyslog-ui
* Copy /var/www/html/bootstrap-rsyslog-ui/config-template.php to /var/www/html/bootstrap-rsyslog-ui/config.php
* Edit config.php and correct mysql settings accordingly

Automating chart cache
---
* The charts are now based on cached json-files instead of querying the database each time the charts are drawned.
* This means you need to schedule a timer job each day.
* Example for crontab:
``` 
  1 0 * * * root "cd /var/www/html/maintenance; ./generate_reports_cache.sh"
```

Enjoy!
