# inwx-update

A small, even minimalistic, yet simple and posix compliant shell script to update IP addresses on [INWX](https://www.inwx.com) using their [API](https://www.inwx.com/en/help/apidoc). The script only needs `curl` and `find` command. With a working `sendmail` command, the script sends a notification mail on errors.

First, copy `inwx-update.sample` to `/etc/default/inwx-update` and set correct variables (`RECORD` for the resource record to update, `DOMAIN` for the main domain, `USER` for the username and `PASSWORD` for the password). Then place the script under `/usr/local/bin` and run it as a cronjob or as systemd timer.

Enter following line to run the script every five minutes as a cronjob:

`*/5 * * * * /usr/local/bin/inwx-update`

Or copy `inwx-update.service` and `inwx-update.timer` to `/etc/systemd/system/` and activate the timer with:

`systemctl enable --now inwx-update.timer`
