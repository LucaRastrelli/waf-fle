WAF-FLE - Readme
===================

Web Application Firewall: Fast Log and Event Console

   Copyright (C) 2011 - 2014  Klaubert Herr 
   For new (released) versions, check at http://waf-fle.org
   WAF-FLE is relased under GPL v2 License

SUMMARY:
---------
WAF-FLE is a OpenSource ModSecurity Console, allows modsecurity admin
to store, view and search events sent by sensors using a graphical 
dashboard to drill-down and find quickly the most relevant events. It
is designed to be fast and flexible, while keeping a powerful and easy
to use filter, with almost all fields clickable to use on filter.

ABOUT THIS FORK:
---------
What's new:
   - PHP 8.x
   - Admin User and Normal User (read more later)
   - Zoom in Total Event Graphs
   - Removed APC references, now it supports only APCu
   - Updated SQL queries
   - ModSecurity 2.9.3+ (older versions in the next update)

To do:
   - Update Tags from OWASP Top 10 2021
   - Update graphs 
   - Update style
   - Everything that comes to mind

If you upgrade from version 0.6.x, you will need to update the DB. 
I'll try to create an automatic update file asap, but for now you will
have to update manually. A new column ('admin') has been added in the
'users' table. It is a tinyint(1) value that can assume two values:
 - 0: normal user
 - 1: admin user
 
You have also to expand the maximum char for the column 'a_uniqid' in
the 'events' table from char(24) to char(64).

Feel free to suggest new functionalities! 


FEATURES FROM MAIN FORK:
---------
   - Central event console
   - Support Modsecurity in “traditional” and “Anomaly Scoring”
   - Brings mlog2waffle as a replacement to mlogc
   - Receive events using mlog2waffle or mlogc
      - mlog2waffle: in real-time, following log tail, or batch scheduled in crontab
      - mlogc: in real-time, piped with ModSecurity log, in batch scheduled in crontab
   - No sensor limit
   - Drill down of events with filter
   - Dashboard with recent events information
   - Almost every event data and charts are “clickable” deepening the drill down filter
   - Inverted filter (to filter for “all but this item”)
   - Filter for network (in CIDR format, x.x.x.x/22)
   - Original format (Raw) to event download
   - Use Mysql as database
   - Wizard to help configure log feed between ModSecurity sensors and WAF-FLE
   - Open Source released under GPL v2

