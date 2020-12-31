# lsof cheat-sheet

	1) ls -l /proc/pid/fd

This will list the pipes

	ls -l /proc/pid/fd


/etc/security/limits.conf

	ulimit -Sn 65536
	ulimit -Hn 65536

 What if there is a file descriptor leak in the application?
On Linux, we can find if any particular open files are growing over a period of time by taking below data with lsof command against he problematic JVM process ID on a periodic basis.

	lsof -p [PID] -r [interval in seconds, 1800 for 30 minutes] > lsof.out
	 
	lsof -p 345031 -r  1800> lsof.out
r is for repeat mode