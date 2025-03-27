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
- #### Count all filetypes in directory
  `find . -type f | sed -e 's/.*\.//' | sort | uniq -c | sort -n`

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

### AV (These are tweaked for my acceptable risk level, while better than nothing, these exclusions create a lot of blind spots that could be leveraged by an attacker. Specifically on Linux a)
- #### ClamAV Scan (Optimized for scheduled periodic running on extremely large datasets.  Excludes non-suspicious filetypes)
  `clamscan --recursive /scan --max-filesize=2M --exclude='(?i)\.(jpg|jpeg|png|gif|mkv|mp4|ass|ssa|vtt|webp|gz|xml|json|db|db-shm|db-wal|ndf|sqlite|log|log\.\d|yaml|yml|wt|conf|pem|ibd|cnf|config|zip|njfv2|schem|playerskin|txt|mca)$'`

- #### ClamAV Scan (Optimized for periodic running on extremely large datasets.  Includes on Executable filetypes)- 
  `clamscan --recursive /scan --include='(?i)\.(bin|elf|exe|com|so|o|a|sh|pl|php|py|deb|rpm|ko|7z|arj|bz2|cab|cpio|dmg|exe|gz|iso|jar|obd|rar|rpm|tar|tbz2|zip|doc|docx|dox|odt|pdf|pub)$'`

- #### ClamAV Scan (Ransomware Detection. Intention is to minimize data loss from Ransomware before it spreads through entire File Structure. )
  ##### Common RansomWare Extensions
  `clamscan --recursive /scan --include='(?i)\.(locked|encrypted|crypt|cerber|zepto|odin|thor|arena|nm4|vvv|ccc|)$'`
  ##### Detect Rewritten Extensions (Malware commonly adds a random ".ext" to the end of a file when encrypting like "file.mp4.a02lv895")
  `clamscan --recursive /scan --include='(?i)\.(.*)\.' --exclude='(?i)\.(tar)\.'`
  
- #### 
  ``
*.copytemp .
