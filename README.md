# pvtrace
Visualize function calls with Graphviz (Source code by M. Tim Jones)

By utilizing the gcc compiler option -finstrument-functions a dynamic function address trace can be recorded. The pvtrace utility provide by this project converts that record into a dot graph that can then be visualised.

The process for creating the call trace graph is as follows:

# Compile in the instrumentation
gcc -g -finstrument-functions instrument.c all-other-source-files.c -o exename

# Run the executable to generate the stack trace (output is trace.txt)
./exename

# Convert the trace.txt to a graphviz dot file (output is graph.dot)
pvtrace exename

# Convert the dot graph into a jpeg for visualisation (output is graph.jpg)
dot -Tjpg graph.dot -o graph.jpg

An article containing full details of this procedure and how it works behind the scenes was written by the pvtrace source code author M. Tim Jones.  This article was available on IBMs developer works website in 2005 and a pdf version can be found in this repository.
