# Choose Your Own Adventure

An interactive text adventure built on a tree data structure.

## How to run

```bash
python3 script.py
```

Enter `1` or `2` at each prompt to navigate the story. Four possible endings.

## How it works

Each story section is a `TreeNode` holding two things: the text to display,
and a list of the choices available from that point. Choices are the node's
children, so the story's branching structure *is* the tree's structure.

`traverse()` walks a single path from the root, guided by user input:

```python
while story_node.choices != []:
    choice = input("Enter 1 or 2 to continue the story: ")
    story_node = story_node.choices[int(choice) - 1]
```

## Why a tree

Story endings need no special handling — a node with an empty `choices` list
is a leaf, and the loop stops on its own. Adding a new branch means adding
nodes; `traverse()` never changes, no matter how deep the story goes.

The alternative — nested `if/elif` blocks — would grow with every branch
and need rewriting to add a level.

## Built with

Python 3, no dependencies. Part of the Codecademy Computer Science path.
