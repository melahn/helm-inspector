# helm-inspector

### Overview
This project provides an interactive tree view of a Kubernetes Helm chart and its dependencies.

The tree view is loaded from a file containing a JSON representation of the Helm chart,
such as can be generated from
https://github.com/Alfresco/alfresco-anaxes-chartmap, though any properly formed JSON 
representation will work. See [JSON Model](#json-model)

The tree view is created using [D3](https://d3js.org/) Version 5.

The user starts out in *navigation* mode in which the user
can click through the nodes of the tree to see the relationships between a Helm chart and its dependencies
as well as the Docker images on which a Helm chart depends.  The user can then elect to go into an
*inspection* mode in which the details of a Helm chart or Docker image can be viewed by hovering the
mouse pointer over a node in the tree.

### Usage
1. Download the two files 'helm-inspector.json' and 'helm-data.json'
2. Open the file 'helm-inspector.json' in a browser

You start out in 'navigate mode'.  Clicking on a dark node in the tree expands the node to see the children.
Clicking on an expanded node collapses the node, hiding the children.

Pressing the 'i' key puts you in 'inspect' mode.  In this mode, hovering over a node shows details of that node.

Pressing the 'n' key puts you back in 'navigate' mode.

#### Navigate Mode Example
![Navigate Mode Example](./resources/navigate-mode-example.png)
#### Inspect Mode Example
![Inspect Mode Example](./resources/inspect-mode-example.png)

*Note*: You can generate different 'helm-data.json' files using https://github.com/Alfresco/alfresco-anaxes-chartmap
or create one any way you want as long as the file conforms to the [JSON Model](#json-model).

### <a name="json-model"></a>JSON Model
The file containing the helm data must be in a file named 'helm-data.json' accessible from the html
page.  

The file contains a single JSON object representing the helm tree.  

Each JSON element with properties represents a Helm chart or a Docker images used by a chart.

Each JSON element that represents a chart or an image must have a 'name' property which is
the full name of the chart or image including a version if applicable.

Each JSON element that represents a chart or an image must have a 'type' property which has a value
of 'chart' or 'image', denoting the type of element.

Each JSON element that represents a chart or an image must have a 'children' property containing 
an array of the child elements of that chart or image, if any.  If there are no child elements, then
the array should be empty, but it still must be present.

### Credits 
The clickable tree view was inspired by [https://bl.ocks.org/d3noob/1a96af738c89b88723eb63456beb6510](https://bl.ocks.org/d3noob/1a96af738c89b88723eb63456beb6510)
which was in turn inspired by the collapsible-tree example in [https://observablehq.com](https://observablehq.com).

### License
MIT
