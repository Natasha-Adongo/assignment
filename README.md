## ASSIGNMENT 2 ##
**BASH SCRIPTING EXERCISES**
## Question 1 ##
1. How many processes are currently running on your system? Use ps and wc, the first line of output of ps is not a process!

 ```
 $ ps wc
  2424 tty2     Ssl+   0:00 gdm-x-session
 
   2426 tty2     Sl+   27:40 Xorg
   
   2442 tty2     Sl+    0:00 gnome-session-b
   
  46178 pts/0    Ss+    0:00 bash
  
  75634 pts/1    Ss+    0:00 bash
  
  76734 pts/1    T      0:00 bash
  
  76735 pts/1    T      0:00 wc
  
  76809 pts/1    T      0:00 bash
  
  76810 pts/1    T      0:00 sleep
  
  77803 pts/1    T      0:00 bash
  
  77804 pts/1    T      0:00 wc
  
  77817 pts/1    T      0:00 bash
  
  77818 pts/1    T      0:00 wc
  
  78521 pts/1    T      0:00 nano
  
  80264 pts/2    Ss+    0:00 bash
  
  80970 pts/2    T      0:00 cat
  
  82633 pts/2    T      0:00 nano
  
 182472 pts/3    Ss+    0:00 bash
 
 186316 pts/3    T      0:00 less
 
 186661 pts/3    T      0:00 less
 
 187451 pts/4    Ss     0:00 bash
 
 189339 pts/4    R+     0:00 ps
 ```

## QUESTION 2  
Write a script that upon invocation shows the time and date, lists all logged-in users, and gives the system uptime. 
The script then saves this information to a logfile.  
```
$ date
$ who
$ uptime
```
```
bash date.sh > date.log
```

### QUESTION 3
which command would you use in order to create an empty file in the current directory, lets say empty.txt

```$ touch empty.txt```

```$ ls```
```  EcoliSRR_anno_variants.vcf   lib                           ofile.csv                             setup                   Work
 chromfiles             empty.txt   
 ```
 ## QUESTION 4  
 You are in /home/icipe/  suppose this directory is empty. How do you create in only one command the whole path /home/icipe/Work/mini-project/RNA-Seq/?
 ```
$ mkdir -p work/mini-project/RNA-seq 
 ```
 ```
 $ cd  work/mini-project/RNA-seq
```
 ```
 (base) icipe@ghost:~/work/mini-project/RNA-seq$ 
```

## QUESTION 5
Suppose your current working directory contains a file named seqs.txt. How do you rename this file into sequences.fasta ? Does this have any effect on the content of the file, and if yes, what does it do?

**no change on the data**

```$ mv octane.pdb prot.fasta``` 

## QUESTION 6 
How can you create in a single command a file containing the contents "Hello, world!" and named universal_greeting.txt?  
```$ echo "hello, world!!" > universal_greeting.txt```  
```$ cat universal_greeting.txt```  
``` hello, world!!```

## QUESTION 7 ##
what about creating the same file but with filenae "Universal greetings.txt"

```
$ echo "universal greetings.txt"
universal greetings.txt
```
## QUESTION 8  
How can you use the commandline (on whichever machine you are now, that is connected to the internet) to download directly the 
file you can see on https://github.com/Fnyasimi/my-first-repo/blob/main/directory1/test.fa ? Be careful, you need to get the raw text file itself, 
not the full HTML page presenting it.  
```
$ wget https://github.com/Fnyasimi/my-first-repo/blob/main/directory1/test.fa?raw=true
```  
## QUESTION 9
How can you count the number of lines in this text file(test.fa)? How do you count the number of sequences
```
$ wc -l test.fa\?raw\=true
10281 test.fa?raw=true
```  
## QUESTION 10  
Extract only the identifier lines from this file, and write them into a file called "identifiers.txt".  
```
grep -w ">*" test.fa\?raw\=true > identifiers.txt
```
```>NM_001361694.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 9, mRNA
>NM_001361695.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 10, mRNA
>NM_001164226.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 1, mRNA
>NM_010938.4 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 6, mRNA
>AK082580.1 Mus musculus 0 day neonate cerebellum cDNA, RIKEN full-length enriched library, clone:C230066G05 product:nuclear respiratory factor 1, full insert sequence
>XM_021165121.1 PREDICTED: Mus caroli nuclear respiratory factor 1 (Nrf1), transcript variant X5, mRNA
>XM_021165122.1 PREDICTED: Mus caroli nuclear respiratory factor 1 (Nrf1), transcript variant X6, mRNA
>AK029034.1 Mus musculus 10 days neonate skin cDNA, RIKEN full-length enriched library, clone:4732483G17 product:nuclear respiratory factor 1, full insert sequence
>AK014494.1 Mus musculus 14 days embryo liver cDNA, RIKEN full-length enriched library, clone:4432414E03 product:nuclear respiratory factor 1, full insert sequence
>NM_001361693.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 8, mRNA
>NM_001361692.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 7, mRNA
>XM_011241048.1 PREDICTED: Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant X8, mRNA
>AK031103.1 Mus musculus 13 days embryo forelimb cDNA, RIKEN full-length enriched library, clone:5930405C14 product:nuclear respiratory factor 1, full insert sequence
>XM_021189475.1 PREDICTED: Mus pahari nuclear respiratory factor 1 (Nrf1), transcript variant X3, mRNA
>XM_006236198.3 PREDICTED: Rattus norvegicus nuclear respiratory factor 1 (Nrf1)identifiers.txt

```
 
