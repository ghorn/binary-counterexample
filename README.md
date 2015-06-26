This is a small executable which serializes a data type using both cereal and binary.
To run it:

    git clone git@github.com:ghorn/binary-counterexample.git
    cd binary-counterexample
    cabal install --only-dependencies
    cabal configure
    cabal build
    ./dist/build/binary-counterexample/binary-counterexample -o shootout.html -v 2

example report here:

