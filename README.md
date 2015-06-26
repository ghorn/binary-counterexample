This is a small executable which uses criterion to profile serialization of
a data type using both cereal and binary. Cereal is about 4x faster on this example.

To run it:

    git clone git@github.com:ghorn/binary-counterexample.git
    cd binary-counterexample
    cabal install --only-dependencies
    cabal configure
    cabal build
    ./dist/build/binary-counterexample/binary-counterexample -o shootout.html -v 2

example report here: http://ghorn.github.io/binary-counterexample

example criterion output:
```
benchmarking cereal-encode-nf
analysing with 1000 resamples
measurement overhead 552.5 ns
bootstrapping with 6 of 7 samples (85%)
time                 132.6 ms   (123.1 ms .. 141.2 ms)
                     0.996 R²   (0.982 R² .. 1.000 R²)
mean                 145.9 ms   (140.3 ms .. 162.3 ms)
std dev              13.34 ms   (500.4 μs .. 18.25 ms)
found 1 outliers among 6 samples (16.7%)
  1 (16.7%) high severe
variance introduced by outliers: 26% (moderately inflated)

benchmarking cereal-encodeLazy-nf
analysing with 1000 resamples
bootstrapping with 7 of 8 samples (87%)
time                 127.4 ms   (127.1 ms .. 127.6 ms)
                     1.000 R²   (1.000 R² .. 1.000 R²)
mean                 127.5 ms   (127.4 ms .. 127.8 ms)
std dev              264.0 μs   (85.24 μs .. 398.7 μs)
found 1 outliers among 7 samples (14.3%)
  1 (14.3%) high severe
variance introduced by outliers: 11% (moderately inflated)

benchmarking binary-encode-nf
measurement took 7.048 s
analysing with 1000 resamples
bootstrapping with 3 of 4 samples (75%)
time                 468.0 ms   (450.2 ms .. 485.4 ms)
                     1.000 R²   (0.999 R² .. 1.000 R²)
mean                 471.3 ms   (467.8 ms .. 476.7 ms)
std dev              4.706 ms   (0.0 s .. 5.095 ms)
variance introduced by outliers: 19% (moderately inflated)
```
