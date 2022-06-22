#!/bin/bash

IsAlive=$(fping 8.8.8.8)
if [[ "$IsAlive" == *"unreachable"* ]]; then
cp /home/Sendmail.txt /home/Sendmailtemplate.txt
fping 8.8.8.8 |grep unreachable | sed "s/$/ - $(date)/" >> /home/PingLog.txt
fping 8.8.8.8 |grep unreachable | sed "s/$/ - $(date)/" >> /home/Sendmailtemplate.txt
sudo cat /home/Sendmailtemplate.txt | ssmtp ToUser@email.com
rm /home/Sendmailtemplate.txt
fi
