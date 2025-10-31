<img align="right" src="https://visitor-badge.laobi.icu/badge?page_id=noetovar5.Robocopy-Tutorial"/>
# Robocopy-Tutorial
Robocopy Tutorial
Robocopy Tutorial
Robocopy (Robust File Copy) is a command-line utility in Windows designed for fast and reliable file copying. It is especially useful for copying large volumes of data, maintaining file attributes, and resuming interrupted transfers.
Basic Syntax
robocopy <Source> <Destination> [<File>[ ...]] [<Options>]
Threading with /MT
Robocopy supports multithreading with the /MT switch. By default, Robocopy uses one thread. You can specify up to 128 threads to speed up the copying process. Example:
robocopy C:\\Source C:\\Destination /MT:16
Useful Switches
/MIR: Mirrors a directory tree (equivalent to /E plus /PURGE).
/R:n: Specifies the number of retries on failed copies (default is 1 million).
/W:n: Specifies the wait time between retries (default is 30 seconds).
/LOG:file: Writes the status output to the log file instead of the console.
/COPYALL: Copies all file info (equivalent to /COPY:DATSOU).
/NP: No progress shown (useful for logging).
/TEE: Output to console window and log file simultaneously.
/SEC: Copies files with security (NTFS ACLs).
Example Usage
robocopy C:\\Data D:\\Backup /MIR /MT:8 /LOG:C:\\Logs\\backup.log /R:5 /W:10
Best Practices
- Use /LOG to keep a record of operations.
- Limit /MT to a reasonable number to avoid disk I/O bottlenecks.
- Use /R and /W to control retry behavior on network or disk errors.
- Test with a small dataset before running on production data.