## QUESTION 11
How can you process the file you got from question 8 to replace all its uppercase "A" letters to lower case "a" letter, 

```
$ grep "A" test.fa\?raw\=true | tr [A] [a]

XM_021165122.1 PREDICTED: Mus caroli nuclear respiratory factor 1 (Nrf1), transcript variant X6, mRNa
CTCGGCGGCGGCGGCGGCGGCaGaGGCGGCaGCGCTCGCCaTTGCCGCTGGTGGCaGGaGGCTGCGaGGaGCCGGCGCGG
TCGCaGTCTCCaCGGCGCaGGCCCaCGGTaGCGCaGCCGCTCTGaGGTCGaaTGaTaTGTGGTTCaTGTaGaCCaCaTTT
TGTTTCCCaCTCaCCCaTTGaTGGaCaCTTGGGTaGCTTCCaTCTTTTGGCTGTTGTGaaTaaTGCTGCTaTGaaCaTGG
GTGTGCaCaTaGCTCTCTGaGaCGCTGCTTTCaGTCCTTCTGGTaGaTCTTCaTGGaGGaGCaCGGaGTGaCCCaaaCTG
aaCaCaTGGCTaCCaTaGaaGCCCaTGCaGTGGCCCaGCaaGTCCaGCaGGTCCaTGTaGCCaCaTaCaCTGaGCaCaGT
aTGCTaaGTGCTGaTGaaGaCTCCCCTTCCTCCCCCGaGGaCaCTTCTTaTGaTGaCTCTGaCaTCCTCaaCTCCaCGGC
aGCTGaTGaGGTaaCTGCCCaTCTGGCTGCTGCaGGTCCTGTGGGaaTGGCCGCTGCTGCTGCTGTGGCaaCaGGGaaGa
aaCGGaaaCGGCCTCaTGTGTTTGaGTCTaaTCCaTCTaTCCGaaaGaGaCaGCaGaCaCGTTTGCTTCGGaaaCTCaGa
GCCaCGTTGGaTGaGTaCaCGaCGCGaGTGGGaCaGCaaGCGaTTGTaCTCTGCaTCTCaCCCTCCaaaCCCaaCCCCGT
CTTCaaGGTGTTTGGCGCaGCaCCTTTGGaGaaTGTGGTGCGaaaGTaCaaGaGCaTGaTCCTGGaaGaCCTGGaGTCaG
CTCTGGCaGaaCaCGCCCCTGCGCCaCaGGaGGTTaaTTCaGaaCTGCCaCCTCTCaCCaTCGaTGGGaTTCCaGTCTCT
GTGGaCaaaaTGaCCCaGGCTCaGCTTCGGGCaTTTaTCCCaGaGaTGCTCaaGTaTTCCaCaGGTCGaGGGaaaCCaGG
CTGGGGGaaaGaaaGCTGCaaGCCTaTCTGGTGGCCaGaaGaCaTCCCaTGGGCTaaTGTCCGCaGTGaTGTCCGCaCaG
aaGaGCaaaaaCaaaGGGTTTCaTGGaCCCaGGCaTTaCGGaCCaTaGTTaaaaaTTGTTaTa
```
## QUESTION 12  
In one command, ask for the display of all identifier lines from the same file test.fa without wrapping the lines, i.e. by having all lines displayed 
on your screen effectively start with the character '>'.  
```  
less -S identifiers.txt  
```  
```  
>XM_015134911.1 PREDICTED: Macaca mulatta nuclear respiratory factor 1 (NRF1), transcript variant X3, mRNA
>XM_011723890.1 PREDICTED: Macaca nemestrina nuclear respiratory factor 1 (NRF1), transcript variant X13, mRNA
>XM_011995878.1 PREDICTED: Mandrillus leucophaeus nuclear respiratory factor 1 (NRF1), transcript variant X2, mRNA
>XM_015134912.1 PREDICTED: Macaca mulatta nuclear respiratory factor 1 (NRF1), transcript variant X4, mRNA
>XM_003803318.3 PREDICTED: Otolemur garnettii nuclear respiratory factor 1 (NRF1), mRNA
>NM_001164227.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 2, mRNA
>AK037697.1 Mus musculus 16 days neonate thymus cDNA, RIKEN full-length enriched library, clone:A130038J21 product:SIMILAR TO NUCLEAR RESPIRATORY FACTOR 1 homolog [Mus musculu>
>XM_016958154.2 PREDICTED: Pan troglodytes nuclear respiratory factor 1 (NRF1), transcript variant X7, mRNA
>XM_021936263.1 PREDICTED: Papio anubis nuclear respiratory factor 1 (NRF1), transcript variant X10, mRNA
>XM_003813488.3 PREDICTED: Pan paniscus nuclear respiratory factor 1 (NRF1), transcript variant X4, mRNA
>XM_003896587.4 PREDICTED: Papio anubis nuclear respiratory factor 1 (NRF1), transcript variant X11, mRNA
>XM_003951129.3 PREDICTED: Pan troglodytes nuclear respiratory factor 1 (NRF1), transcript variant X9, mRNA
>XM_001155756.5 PREDICTED: Pan troglodytes nuclear respiratory factor 1 (NRF1), transcript variant X8, mRNA
>XM_017957164.2 PREDICTED: Papio anubis nuclear respiratory factor 1 (NRF1), transcript variant X12, mRNA
>XM_021673680.1 PREDICTED: Aotus nancymaae nuclear respiratory factor 1 (NRF1), transcript variant X1, mRNA
```


