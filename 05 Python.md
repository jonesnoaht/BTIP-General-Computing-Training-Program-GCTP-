# Python

Download Hydrogen in Atom, use Visual Studio as your IDE, or somesuch

Python should be considered to be a Swiss army knife of functionality. It is a language in which many packages have been written to perform many different types of tasks. Here are a few useful packages.

 - [PyYAML](https://pyyaml.org/) for processing YAML
 - [FCM](https://pythonhosted.org/fcm/index.html) The classic package for processing FCS files.
 - [FlowCytometryTools](https://github.com/eyurtsev/FlowCytometryTools) for processing flow cytometry files.


## PyYAML

For a quick script, see the end of 3 YAML.yml.

## FCM and FlowCytometryTools

Note that these are two different packages that we will be working with.

[Documentation](https://eyurtsev.github.io/FlowCytometryTools/)
[Basic tutorial](https://pythonhosted.org/fcm/basic.html)

### FCM

```{python}
import fcm

data = loadFCS('../sample_data/3FITC_4PE_004.fcs')
FCSreader('../sample_data/3FITC_4PE_004.fcs').parse_header()
```

### FlowCytometryTools

```{python}
import FlowCytometryTools

from FlowCytometryTools import test_data_dir, test_data_file
datadir = test_data_dir
datafile = test_data_file

print(sample.channel_names)
```

. . . and [so on](https://eyurtsev.github.io/FlowCytometryTools/tutorial.html)
