# hist

Generate histograms from the command line.

### Dependencies
Python 2.7 & numpy required, gnuplot for easy plotting.

### Installation
Just drop the hist script into a directory in your path.

### Examples

```
$ hist random.dat
6.389172e-02 1.400000e+01
1.614881e-01 8.000000e+00
2.590844e-01 9.000000e+00
3.566808e-01 1.300000e+01
4.542771e-01 8.000000e+00
5.518735e-01 1.100000e+01
6.494698e-01 1.400000e+01
7.470662e-01 5.000000e+00
8.446625e-01 7.000000e+00
9.422589e-01 1.100000e+01
```
#### Change the number of bins:
```
$ hist random.dat -n 3
1.777541e-01 3.600000e+01
5.030753e-01 3.600000e+01
8.283965e-01 2.800000e+01
```

#### Change the bin width:
```
$ hist random.dat -w0.5
2.650935e-01 5.300000e+01
7.650935e-01 4.700000e+01
```

#### Set the y axis to the log scale:
```
$ hist random.dat -ly
6.389172e-02 1.400000e+01
1.614881e-01 8.000000e+00
2.590844e-01 9.000000e+00
3.566808e-01 1.300000e+01
4.542771e-01 8.000000e+00
5.518735e-01 1.100000e+01
6.494698e-01 1.400000e+01
7.470662e-01 5.000000e+00
8.446625e-01 7.000000e+00
9.422589e-01 1.100000e+01
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

