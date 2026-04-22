
 touch 0 1 2 4 5 6 7 8 9 A
 
 rm -f A

 mkdir A

 ln -s 0 3
 
 chmod 701 0
 chmod 602 1
 chmod 642 2
 chmod 510 4
 chmod 460 5
 chmod 460 6
 chmod 510 7
 chmod 642 8
 chmod 602 9
 chmod 701 A
 touch -t 198601050000 0
 touch -t 198611130001 1
 touch -t 198803050010 2
 touch -t 199002160011 3 -> 0
 touch -t 199010071000 4
 touch -t 199011070101 5
 touch -t 199102080110 6
 touch -t 199103080111 7
 touch -t 199405201000 8
 touch -t 199406101001 9
 touch -t 199504101010 A

 Tz=utc ls -l --time-style='+%F %R' | sed 1d | awk '{print $1, $6, $7, $8, $9, $10}'

 # outputs:
-rwx-----x 1990-02-16 00:11 0  
-rw-----w- 1986-11-13 00:01 1  
-rw-r---w- 1988-03-05 00:10 2  
lrwxrwxrwx 2026-04-22 17:04 3 -> 0
-r-x--x--- 1990-10-07 10:00 4  
-r--rw---- 1990-11-07 01:01 5  
-r--rw---- 1991-02-08 01:10 6  
-r-x--x--- 1991-03-08 01:11 7  
-rw-r---w- 1994-05-20 10:00 8  
-rw-----w- 1994-06-10 10:01 9  
drwx-----x 1995-04-10 10:10 A  

recoding@leef-HP-All-in-One-24-f0xx:~/Practice-mode/piscine-go$ tar -cf done.tar *
recoding@leef-HP-All-in-One-24-f0xx:~/Practice-mode/piscine-go$ ls
0  1  2  3  4  5  6  7  8  9  A  done.tar