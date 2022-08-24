These are the first commands after getting SSH access

echo 'export SKIP_FW_QUERY=1' >> /data/openpilot/launch_env.sh
echo 'export FINGERPRINT="VOLKSWAGEN PQ35/PQ46/NMS GEN"' >> /data/openpilot/launch_env.sh 
and
echo -n "gateway" > /data/params/d/ForceNetworkLocation

OpenSSH or Similar Client
(⚠ Instructions are not updated for 0.8.3+)

Download the private key from the openpilot repo.. Save the key file as a text file and name it something like key.pem.
Open a terminal
Run C$ chmod 600 key.pem` (otherwise, the system will think the text file is not safe).
Get the IP address of your comma two from Settings > WiFi > Open WiFi Settings > More Options > Options (top right icon) > Advanced (please make sure your comma two and your computer connect to the same WiFi).
Ping the device address from your computer to make sure it is reachable.
Under a Unix/Linux, macOS terminal or Windows 10 with OpenSSH, use the command:
$ssh comma@<IP address of comma two> -p 8022 -i key.pem
Example:

$ ssh comma@192.168.1.100 -p 8022 -i key.pem