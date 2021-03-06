# worm_simulator
This is a pair of Python scripts intended to simulate the propagation of a worm through a network (simulated as an undirected graph).  
## simulate_worm.py
```
Load a random graph from a CSV file,infect a given node, and spread with a
given probability.

Options:
  -h, --help            show this help message and exit
  -n FILE, --network=FILE
                        Opens the csv-formatted networkCSV-format file located
                        at FILE.
  -p PROBABILITY, --infection-probability=PROBABILITY
                        The probability that an infection will spread
  -f NODE, --first-infected=NODE
                        The index of the initially infected node. Default
                        (random): choose a node at random.
  -i NODE, --inoculator=NODE
                        The index of the first inoculator node. Default is
                        None (no argument supplied means no inoculation), and
                        an inoculator can be chosen at random by specifying
                        'random'.
  -q PROBABILTIY, --inoculation-probability=PROBABILTIY
                        The probability that a node will be inoculated(and
                        cured).
```
## make_network.py
```
Generate a random graph, and save it as a CSV file containing its edges.

Options:
  -h, --help            show this help message and exit
  -o FILE, --out=FILE   Write the output graph in CSV format to FILE. Defaults
                        to 'graph.csv' inside the current working directory.
  -v COUNT, --vertices=COUNT
                        Size (vertex count) of the output graph
  -p VALUE, --probability=VALUE
                        This argument is used to specify a probability for use
                        with either the -e or -w option. VALUE must be between
                        0 and 1.
  -n NUM, --num-edges=NUM, --number-of-edges=NUM, --num-neighbors=NUM, --number-of-neighbors=NUM
                        This argument is used to specify a number of edges for
                        use when generating a Barabási-Albert network with the
                        -b option, or to specify the number of neighbors when
                        generating a Watts-Strogatz network with the -w
                        option.
  -e, --erdos, --erdos-renyi
                        Generate an Erdös-Rényi output graph, with the
                        specified probability of edge creation. A value of
                        0.015 produces fairly sparse but typically connected
                        graphs, while 0.5 chooses from graphs uniformly among
                        those of degree equal to that specified by the -v
                        parameter. Probability is specified with -p <value>.
  -b, --barabasi, --barabasi-albert
                        Generate a Barabási-Albert output graph, with the
                        specified number of edges per new node. Number of
                        edges is specified with -n <value>.
  -w, --watts, --watts-strogatz
                        Generate a Watts-Strogatz graph, with the specified
                        probability of random swaps as well as the specified
                        number of (initially) short-circuited neighbors.
                        Number of neighbors is specified with -n <value>, and
                        probability is specified with -p <value>.
  -d, --display, --draw
                        Enable matplotlib drawing and display of the generated
                        network. Not recommended for graphs with more than
                        several hundred vertices.

The program is unable to generate more than one graph at a time, and so cannot
run when any pair of -e, -b, and -w (or all three) are specified.
```
**Libraries used**:
- Networkx
- matplotlib