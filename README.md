# IoT Gateway source code

Direction: "/home/pi/Desktop/iot" <br>
<br>

## Create Auto Start Script

1. Create service:
```
sudo systemctl edit --force --full iot_gateway.service
```

2. Add content:
```
[Unit]
Description=IoT Gateway Service
After=network-online.target network.target multi-user.target

[Service]
Type=simple
WorkingDirectory=~
ExecStart=/usr/bin/python3 /home/pi/iot/iotgw.py
User=pi

[Install]
WantedBy=multi-user.target
```

3. Run script
```
sudo systemctl enable iot_gateway.service
sudo systemctl start iot_gateway.service
```
