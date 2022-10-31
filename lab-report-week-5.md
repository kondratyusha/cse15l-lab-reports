# Lab Report Week 5: Researching Commands

## `less` command

1) For example, `less -p` can be used to find an option for a command in man:

```
-ppattern or --pattern=pattern
    The -p option on the command line is equivalent to specifying +/pattern; that is, it tells less to start at the first occurrence of pattern in the file.
```

<img src="Lab_5_1.png" alt="drawing" width="800"/>

2) Another useful example is `less -I` which will ingnore the case of the searched pattern.

```
-I or --IGNORE-CASE
    Like -i, but searches ignore case even if the pattern contains uppercase letters.
```

```
less -I -pCONSUME journal.pbio.0020302.txt
```

<img src="Lab_5_2.png" alt="drawing" width="800"/>

3) One more useful exapmple is `less -E`. It will exit the file at its end and jump to a next file. With this option we can search for a pattern in several files at once.

```
-E or --QUIT-AT-EOF
    Causes less to automatically exit the first time it reaches end-of-file.
```

```
less -I -N -pCONSUME -E ./*.txt
```

Option `-N` will display the line numbers.

## `find` command

1) `find -empty` will find empty files and folders in a directory.

The directory `/technical` contains no empty files.

```
[cs15lfa22ow@ieng6-201]:technical:253$ find ./ -empty
[cs15lfa22ow@ieng6-201]:technical:254$ 
```

2) Usefull usage is `find / -amin -60`, this command will show all files which were accessed in last 60 min.

```
[cs15lfa22ow@ieng6-201]:technical:245$ find ./ -amin -60
./
./911report
./biomed
./government
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./government/Post_Rate_Comm
./plos
```

3) Another useful option for the `find` command is `find -size +200k`. This option will find all files in a directory that are larger than 200 kilobytes.
Also, `find -size -200M` will find all files in a directory that are less than 200 megabytes.

```
[cs15lfa22ow@ieng6-201]:technical:261$ find ./ -size +200k
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-3.txt
./government/About_LSC/commission_report.txt
./government/Env_Prot_Agen/bill.txt
./government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./government/Gen_Account_Office/d01591sp.txt
```

## `grep` command

1) `grep -c`
```
-c, --count
    Suppress normal output; instead print a count of matching lines for each input  file. With  the  -v, --invert-match option (see below), count non-matching lines.
```

Usage example is `grep -c "cell" ./*/* | less`, this command will conviniently show files and number of lines that match in these files.

```
./911report/chapter-1.txt:2
./911report/chapter-10.txt:0
./911report/chapter-11.txt:2
./911report/chapter-12.txt:0
./911report/chapter-13.1.txt:0
./911report/chapter-13.2.txt:0
./911report/chapter-13.3.txt:4
./911report/chapter-13.4.txt:13
./911report/chapter-13.5.txt:7
./911report/chapter-2.txt:13
./911report/chapter-3.txt:9
./911report/chapter-5.txt:7
./911report/chapter-6.txt:13
./911report/chapter-7.txt:1
./911report/chapter-8.txt:11
./911report/chapter-9.txt:0
./911report/preface.txt:0
./biomed/1468-6708-3-1.txt:4
./biomed/1468-6708-3-10.txt:0
./biomed/1468-6708-3-3.txt:1
./biomed/1468-6708-3-4.txt:0
./biomed/1468-6708-3-7.txt:3
./biomed/1471-2091-2-10.txt:58
./biomed/1471-2091-2-11.txt:153
./biomed/1471-2091-2-12.txt:3
./biomed/1471-2091-2-13.txt:3
./biomed/1471-2091-2-16.txt:1
```

2) `grep -l` 

```
-l, --files-with-matches
    Suppress  normal output; instead print the name of each input file from which output would normally have been printed. The scanning will stop on the first match.
```

This command `grep -l "cse" ./*/*` will show filenames that match regex pattern.

```
[cs15lfa22ow@ieng6-201]:technical:272$ grep -l "cse" ./*/*
./biomed/1471-2164-4-6.txt
./biomed/1471-2202-2-1.txt
./biomed/1471-2350-2-11.txt
```

3) `grep -o`

```
-o, --only-matching
    Print only the matched (non-empty) parts of a matching line, with each such part on a separate output line.
```

Usage example is `grep -o "cse" ./*/*`, this command will show all matching lines in all files in `/technical` directory.

```
[cs15lfa22ow@ieng6-201]:technical:275$ grep -o "cse" ./*/*
./biomed/1471-2164-4-6.txt:cse
./biomed/1471-2202-2-1.txt:cse
./biomed/1471-2350-2-11.txt:cse
```

[Back](index.html)