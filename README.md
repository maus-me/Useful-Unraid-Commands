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
   
- #### 
  ``
