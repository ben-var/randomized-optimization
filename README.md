
# Assignment 2 - Randomized Optimization

The code for this assignment chooses three toy problems, but there are other options available in _ABAGAIL_. Most of this code was adapted from https://github.com/cmaron/CS-7641-assignments/tree/master/assignment2, which is allowed for this assignment. Thank you kindly Chad for sharing your implementation.

## General

Please ensure that ant, Jython, Java, and Python 3 are each correctly installed on your computer before trying to run any of this code. Additionally, please ensure that your PATH variables are correctly set up for jython, java, and ant, as this can cause issues with running the code.

## Data

The data loading code expects datasets to be stored in "./data". The code in this repository is adapted for the Bank Marketing
dataset from the UCI Machine Learning repository (bank.csv).

Because _ABAGAIL_ does not implement cross validation some work must be done on the dataset before the other code can
be run. The data can be generated via 

```
python run_experiment.py --dump_data
```
 
Be sure to run this before running any of the experiments. This will split data into train, test, and validation sets.

## Output

Output CSVs and images are written to `./output` and `./output/images` respectively. Sub-folders will be created for
each toy problem (`CONTPEAKS`, `FLIPFLOP`, `TSP`) and the neural network from the _Supervised Learning Project_ (`NN_OUTPUT`, `NN`).

If these folders do not exist the experiments module will attempt to create them.

## Running Experiments

Each experiment can be run as a separate script. Running the actual optimization algorithms to generate data requires
the use of Jython. Jython 2.7.0 was used to generate the results for this analysis.

For the three toy problems, run:
 - continuouspeaks.py
 - flipflop.py
 - tsp.py

For the neural network problem, run:
 - NN-Backprop.py (for benchmarking purposes)
 - NN-GA.py
 - NN-RHC.py
 - NN-SA.py

## Graphing

The `plotting.py` script takes care of all the plotting. Since the files output from the scripts above follow a common
naming scheme it will determine the problem, algorithm, and parameters as needed and write the output to sub-folders in
`./output/images`. This _must_ be run via python, specifically an install of python that has the requirements from
`requirements.txt` installed. Either modify plotting.py to exclude graphs you will not be plotting, or please run each
experiment as shown in "Running Experiments" before running the plotting code.

In addition to the images, a csv file of the best parameters per problem/algorithm pair is written to
`./output/best_results.csv`.
