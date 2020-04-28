# Dataset generated from the CSIC 2010 dataset.
This folder contains different subsets generated from the CSIC 2010 dataset.

## anomalousTrafficTest.txt, normalTrafficTest.txt and normalTrafficTraining.txt
This files contains the original dataset, the format could be found in the [CSIC web page](http://www.isi.csic.es/dataset/ "HTTP DATASET CSIC 2010").

## dataset_cisc_train_test.tar.gz
This dataset contains a formated version of the CSIC 2010 dataset with the following format:
* **Start - Id: xxx**, where xxx is the ModSecurity unique id of the request
* **class:** with values _Valid_ or _Attack_
* **full request, including headers and body**
* **End - Id: xxx**,where xxx is the ModSecurity unique id of the request

The normal train file is compose of 36000 valid requests.
The normal test file is compose of 36000 valid requests.
The test file is compose of 25065 attack requests.
