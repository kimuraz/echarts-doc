
{{target: series-sankey}}

# series.sankey(Object)

** Sankey Graphs **

Sankey diagram is a specific type of streamgraphs(can also be seen as a directed acyclic graph). In which the width of each branch is shown proportionally to the flow quantity. These graphs are typically used to visualize energy or material or cost transfers between processes. They can also visualize the energy accounts, material flow accounts on a regional or national level, and also the breakdown of cost of item or services.

**Example: **

~[700x580](${galleryViewPath}sankey-energy&edit=1&reset=1)


<br>
**Visual Encoding: **

The sankey graphs encodes each `node` of the raw data into a small rectangular. And different nodes are presented in different colors as far as possible. The `label` next to the small rectangular, which encoding the name of the node.

In addition, the edge between two small rectangulars in the graph encoding the `link` of the raw data. The width of edge is shown proportionally to the `value` of `link`.



## type(string) = 'sankey'

{{use: partial-component-id(prefix="#")}}

{{ use: partial-rect-layout-width-height(
    componentName='sankey',
    defaultLeft: '5%',
    defaultRight: '20%',
    defaultTop: '5%',
    defaultBottom: '5%',
    defaultWidth: 'null',
    defaultHeight: 'null'
) }}


## nodeWidth(number) = 20

The node width of rectangle in graph.


## nodeGap(number) = 8

The gap between any two regtangles in each column from the graph.


## layoutIterations(number) = 32

The iterations of layout, which is used to continuously optimize the positions of nodes in graph, decreasing the overlapping between nodes and edges.

The default iterations of layout: `32`.

The test shows that iterations of layout could not be less than the default value.

## draggable(boolean) = true

The drag-and-drop interaction of the node, which is enabled by default. After opening, the user can drag any node in the Sankey diagram to any position. To turn this interaction off, simply set the value to `false`.

## focusNodeAdjacency(boolean|string) = false

Mouse hover to the node (edge), adjacent nodes and edges highlighted interaction, default off, can be manually opened. When hover to the node, three highlighting methods are provided: 1) The outgoing edges of the corresponding node are highlighted, and the value is `'outEdges'`. 2) The incoming edges of the corresponding node are highlighted, and the value is `'inEdges'`. 3) All the edges that adjacent to the node are highlighted, and the value is `'allEdges'`. When hover to the edge , Uniformly edges and two adjacent nodes of the edge are highlighted.

## label(Object)

`label` describes the text label style in each rectangular node.

{{use:partial-label(
    prefix="##",
    defaultShowLabel=true,
    defaultPosition="'right'",
    formatter1d=true
)}}

## itemStyle(Object)

The style of node rectangle in sankey graphs.

{{use: partial-item-style(
    prefix="##",
    useColorPalatte=true,
    defaultBorderWidth=1,
    defaultBorderColor="'#aaa'"
)}}


## lineStyle(Object)

The line style of sankey graph, in which [lineStyle.color](~series-sankey.lineStyle.color) can be assigned to the value of `'source'` of `'target'`, then the edge will automatically take the source node or target node color as its own color.

{{use: partial-sankey-line-style(prefix="##")}}


## emphasis(Object)
### label(Object)
{{use:partial-label(
    prefix="###",
    formatter1d=true
)}}
### itemStyle(Object)
{{use: partial-item-style(prefix="###")}}
### lineStyle(Object)
{{use: partial-sankey-line-style(
    prefix="###"
)}}


## data(Array)

{{ use: partial-1d-data-desc() }}

### name(string)

The name of data item.

### value(number|Array)

The value of data item.

### itemStyle(Object)

The style of this node.
{{use:partial-item-style(prefix="###", useColorPalatte=true)}}

### label(Object)

The lable style of this node.
{{ use:partial-label(
    prefix="###"
) }}

### emphasis(Object)
#### itemStyle(Object)
{{use:partial-item-style(prefix="####")}}
#### label(Object)
{{ use:partial-label(
    prefix="####"
) }}

{{use: partial-tooltip-in-series-data(
    galleryViewPath=${galleryViewPath}
)}}


## nodes(Array)

Equals to [data](~series-sankey.data)

## links(Array)

The links between nodes. **Notes: The Sankey diagram theoretically only supports Directed Acyclic Graph(DAG), so please make sure that there is no cycle in the links.** For instance:

```js
links: [{
    source: 'n1',
    target: 'n2'
}, {
    source: 'n2',
    target: 'n3'
}]
```

### source(string)

The [name of source node](~series-graph.data.name) of edge

### target(string)

The [name of target node](~series-graph.data.name) of edge

### value(number)

The value of edge, which decides the width of edge.

### lineStyle(Object)

The line stlye of edge.
{{use:partial-sankey-line-style(
    prefix="###"
)}}

### emphasis(Object)

#### lineStyle(Object)

{{ use:partial-sankey-line-style(
    prefix="####"
) }}

## edges(Array)

Equals to [links](~series-sankey.links)

{{ use:partial-silent(
    prefix="#"
)}}

{{use: partial-animation(
    prefix="#",
    defaultAnimationEasing="'linear'",
    defaultAnimationDuration=1000,
    galleryEditorPath=${galleryEditorPath}
)}}


{{use: partial-tooltip-in-series(
    galleryViewPath=${galleryViewPath}
)}}




{{target: partial-sankey-line-style}}

#${prefix} color(Color) = "'#314656'"
The color of the edge in sankey graphs.

#${prefix} opacity(number) = 0.2
The opacity of the edge in sankey graph.

#${prefix} curveness(number) = 0.5
The curveness of the edge in sankey graph.

{{use: partial-style-shadow(prefix=${prefix})}}
