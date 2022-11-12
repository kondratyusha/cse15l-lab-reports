# Lab Report Week 5: Researching Commands

## `find` command

1) `find -type` will find files of specified type in a directory.

`find -type d` will find directories in a working directory and below.

```
[cs15lfa22ow@ieng6-203]:technical:376$ find -type d
.
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

`find -type f -name '*.txt'` will find all .txt files in a working directory and below.

```
./government/About_LSC/diversity_priorities.txt
./government/About_LSC/reporting_system.txt
./government/Alcohol_Problems/DraftRecom-PDF.txt
./government/Alcohol_Problems/Session2-PDF.txt
./government/Alcohol_Problems/Session3-PDF.txt
./government/Alcohol_Problems/Session4-PDF.txt
./government/Env_Prot_Agen/1-3_meth_901.txt
./government/Env_Prot_Agen/atx1-6.txt
./government/Env_Prot_Agen/bill.txt
./government/Env_Prot_Agen/ctf1-6.txt
./government/Env_Prot_Agen/ctf7-10.txt
./government/Env_Prot_Agen/ctm4-10.txt
./government/Env_Prot_Agen/final.txt
./government/Env_Prot_Agen/jeffordslieberm.txt
./government/Env_Prot_Agen/multi102902.txt
./government/Env_Prot_Agen/nov1.txt
./government/Env_Prot_Agen/ro_clear_skies_book.txt
./government/Env_Prot_Agen/section-by-section_summary.txt
./government/Env_Prot_Agen/tech_adden.txt
./government/Env_Prot_Agen/tech_sectiong.txt
./government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./government/Gen_Account_Office/InternalControl_ai00021p.txt
```

`find -type d -name '[Gg]*'` will find directories starting with G or g.

```
[cs15lfa22ow@ieng6-203]:technical:402$ find -type d -name '[Gg]*'
./government
./government/Gen_Account_Office
```
2) `find -amin n` will show files accessed in last n minutes.

Usefull application is `find / -amin -60`, this command will show all files which were accessed in last 60 min.

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

`find -type d -amin -60` will find all directories used in past hour.

```
[cs15lfa22ow@ieng6-203]:technical:417$ find -type d -amin -60
.
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

`find -type f -amin -10` will find all files used in past ten minutes.

```
[cs15lfa22ow@ieng6-203]:biomed:431$ find -type f -amin -10
./1471-2318-3-2.txt
```

3) Another useful option for the `find` command is `find -size n`. This option will find all files in a directory that match number n.

`find -size +200k` will find all files in a directory that are larger than 200 kilobytes.

```
[cs15lfa22ow@ieng6-203]:technical:437$ find -size +200k
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-3.txt
./government/About_LSC/commission_report.txt
./government/Env_Prot_Agen/bill.txt
./government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./government/Gen_Account_Office/d01591sp.txt
```

`find -size -1500c` will find all files in a directory that are smaller than 1500 bytes.

```
[cs15lfa22ow@ieng6-203]:technical:445$ find -size -1500c
./plos/pmed.0020048.txt
./plos/pmed.0020120.txt
./plos/pmed.0020157.txt
./plos/pmed.0020191.txt
./plos/pmed.0020192.txt
./plos/pmed.0020226.txt
```

`find -size 4` will find all files in a directory that are 4  512-byte blocks.

```
[cs15lfa22ow@ieng6-203]:technical:456$ find -size 4
./government/Media/Campaign_Pays.txt
./government/Media/Court_Keeps_Judge_From.txt
./government/Media/Fire_Victims_Sue.txt
./government/Media/Helping_Hands.txt
./government/Media/It_Pays_to_Know.txt
./government/Media/Justice_requests.txt
./government/Media/Lawyer_Web_Survey.txt
./government/Media/Self-Help_Website.txt
./government/Media/Wilmington_lawyer.txt
./plos/pmed.0020028.txt
./plos/pmed.0020082.txt
```

[Back](index.html)