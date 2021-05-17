# FreeDMR-autoinstall

<em><b>!Modificación de script para instalación automática de FreeDMR y HBMonv2</b></em>

Auto Installation script for HBlink3 and HBMonitor

  I wrote this script that fully automates the installation of this unique software for all my friends 
who would like to have their own HBlink server with Dashboard, but are not very familiar with Linux.

  In addition, I think it will also save a lot of time for those who are experts.
Everyone can use it and change it as they wish according to their own skills and preferences.

The installation uses the original software without modification.

The only thing I have added is a configured PARROT so that everyone who installs it 
can try its functionality immediately "out-of-the-box"

To use the script by clean install just follow the next commands in terminal:

cd

sudo apt-get install git

sudo git clone https://github.com/darlolanza/HBL-autoinstall.git

cd HBL-autoinstall

sudo chmod +x autoinstall.sh

sudo ./autoinstall.sh

If you want to reinstall the system use:

cd

sudo ./autoinstall.sh

73 de LZ1GSP

# IMPORTANTE LUEGO DE LA INSTALACIÓN

TIPEAR

```bash
nano /lib/systemd/system/proxy.service
```

<em><b>Rellenar con esto y grabar.</b></em>

```bash
[Unit]

Description= Proxy Service 



After=syslog.target network.target



[Service]
User=root

WorkingDirectory=/opt/FreeDMR

ExecStart=/usr/bin/python3 hotspot_proxy_v2.py






[Install]
WantedBy=multi-user.target

```
y Volver a ejecutar

```bash
systemctl enable proxy.service
systemctl start proxy.service
systemctl status proxy.service
```





