```javascript
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>bildup table with dom structure</title>

    <style media="screen">
      td,tr{
        border: 1px solid black;
      }
      cell{
        text-align: right;
      }
    </style>

    <script type="text/javascript">
        window.onload = function() { //run function inside after page and its elements are loaded
            function buildup(array) {
                //lets create a table node
                var table = document.createElement("table");
                var root = document.getElementById("root"); //we created div by an id 'root' in html
                // and then connect the node p to it. but if div was not there we had to
                // go in create node for body, html and connect them all
                root.appendChild(table);
                var thead = document.createElement("thead");
                table.appendChild(thead);
                var tr = document.createElement("tr");
                thead.appendChild(tr);
                for (var key in array[0]) {
                    tr.appendChild(document.createElement("td")).appendChild(document.createTextNode(key));
                }
                for (var i = 0; i < array.length; i++) {
                    var tr = document.createElement("tr");
                    for (var key in array[0]) {
                        var td = document.createElement("td")
                        var cell = document.createTextNode(array[i][key]);
                        td.appendChild(cell);
                        tr.appendChild(td);
                    }
                    thead.appendChild(tr)
                }
                return table;
            }
            buildup(Mountains)
        }
        var Mountains = [{
            name: "Kilimanjaro",
            height: 5895,
            country: "Tanzania"
        }, {
            name: "Everest",
            height: 8848,
            country: "Nepal"
        }, {
            name: "Mount Fuji",
            height: 3776,
            country: "Japan"
        }, {
            name: "Mont Blanc",
            height: 4808,
            country: "Italy/France"
        }, {
            name: "valselberg",
            height: 323,
            country: "Netherland"
        }, {
            name: "Dennali",
            height: 6168,
            country: "United States"
        }, {
            name: "Poppcatepetl",
            height: 5465,
            country: "Mexico"
        }];
    </script>
</head>


<body>
    <div id="root">
        <p>To Create a wrapper</p>
    </div>

</body>

</html>
```
