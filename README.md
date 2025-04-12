# raspberry-pi-headless-setup.
This is the detailed step by step process to setup you raspberry pi  
**step 1:( installation of imager tool)**  
1. Go to raspberrypi offical website.  
2. then go to software section.  
3. and download imager tool.  
**step 2:(installation of os)**  
1. insert SD card into your pc.  
2. open imager tool.  
3. select your raspberry pi and OS  
![Screenshot 2025-04-12 111954](https://github.com/user-attachments/assets/e9d448fb-695a-4e39-9faf-990b4329e50b)  
4. ![Screenshot 2025-04-12 112412](https://github.com/user-attachments/assets/dacfc1fb-8f11-4d3b-9351-82d57e74a508)  
5. choose your storage (sd-card).  
6. and then next without any customization (because we do this later due to some issue with us)  
7. after installation remove you sd-card and follow next steps.  
**step 3:(creating wifi config. file to connect your pi to your hotspot)**  
**remember that your can edit anything in sd card with contains os. so, Do this steps in another folder.**  
1. in any folder create a file wpa_supplicant.conf with no extension.  
leftclick on free space in your folder>new>text document>rename it(wpa_supplicant.conf)and also make sure to remove .txt extention.  
2. tick this thing to make sure there is no extenstion in your file.  
![Screenshot 2025-04-12 114810](https://github.com/user-attachments/assets/b2c459dc-f519-48af-a714-4a9d9ae43033)  
3. open wpa_supplicant.conf with vs code/notepad++
4. and type this:
```conf
country=IN
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="YourWiFiName"
    psk="YourPassword"
}
```
5. feed your ssid and password and
6. before saving line ending should be LF not CRLF
**if you are using vs code in lower left corner you will se either LF or CRLF ,IF CRLF make it LF**
**and if you are using notepad++ go to edit>EOL conversion>select LF**
![Screenshot 2025-04-12 121230](https://github.com/user-attachments/assets/66654ecb-fc34-45c0-b424-89e57fde6223)
![Screenshot 2025-04-12 121430](https://github.com/user-attachments/assets/5102a560-8d8b-4cbe-ab31-97f08fb115c7)
**step 4:(creating userconf file for setting username and password of raspberrypi)**
1. same as we created wpa_supplicant.conf create a file named (userconf) with no extention
2. open this file in vs code/notepad++
3. type in this format- username:hash password
4. set username as per you choice
5. and hash password will the encrypted form of your password.
6. after this same this file and also remember this end of line should be LF.
example- raspberry:$6$MQk.VqZJgjdMk0az$kpR7ttBc1QAXd5CqywHFjtqj.RDHJbXFFKBKOCraIlP7rH26P95INS.luhGRWKPtELBvwLWX2NJqSUocGqbiD/  
**step 5:(how to create hash password)**
1. download gitbash software
2. after that open it and give command- openssl passwd  
3. and enter the password you want to set and re-enter(password is not visible so don't worry).
4. and you get hash password like this
5. ![Screenshot 2025-04-12 125112](https://github.com/user-attachments/assets/f7cd37cd-7275-4646-90a7-672a628c9be8)
6. copy it(ctrl +c) and paste it your userconf file.
**step 6:(cut paste only)**
1. only cut not copy
2. insert your sd card and
3. cut and paste your files (wpa_supplicant.conf and userconf)one by one into your OS file
4. HERE![(Upload-from-mobile-1744443231)1000133506](https://github.com/user-attachments/assets/00ac0a75-0d24-4f98-9134-d6df661b1497)
   **step 7:(ENABLE SSH)**
1. after cut paste
2. just like previous file create file ssh with no extension(remove.txt){where we pasted our other files}
3.  and now all set eject your sd card from your laptop and insert into raspberry
4.  **power your pi and wait for 5-10min** it will connected to your hotspot.
**if not try again this process carefully**  
   **DISCLAIMER**  
    -dont shutdown your pi by unpluging it.it may cause corruption of os.  
    -use command sudo shutdown now to shutdown it and unlug it when geen led turn off.  
    -make sure not to disturbe your pi it may also cause problem.  
    **THANK YOU** 











