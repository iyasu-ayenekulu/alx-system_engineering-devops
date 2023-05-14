MY FIRST POSTMORTEM
403 Error

An Outage Experience I Had
From 6PM to 7PM GMT, requests to our servers from all sources were receiving 403 errors. About 78% of our subscribers were trying to access our content but were denied access. This was as a result of an outbreak on the firewall on the load balancer

Timeline (All in Greenwich Mean Time)
5:30 PM – Our load balancer was being tuned.
5:50 PM – We received a complaint from the on-call management system that our site is not responding.
5:51 PM – The on-call person was trying to find out what was wrong with the load balancer.
5:59 PM – The on-call engineer escalated the task to other software engineers to check it out as well.
6 PM – The whole website was not accessible.
6:30 PM – The engineers found out the issue was with the firewall.
6:45 PM – Firewall traffic was cleaned up and unused rules were removed from the firewall to prevent accidents.
7 PM – The issue was completely resolved and the site was up and running.

Root cause and resolution
CAUSE: The load balancer was tuned and the firewall configuration was unconsciously affected. This caused a block on all ports except port 22. RESOLUTION: The issue was found out and firewall was configured to allow required ports.

Corrective and preventative measures
The following measures will be put in place to make sure the same thing never repeats itself:
  •    The firewall configuration files’ content will always be simple and clear.
  •    Burden on the firewall will be reduced by regularly removing unwanted traffic on the firewall.
