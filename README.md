# Useful-Unraid-Commands
Useful commands/Scripts that I have found/used when tinkering with my unraid server compiled in one place.  

## Monitoring
### CPU Monitoring

 - #### Monitor CPU MHz
   `cat /proc/cpuinfo | grep "MHz" `

- #### Check Max CPU Hz Frequency
  `cat /sys/devices/system/cpu/cpu*/cpufreq/scaling_max_freq `
  
   
- #### Watch CPU MHz
  `watch "grep 'cpu MHz' /proc/cpuinfo"`
   
- #### Find files with User Permissions
  `find . ! -user nobody`

- #### Find Problem Media Files
  `find . -type f ! -name '*.mp4' ! -name '*.mkv' ! -name '*theme.mp3' ! -name '*.srt' ! -name '*.avi' ! -name '*.sub'`
  
- #### 
  ``
