ENM CPU Load Predictive Model
=============================


# 1.  Challenge Description


## 1.1 Dataset Description
This dataset in `data/` folder is based on real data extracted from DDP on
customer sites. The dataset contains data from 11 network operators and the
file names follow a name convention aiming at grouping the files by
network operator:

### JSON files:
Filename format: customer-<operator-id>-<service-group>.json
Content: list of supported nodes/features

### CSV files:
Format: <type-of-content>-<operator-id>-<service-group>-<start-of-date-range>-<end-of-date-range>.csv

type-of-content:

- features: counts of nodes per node-type per day; each column is a different node type, each row is a different day. The first row is the header.
- labels: CPU metrics collected daily every minute from all the servers in a service-group; each column is a CPU load reading in % time, each row is a different day. No header.
- dates: each row is a day for each row in features and labels files. No header.

## 1.2 Feature Description

The dataset is heavily anonymized. The real network-operator-id is replaced by a counter. The CSV containing the features is a CSV files having as column the type of nodes supported by ENM, as row the day the node volumes were measured, as cell-values the number of nodes divided by 10000. In `graph` folder there's an HTML file containing a Plotly graph per each operator having as Xs the content of the corresponding `dates` CSV file, a plot per every node type with node-counts as Ys, a plot for the CPU load, and a plot for the averaged CPU load over time.

## 1.3 Research Areas

This dataset can be used for both data exploration as well as modelling tasks.
In terms of modelling tasks, it can be used for both time-series modelling as
well as non-temporal tasks.

## 1.4 Challenge

The expected outcome of the produced model(s) is:
- to be able to tell how much CPU load a single node of every type is generating on a service-group 
- to be able to predict how much CPU load a combination of nodes outside the range of the training data will generate on a service-group
 
