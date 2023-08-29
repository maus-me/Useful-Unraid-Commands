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

### Files

- #### Find files with Permissions Issues
  `find . ! -user nobody`
  `find . ! -group users`
  `find . -type f ! -perm -755 ! -perm -777 ! -perm -666`

- #### Find Problematic Media Files
  `find . -type f ! -name '*.mp4' ! -name '*.mkv' ! -name '*theme.mp3' ! -name '*.srt' ! -name '*.sub' ! -name '*.MKV' ! -name '*.avi' ! -name '*.ssa' ! -name '*.ass'`
  
  `find . -type f -name '*.txt'`
  
  Note: I specifically avoid avi, m4v, mpg, ts, and others to ensure best playback compatibility (avoiding MPEG, MJPEG, WMV3, VC1, MP2, PCM).
  
- #### Remove Problematic Media Files
  `find . -type f -name '*.txt' -delete`

  
- #### 
  ``
*.copytemp .
