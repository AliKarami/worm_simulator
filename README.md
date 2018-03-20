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
Generate a random graph, and save it as a CSV file.

Options:
  -h, --help            show this help message and exit
  -o FILE, --out=FILE   Write the output graph in CSV format to FILE
  -v VERTICES, --vertices=VERTICES
                        Size (vertex count) of the output graph
  -e probability, --erdos=probability, --erdos-renyi=probability
                        Generate an Erdös-Rényi output graph, with the
                        specified probability of edge creation. A value of
                        0.015 produces fairly sparse but typically connected
                        graphs, while 0.5 chooses from graphs uniformly among
                        those of degree equal to that specified by the -v
                        parameter.
  -b edges, --barabasi=edges, --barabasi-albert=edges
                        Generate a Barabási-Albert output graph, with the
                        specified number of edges per new node.
  -w pksum, --watts=pksum, --watts-strogatz=pksum
                        Generate a Watts-Strogatz graph, where pksum is p + k,
                        with p being the probability of an edge being
                        replaced, and k being the number of neighbors per sub-
                        ring. I prefer 2.25 or so.

The program is unable to generate more than one graph at a time, and so cannot
run when any pair of -e, -b, and -w are specified.
```
**Libraries used**:
- Networkx
- matplotlib