## QUESTION 13 
Can you write a very short script possibly a single commandline to etract from the same file the species name?

```
$ cut -d ' ' -f 2-4 identifiers.txt |cut -d : -f 2 | sed 's/^ *//g'| cut -d '' -f 1

Mus musculus nuclear
Mus musculus nuclear
Mus musculus nuclear
Mus musculus nuclear
Mus musculus 0
Mus caroli
Mus caroli
Mus musculus 10
Mus musculus 14
Mus musculus nuclear
Mus musculus nuclear
Mus musculus
Mus musculus 13
Mus pahari
Rattus norvegicus
Peromyscus maniculatus
Mus musculus nuclear
Mus musculus 6
Mus musculus 6
Mus musculus
Mus pahari
Cricetulus griseus
Mesocricetus auratus
Rattus norvegicus
Nannospalax galili
Nannospalax galili
```  
## QUESTION 14  
Once this is done, how do you count the species names with their order of multiplicity 
(i.e. how many sequences belong to Mus musculus, how many to Homo sapiens, etc)?  

```  
cut -d ' ' -f 2-4 identifiers.txt | cut -d : -f 2 | sed 's/^ *//g'| cut -d ' ' -f 1,2 | uniq -c | sort -n
```  
```  
      1 Rattus norvegicus
      1 Rattus norvegicus
      1 Rhinopithecus roxellana
      2 Cercocebus atys
      2 Cercocebus atys
      2 Chlorocebus sabaeus
      2 Homo sapiens
      2 Mus caroli
      2 Mus musculus
      2 Mus musculus
      2 Nannospalax galili
      2 Pan troglodytes
      2 Pongo abelii
      2 Rhinopithecus roxellana
      2 Rhinopithecus roxellana
      3 Heterocephalus glaber
      4 Mus musculus
      5 Chinchilla lanigera
      5 Mus musculus
      6 Mus musculus
```  


## QUESTION 15
Write a loop in bash producing all the intergers from 1 to 30, one perline

```$ for numbers in 1 30 ; do seq $numbers ; done```
```
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19 
```
