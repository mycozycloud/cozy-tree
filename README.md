# Description

Cozy-Tree provides two tree structures used by Cozy application

```coffee
{DataTree, Tree} = require('cozy-tree')
t = new Tree()
```

## Tree
JS object with some feature to add easily properties from a string
representation.
JS object with properties like this :

all:
  todo: {}
  recipe:
    dessert:
      brownie: {}

could be created with this code :
tree = new Tree
tree.addNode "todo"
tree.addNode "recipe/dessert/brownie"

## DataTree

The aim of this class is to have a representation of the tree on server side.
The structure is close to what expect jstree on client side so that a simple
serialization can send the tree to the client .
All manipulations of the TreeData - creation renaming move delete update -
are done through the manipulation of Note
Structure of the tree :
      nodes : {"id_1":node_1, ... ,"id_n":node_n} hash table of all node.
          Ids are the same as notes ids.
          If you want to access to the node corresponding to a note : node = nodes[note_id]
      root : ref to the root node. Initialised with the node "All"
Structure of a node :
      _parent  : parentNode reference
      _id      : note.id
      children : []
      data     : note.title  => "data" corresponds to jstree requirements
      attr     : {id:note.id}


# About Cozy

Cozy is the personal
server for everyone. It allows you to install your every day web applications
easily on your server, a single place you control. This means you can manage
efficiently your data while protecting your privacy without technical skills.

More informations and hosting services on:
http://cozycloud.cc
