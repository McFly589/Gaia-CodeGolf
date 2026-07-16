# Gaia-CodeGolf

Here you have my contribution to the contest [Employee Programming Challenge #1] (https://openexchange.intersystems.com/contest/47).

The script has only one line of ObjectScript code.  
It's not very quick but it has only 331 characters, good for the Code Golf nomination *<8-)

## Prerequisites

Make sure you have [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and [Docker desktop](https://www.docker.com/products/docker-desktop) installed.

## Build

Create a directory and run the following command from inside it:

```bash
git clone https://github.com/McFly589/Gaia-CodeGolf.git .
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

## Result
Results are saved into /home/irisowner/dev/data/out/r.csv  
File has 57,099 entries
```
$ 
$ pwd
/home/irisowner/dev/data/out
$ ls -l
total 6316
-rwxr-xr-x 1 irisowner irisowner 6464588 Jul 16 21:45 r.csv
$ wc -l r.csv
57099 r.csv
$
```

