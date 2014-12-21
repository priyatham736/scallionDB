scallionDB
==========

An in memory JSON tree database. 

Requirements:
* Python 2.7+
* pyzmq 14.4+

Let's agree on a format. '_id' represents a node and hence should be unique. '_children' represents a node's children and hence should be an array. Example

```
{"a":1,"b":5,"_id":"aaaa",
"_children":[{"a":7, "c":20,"_id":"bbbb",
            "_children":[{"b":-1, "a":45, "bar":"a","_id":"cccc",
	                     "_children":[{"foo":"bar","_id":"dddd","_children":[]}]
						 },
                         {"b":-1, "f":25, "bar":"b","_id":"eeee",
	                     "_children":[{"foo":"baz","_id":"ffff","_children":[]}]
						 }			 
						 ]		
			},
           {"a":-4, "r":0,"_id":"gggg",
            "_children":[{"x":-1, "a":-45,"bar":"c","_id":"hhhh",
	                     "_children":[{"foo":"bar","_id":"iiii","_children":[]}]
						 },
                         {"y":-1, "f":75,"bar":"d","_id":"jjjj",
	                     "_children":[{"foo":"ball","_id":"kkkk","_children":[]}]
						 }			 
						 ]		
			}]
}
```


### Start the server

```
bin/scallion.py start
```

### Using the client library

```python
import sys
#sys.path.append('<path to pyscallion's parent folder>')
from pyscallion import ScallionClient

client = ScallionClient()
client.showTrees()
#'[]'


```
