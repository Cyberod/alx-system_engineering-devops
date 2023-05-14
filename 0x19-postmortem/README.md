# Server Outage Incident report
> By IFEANYI JONATHAN (Cyberod)
<img src="https://github.com/Cyberod/alx-system_engineering-devops/assets/110993874/df285582-3980-4ed4-b700-d1bd77f5c6c8" alt="What did" width="700" height="400">

## Issue Summary
By 8:00PM GMT+1 on the 27th of March 2023 i was unable to connect to my web-server_02 through ssh but I was able to re-instate it by 8:40PM and my web-servers were able to work correctly. The root cause of the outage was that i logged out of my web-server_02 but forgot to allow connection on `port 22/TCP`

## Timeline (all time in GMT + 1)
| Time (GMT+1) | Actions |
| -------------- | -------- |
| 8:00 PM | I tried to SSH back into my webserver_02 after i had installed the firewall and logged out|
| 8:25 PM | I checked if my server was still listening to port 22 with the command `sudo lsof -i -P -n \| grep LISTEN` |
| 8:28 PM | I found out that my web-server was not listening on `port 22/tcp` |
| 8:30 PM | I requested for new web-server  |
| 8:35 PM | I installed all the necessary files i needed to complete my task on the web-server |
| 10:20AM | I successfully redid all the task that was lost|

## Root cause and resolution:
<img src="https://github.com/Cyberod/alx-system_engineering-devops/assets/110993874/bda86b16-10f1-44c9-8fe2-60eaac2a611e" alt="root cause" width="700" height="400">

The root cause was that I forgot to allow connection on `port 22` while installing `firwall(ufw)`

## Preventive measures
- make sure my web-server is allowed to listen to port 22 by using the command `$ sudo ufw allow 22/tcp`
- Always check what port your server is listening to before you log out
