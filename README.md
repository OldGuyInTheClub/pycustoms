# pyCustoms
pyCustoms inspects Python packages and optionally graphs dependencies

Matlab's functions are straightforward: One file per function, send in inputs and get outputs. Python likes namespaces, modules, classes, objects, and packages so a lot of capability is buried deep in package hierarchies. Combine that with documentation that varies from good to nonexistent and it can be tough to figure out what to invoke and how to invoke it.

pyCustoms is experimental spaghetti code to inspect a package and figure out what links to what. It uses importlib to programmatically load packages, dir to get information, and inspect to identify builtins, classes, functions, modules, and 'none of the above' aka nofta.

pyCustoms returns a tree-like defaultdict of all results and a dependency list of tuples that show how modules, which seem to be the most important, link to one another.

A separate draw_graph function takes the pyCustoms results and uses graphviz to generate a visual representation with some choice of engines, layout options, and the like. The network view is amusing initially since the right choice of parameters can make it look like a fireworks display. It takes a lot of zooming and panning to see the details and ultimately the prettyprinted defaultdict is faster and more useful.

This code could be improved substantially, turned into a class, and so on but the results of this experiment don't justify that effort.
Ravi Narasimhan
3 June 2017
