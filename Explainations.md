# Explainations

## vartype: ```temp, server, global``` This is the variable type.

## varname: Name of your variable.

## type: 

|Type|Representation|
|----|-------|
|guild|Represents a Guild|
|channel|Represents a Channel|
|message|Represents a Message|
|role|Represents a Role|
|member|Represents a GuildMember|
|user|Represents a User|
|buttoninteraction|Represents a ButtonInteraction|
|selectinteraction|Represents a SelectInteraction|
|commandinteraction|Represents a CommandInteraction|
|string|Represents a String|
|number|Represents a Number|
|emoji|Represents a Emoji|
|row|Represents a Row|

vardesc: This will be a small description about your variable

## Copypaste this under the html of your mod.

```html
<script>
    $(document).on("click", "#saveEditResponseBtn", function(e) {
        if(e.target.parentElement.parentElement.children[0].children[0].innerHTML.includes(this.name)){
            varname = document.getElementById("varname").value
            vartype = document.getElementById("vartype").value
            type = "member"
            vardesc = "This variable is sus"
            varid = "id"
            newVar(vartype, varname, type, vardesc, varid)
        }
    })
    function newVar(vartype, varname, type, vardisplay, id) {
        if(vartype && varname && type && vardisplay && id) {} else { return alert("[newVar] Missing parameters") }
        if(document.getElementById(id)){
            document.getElementById(id).remove()
        }
        var newLiHtml =
            '<li id="' + id + '"' + 'class="list-group-item py-0" vartype="' + type + '">';
        newLiHtml +=
            "<strong>" + vartype + "Vars." + varname + "</strong> - " + vardisplay + " mod variable</li>";
        $("#UserVariableList").append(newLiHtml);
    }
</script>
```
