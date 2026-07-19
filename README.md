# Gaia-CodeGolf

Here you have my contribution to the contest [Employee Programming Challenge #1] (https://openexchange.intersystems.com/contest/47).

The script has only one line of ObjectScript code.  
It's not very quick but it has only 318 characters, good for the Code Golf nomination *<8-)

## Prerequisites

Make sure you have [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and [Docker desktop](https://www.docker.com/products/docker-desktop) installed.

## Build

Create a directory and run the following command from inside it:

```bash
git clone https://github.com/McFly589/gaia-codegolf.git .
```

Start up the Docker container:

```bash
docker-compose up --build -d
```

## Run the solution

Build the project in Docker container:

```
docker-compose exec iris iris session iris
```

When you get the prompt USER>  
call the routine typing:
```
do ^RunScript
```

The terminal will show:
```
USER>do ^RunScript
/home/irisowner/dev/data/temp/EpochPhotometry_000000-003111.csv
/home/irisowner/dev/data/temp/EpochPhotometry_003112-005263.csv
/home/irisowner/dev/data/temp/EpochPhotometry_005264-006601.csv
/home/irisowner/dev/data/temp/EpochPhotometry_006602-007952.csv
/home/irisowner/dev/data/temp/EpochPhotometry_007953-010234.csv
/home/irisowner/dev/data/temp/EpochPhotometry_010235-012597.csv
/home/irisowner/dev/data/temp/EpochPhotometry_012598-014045.csv
/home/irisowner/dev/data/temp/EpochPhotometry_014046-015369.csv
/home/irisowner/dev/data/temp/EpochPhotometry_015370-016240.csv
/home/irisowner/dev/data/temp/EpochPhotometry_016241-017018.csv
/home/irisowner/dev/data/temp/EpochPhotometry_017019-017658.csv
/home/irisowner/dev/data/temp/EpochPhotometry_017659-018028.csv
/home/irisowner/dev/data/temp/EpochPhotometry_018029-018472.csv
/home/irisowner/dev/data/temp/EpochPhotometry_018473-019161.csv
/home/irisowner/dev/data/temp/EpochPhotometry_019162-019657.csv
/home/irisowner/dev/data/temp/EpochPhotometry_019658-020091.csv
/home/irisowner/dev/data/temp/EpochPhotometry_020092-020493.csv
/home/irisowner/dev/data/temp/EpochPhotometry_020494-020747.csv
/home/irisowner/dev/data/temp/EpochPhotometry_020748-020984.csv
/home/irisowner/dev/data/temp/EpochPhotometry_020985-021233.csv
Elapsed time: 226.615018 seconds

USER>
```
## Code length
Code has only 318 charecters (line 20):
```
USER>d ^%G

Device: 
Right margin: 80 => 
Screen size for paging (0=nopaging)? 24 => 
For help on global specifications DO HELP^%G
Global ^rMAC("RunScript"
^rMAC("RunScript",0)="67770,57222.844851588"
^rMAC("RunScript",0,0)=26
                    1)=$c(9)_"#; We will run this routine to do the benchmark"
                    2)="Run()"
                    3)=$c(9)_"#; extract files if necessary from .data/in to .data/temp"
                    4)=$c(9)_"set wfile=""/home/irisowner/dev/data/in/*.gz"""
                    5)=$c(9)_"for  {"
                    6)=$c(9,9)_"set file=$zsearch(wfile),wfile=""""  quit:file="""""
                    7)=$c(9,9)_"set out=""/home/irisowner/dev/data/temp/""_$e($p(file,""/"",$l(file,""/"")),1,*-3)"
                    8)=$c(9,9)_"write out,!"
                    9)=$c(9,9)_"do $zf(-100,""/STDOUT=""""""_out_""""""/STDERR=""""""_out_"""""""",""gzip"",""-dc"",file)"
                   10)=$c(9)_"}"
                   11)=""
                   12)=$c(9)_"#; Start time"
                   13)=$c(9)_"Set startTime = $ZHOROLOG"
                   14)=""
                   15)=$c(9)_"#; Insert the call to your method/rountine that"
                   16)=$c(9)_"#; - reads the csv files from ./data/in or .data/temp"
                   17)=$c(9)_"#; - processes data"                              
                   18)=$c(9)_"#; - creates output file in .data/out"
                   19)=""
                   20)=$c(9)_"s w=""/t/*"",o=""/o/r"",c="","",S=""]"""",""""["",X=""(n,A,p)s (a,p)=0,i=9e8,l=$p(L,S,n) f x=1:1:$l(l,c){s v=$p(l,c,x) i $num(v) s:v>a a=v s:v<i i=v} s:a p=a-i/i*100,A=i_c_a"" o o:""W"" u o f{s =$zse(w),w="""" q:f=""""  o f f{u f r L#6e4 q:$zeof  i +L{x (X,9,.B,.Q),(X,14,.R,.P) s:Q>P P=Q i P>100 u o w $p(L,c,2)_c_B_c_R_c_P,!}} c f} c o"
                   21)=$c(9)
                   22)=$c(9)_"#; End time"
                   23)=$c(9)_"Set endTime = $ZHOROLOG"
                   24)=$c(9)_"#; Elapsed time in seconds"
                   25)=$c(9)_"Set elapsed = endTime - startTime"
                   26)=$c(9)_"Write ""Elapsed time: "", elapsed, "" seconds"", !"
               "LANG")=0
               "SIZE")=1067

Global ^

USER>w $l($zstrip(^rMAC("RunScript",0,20),"<>w"))
318
```

## Result
Results are saved into /home/irisowner/dev/data/out/r  
File has 57,099 entries
```
$ 
$ pwd
/home/irisowner/dev/data/out
$ ls -l
total 6316
-rwxr-xr-x 1 irisowner irisowner 6464588 Jul 16 21:45 r
$ wc -l r
57099 r
$
```

