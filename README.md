# hist

Generate histograms from the command line.

### Dependencies
Python 2.7 & numpy required, gnuplot for easy plotting.

### Installation
Just drop the hist script into a directory in your path.

### Examples

```
$ hist random.dat
6.389172e-02 14
1.614881e-01 8
2.590844e-01 9
3.566808e-01 13
4.542771e-01 8
5.518735e-01 11
6.494698e-01 14
7.470662e-01 5
8.446625e-01 7
9.422589e-01 11
```

#### Change the number of bins:
```
$ hist random.dat -n 3
1.777541e-01 36
5.030753e-01 36
8.283965e-01 28
```

#### Change the bin width:
```
$ hist random.dat -w0.5
2.650935e-01 53
7.650935e-01 47
```

#### Set the y axis to the log scale:
```
$ hist random.dat -ly
6.389172e-02 1
1.614881e-01 0
2.590844e-01 0
3.566808e-01 1
4.542771e-01 0
5.518735e-01 1
6.494698e-01 1
7.470662e-01 0
8.446625e-01 0
9.422589e-01 1
```

#### Calculate the uncertainty:
```
$ hist random.dat -u
6.389172e-02 1.400000e+01 3.741657e+00
1.614881e-01 8.000000e+00 2.828427e+00
2.590844e-01 9.000000e+00 3.000000e+00
3.566808e-01 1.300000e+01 3.605551e+00
4.542771e-01 8.000000e+00 2.828427e+00
5.518735e-01 1.100000e+01 3.316625e+00
6.494698e-01 1.400000e+01 3.741657e+00
7.470662e-01 5.000000e+00 2.236068e+00
8.446625e-01 7.000000e+00 2.645751e+00
9.422589e-01 1.100000e+01 3.316625e+00
```

#### Integration with gnuplot (with error bars):
```
$ hist random.dat -u -g | gnuplot -p
```
![screenshot](https://raw.github.com/SamChill/hist/gh-pages/screenshot.png)


#### Integration with gnuplot (with error bars, lines, and log scale y-axis):
```
$ hist random.dat -u -l -ly -g | gnuplot -p
```
![screenshot](https://raw.github.com/SamChill/hist/gh-pages/screenshot2.png)




### Usage
```
usage: hist [-h] [-n BINS] [-w BIN_WIDTH] [-g] [-ly] [-l] [-u]
            [FILE [FILE ...]]

positional arguments:
  FILE

optional arguments:
  -h, --help            show this help message and exit
  -n BINS, --number-of-bins BINS
                        number of bins
  -w BIN_WIDTH, --bin-width BIN_WIDTH
                        bin width
  -g, --gnuplot         gnuplot output
  -ly, --logscale-y     set logscale for y
  -l, --lines           use lines
  -u, --uncertainty     calculate uncertainty
```

