
## Explainations

vartype: (temp, server, global) This is the variable type

varname: Name of your variable

type: member, message, user whatever

vardesc: This will be a small description about your variable

```js
<script>
    // Function to create a new variable in dbs
    function newVar(vartype, varname, type, vardisplay) {
        // Remove if already exists
        if(myVar){
            myVar.remove()
       }

       var newLiHtml =
           '<li class="list-group-item py-0" vartype="' + type + '">';
       newLiHtml +=
           "<strong>" + vartype + "Vars." + varname + "</strong> - " + vardisplay + " mod variable</li>";
       var myvar = $("#UserVariableList").append(newLiHtml);
    
    }
</script>
```
