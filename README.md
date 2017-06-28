# NHSbuntu-identity-agent

## Installation on Debian, Ubuntu or derivatives
you will need python3, pip, curl, pcscd and Git if not already installed on your machine

`sudo apt install python3-pip curl pcscd python3-pykcs11`

add the NHSbuntu packagecloud repo and install driver packages for smart card readers on Linux

`curl -s https://packagecloud.io/install/repositories/nhsbuntu/nhs-smartcards/script.deb.sh | sudo bash`

NOTE: if you are on a version of Ubuntu other than 16.04/xenial (or an Ubuntu derivative like mint) then you need to ensure that the distro codename is added correctly in etc/apt/sources.list.d/nhsbuntu-smartcards.list (should point to 'ubuntu' and 'xenial main')

`sudo apt install libclassicclient libssl0.9.8 ifdokccid`

## Usage (testing)

`python -i authenticator.py`

`>>> auth = authenticator()`

`>>> response = auth.authenticate("1234")`

should respond with XML containing a valid ticket for NHS Spine SSO
