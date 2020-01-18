# helm-inspector

### Overview
This project provides an interactive tree view of a Kubernetes Helm chart and its dependencies.

The tree view is loaded from a JSON representation of the Helm chart such as can be generated from
https://github.com/Alfresco/alfresco-anaxes-chartmap.  The tree is created using [D3](https://d3js.org/).

The user starts out in *navigation* mode in which the user
can click through the nodes of the tree to see the relationships between a Helm chart and its dependencies
as well as the Docker Images on which a Helm chart depends.  The user can then elect to go into an
*inspection* mode in which the details of a Helm Chart or Docker image can be viewed by hovering the
mouse pointer over a node in the tree.

### Thanks 
This was inspired by [https://bl.ocks.org/d3noob/1a96af738c89b88723eb63456beb6510](https://bl.ocks.org/d3noob/1a96af738c89b88723eb63456beb6510)
which was in turn inspired by the collapsible-tree example in [https://observablehq.com](https://observablehq.com).

### License
MIT
