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

- #### Find files with User Permissions
  `find . ! -user nobody`

- #### Find Problematic Media Files
  `find . -type f ! -name '*.mp4' ! -name '*.mkv' ! -name '*theme.mp3' ! -name '*.srt' ! -name '*.avi' ! -name '*.sub'`
  
  `find . -type f -name '*.txt'`
  
  Note: I specifically avoid avi, m4v, mpg, ts, and others to ensure best playback compatibility.
  
- #### 
  ``
*.copytemp .
