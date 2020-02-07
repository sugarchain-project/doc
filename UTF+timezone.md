This change is optional

### UTF-8 en_US.UTF-8
```
export LANGUAGE="en_US.UTF-8" && \
echo 'LANGUAGE="en_US.UTF-8"' >> /etc/default/locale && \
echo 'LC_ALL="en_US.UTF-8"' >> /etc/default/locale
```

### Set Timezone Asia/Seoul or another location
https://vitux.com/how-to-change-the-timezone-on-your-ubuntu-system/
```
timedatectl set-timezone Asia/Seoul
```
