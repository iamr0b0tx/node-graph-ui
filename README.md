# node-graph-ui

A user interface paradigm based on node graphs. We provide an computer interface via interactive nodes, each node does
mostly one thing and that thing well.

## 1 Structure

The user interface is composed of nodes, the node are divided into
different conceptual types Expressive nodes and Active nodes.

### 1.1 Expressive Nodes

These are nodes that "return" data. E.g. A node that performs addition is an expressive node, this is because it takes "
inputs" (other nodes) and adds them up to return something else which can be "output-ed" by another node

### 1.2 Active nodes

These nodes "do things", E.g. you could have a node that can show the value returned from an Adder Node, like a screen.

## 2 Use cases

### 2.1 Programming

#### 2.1.1 Text Editing

To solve NGUI for programming we need to solve it for text editing first. We could do this naively by offering a text
editing node, this would be like a text editing window but as a node.

#### 2.1.2 Programming node types

We would need to customize a simple text editing node to make it more useful for programming. We need to provide some if
not all the following

- Syntax highlighting
- Go To definition

### 2.2 Media

#### 2.2.1 Images

#### 2.2.2 Videos

#### 2.2.3 Audio

##### 2.2.3.1 Music

#### 2.2.3 Games

## 3 Development

We would provide a ngui framework that allows for the development of nodes, a node graph visualizer and node graph
server. At the art of the framework would be

- The node graph visualizer: This would be the rendering engine for the node graphs, this allows to visualize and
  interact with the visual elements the node graph provides
- The node server: some node graphs would have specific nod graph servers that they communicate with. This would be like
  a specialized store and logic specific to some nodes. E.g. we could have a image preview node graph with a resize
  command that the server can accept and re-render for the node ui.

Inherently a nodes have the following side

- Frontend: The specification of the UI/UX for the node and some logic to perform some frontend actions
- Backend: This is the node server, this allows for performing some complex actions that are too complicated for the Ui
  to handle. This also allows for asynchronous processing of the UI

## 4 User Interface

The user interface is asynchronous as each node processes independently for other nodes unless they have a dependency.
There UI is managed in sessions, each session is a infinite canvas that starts off blank with no nodes. There is a
spotlight that allows use to reach into the system and initialize genesis nodes, this could be something like opening a
music files that starts a music player node or a browser search that opens a browser node.

### 4.1 Expansion

Because of the simplistic, single responsibility nature of nodes, we need initialization of more nodes to accomplish
more tasks or complex actions. The process of initializing more nodes from one is called expansion