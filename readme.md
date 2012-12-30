
# peas.js
v0.7

Tree data structure in javascript.
prototype based implementation.

Tested with [basement tests](http://nzonbi.github.com/peas.js/) (tests in the browser)

license (MIT) included in "license" file.



## Documentation

Nodes are create with:

    var new_node = new pea( item )

The item parameter, is the node payload, assigned to new_node.item

A list of properties and methods of nodes objects is provided:

### nodes properties

* node.top
  parent node

* node.next
  next sibling or null

* node.prev
  previous sibling or null

* node.item
  Anything that is assigned as the node payload

* node.sub.n
  number of childs

* node.sub.first
  first child or null

* node.sub.last
  last child or null


### nodes methods

* node.sub.add( subnode )
adds subnode as last child of node, then returns subnode

* node.sub.at( index )
returns the child at index position (zero index)

* node.sub.insertAt( subnode, i )
Insert subnode as i (zero index) child of node. Returns subnode.

* node.rip()
Pulls node object from its tree, and returns it (node).
Other nodes of the tree are left in consistent state.

* node.walk( action )
Calls "action" function on all the nodes below "node". Descend
recursively on subnodes of subnodes.
On each case, the function will get as first and only parameter,
the current node that is acting upon.

* node.sub.each( action )
Calls "action" function on all the direct subnodes of "node",
only the first level of depth. No recursion.
On each case, the function will get as first and only parameter,
the current node that is acting upon.

* node.sub.onAllBelow( action )
Calls "action" function on all the descendants nodes of "node",
using recursion.
On each case, the function will get as first and only parameter,
the current node that is acting upon.

* node.flat()
Returns an array with references to all descendants nodes
of "node", in the tree.

* node.root()
Returns the root node of the tree, from where "node" is part of.

* node.putBefore( spare )
Inserts "spare" node into the tree where "node" is part of.
"spare" is inserted just befor of "node".

