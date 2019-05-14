# QOCE
These codes are for our paper "Quadratic Optimization based Clique Expansion for Overlapping Community Detection"

## Requirements
Before compiling codes, the following software should be installed in your system.
- Matlab
- gcc (for Linux and Mac) or Microsoft Visual Studio (for Windows)

## Datasets Information
- LFR benchmark graphs (available at http://sites.google.com/site/santofortunato/inthepress2/)
- Amazon dataset (available at http://snap.stanford.edu/data/)
- Citeseer and Cora refer to (1), Senate refers to (2), and HS as well as SC refer to (3)  

(1) P. Sen, G. Namata, M. Bilgic, L. Getoor, B. Galligher, T. Eliassi-Rad, Collective classification in network data, AI Magazine 29 (3) (2008) 93-106.

(2) D. Gleich, K. Kloster, Seeded pagerank solution paths, European Journal of Applied Mathematics 27 (6) (2016) 812–845.

(3) D. Park, R. Singh, M. Baym, C.-S. Liao, B. Berger, Isobase: a database of functionally related proteins across ppi networks, Nucleic acids research 39 (2010) D295–D300.

### Example dataset
- Karate dataset
- nodes: 34, edges: 78
- two communities with ground truth size >= 3

## How to run QOCE algorithm
1. Find all maximal cliques
```
$ cd GetMaxCliques
$ Set the minimum size of clique "minimumCliqueSize" in code called "find_cliques.cpp"
$ cd build
$ sh makefile
$ sh produceMaximumCliques
```
2. Detect communities from maximum cliques
```
$ cd QOCE_codes 
$ matlab 
$ mex -largeArrayDims rwvec_mex.cpp   % compile the mex file 
$ QOCE(k0,alpha) 
```
Command Options:

minimumCliqueSize: minimum size of clique (default: 3)

k0: steps of random walk for sampling (default: 3)

alpha: a parameter controls quadratic optimization (default: 0.2)

## How to run baseline algorithms
```
$ cd baseline_codes
$ sh complile-all.sh
$ sh run.sh
```

## Announcements

### Licence
This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but without any warranty; without even the implied warranty of merchantability or fitness for a particular purpose. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see http://fsf.org/.

### Notification
Please email to panshi@hust.edu.cn or setup an issue if you have any problems or find any bugs.

### Acknowledgement
In the program, we incorporate some open source codes as baseline algorithms from the following websites:
- [BIGCLAM](http://snap.stanford.edu/snap/download.html) codes in the SNAP distribution package
- [CFinder](http://hal.elte.hu/cfinder/wiki/?n=Main.Software)
- [DEMON](http://www.michelecoscia.com/?page_id=42)
- [NISE](http://lab.icc.skku.ac.kr/~jjwhang/codes/cikm2013/nise.html)
