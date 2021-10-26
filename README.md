# AT4val
A pythonian (sage) version of the Census of arc-transitive tetravalent graphs by Potočnik, Spiga and Verret.

From Potočnik [website](https://www.fmf.uni-lj.si/~potocnik/work.htm) we obtained the following description

> Based on some theoretical work of Pablo Spiga, Gabriel Verret and myself, we were able to construct a complete list of all tetravalent arc-transitive graphs on at most 640 vertices. The magma code which generates the sequence of these graphs can be found [here](https://www.fmf.uni-lj.si/~potocnik/work_datoteke/Census4val-640.mgm). If you use this list for research purposes, please cite the following papers: P. Potočnik, P. Spiga, G. Verret, Bounding the order of the vertex-stabiliser in 3-valent vertex transitive and 4-valent arc-transitive graphs, J. Combin. Theory Ser B 111 (2015), 148-180, and P. Potočnik, P. Spiga, G. Verret, Cubic vertex-transitive graphs on up to 1280 vertices, J. Symbolic. Comp. 50 (2013) 465-477. We would also like to thank Marston Conder who provided the list of all regular maps with at most 640 edges, which were needed to compile this census.

In this repo you will find the following files:

1. `Census4val-640.sage `. This is a `sage` file which contains a (python) dictionary consisting of the sage versions of the graphs in the original Census. The keys of the dictionary are meant to match those from the original code so what is called `AT4val[21,1]` in the Magma version should be referenced as `AT4val[(21,1)]` in the python version.

2. A colection of files with name `Census4val-AAA-BBB.sage`. Each of these files creates the dictionary `AT4val` (if it does not exists already) and imports the graphs of order in between `AAA` and `BBB`.

3. A file named `Census4val-640_lists.py ` which creates the dictionary `AT4val_lists`
and fills it with the lists of edges of the graphs in the census (whithout actually creating the Graphs). This is pure python (no sage) and can be used to build the graphs somewhere else.

4. A binary file `AT4val` which contains the dictionary `AT4val` and can be imported using [pickle](https://docs.python.org/3/library/pickle.html) with the code

  ```
  import pickle
  AT4val = pickle.load(open('AT4val','rb'))
  ```
  You have to trust me on this.
