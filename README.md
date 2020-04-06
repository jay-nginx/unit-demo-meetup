# unit-demo-meetup
Demo files for the NGINX Unit Demo from the Meetup

Check Status UNIT:
sudo systemctl status unit

Check what APPs are being served by UNIT:
sudo curl --unix-socket /var/run/control.unit.sock localhost/config
  Location of <control.unit.sock> will be dependent on your install. 

Clean any running applications:
sudo curl --unix-socket /var/run/control.unit.sock -X PUT --data-binary @/opt/unit-files/clean.json localhost/config

Apply the Config file:
sudo curl --unix-socket /var/run/control.unit.sock -X PUT --data-binary @/opt/unit-files/combined.config localhost/config
  Please inspect the combined.config file to ensure the location of your files to serve is correct. 
