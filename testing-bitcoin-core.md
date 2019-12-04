# Testing Bitcoin Core
After [building](building-bitcoin-core.md), this is how you verify that all the tests are passing.

## Unit Tests

### Running all the Unit Tests
After building, they can be run with `make check`. This will run all of the tests unless a test was explicity disabled when running the `./configure` script.

### Running Individual Tests
After building, an executable called `test_bitcoin` is created. Running `test_bitcoin` without any arguements will run all of the unit tests. This is how to run individual unit tests:
```shell
./src/test/test_bitcoin --run_test=<test_name>
```

## Functional Tests
To run the standard test suite, you can use 
```shell
./test/functional/test_runner.py`
```
For the extended test suite, use `--extended` and for all the options, use `--help`.
