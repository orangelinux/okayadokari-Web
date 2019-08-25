# okayadokari-Web
オカヤドカリ水槽の状態をwebから見るやつです。
動かすときは

```
crontab -e 
```
して下を追記します。
```
# m h  dom mon dow   command
* * * * * for i in `seq 0 10 59`;do (sleep ${i} ; /home/pi/send.sh prm1 prm2) & done; 
*/1 * * * * /home/pi/fan.sh
30 * * * * python3 /home/pi/temp.py
30 * * * * python3 /home/pi/wter.py

```
