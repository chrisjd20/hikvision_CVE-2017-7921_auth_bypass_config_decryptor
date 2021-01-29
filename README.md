# hikvision_CVE-2017-7921_auth_bypass_config_decryptor
This python file will decrypt the configurationFile used by hikvision cameras vulnerable to CVE-2017-7921.

https://www.checkpoint.com/defense/advisories/public/2017/cpai-2017-0876.html/

# Description 

Hikvision IP Cameras Authentication Bypass (CVE-2017-7921)

Basically, hikvision cameras that are vulnerable to the CVE listed above, can have several routes exposed by using a simple base64 string supplied as an argument in the url. 

For example:

`/System/configurationFile?auth=YWRtaW46MTEK`

This would allow an unauthenticated user to download the config file for the camera which includes user information. This configuration file uses weak encryption and a static key by default.

The python script supplied, will decrypt this configuration file. 

I also supply a sample generated example configuration file for you to test. 

# How To Use

`./decrypt_configurationFile.py <nameofdownloadedconfig>`


# Dependencies:

`sudo python3 -m pip install pycryptodome`

**Tested on Ubunut 20.04 with python 3.8.5**
