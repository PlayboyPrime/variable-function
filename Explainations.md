# Explainations

## varselectid: Id of vartype select.

## varnameid: Id of varname input.

## type: This will be the variable type. 

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

vardesc: This will be a small description about your variable.

id: Id of variable. This id is used to find the variable and replace on change. Recomended to use mod name(Ex. MyModNameVar1)

## Picture

![image](https://user-images.githubusercontent.com/55946112/163659511-81458107-8d09-4377-978c-3c845be61e5e.png)


## Copypaste this under the html of your mod.

```html
<script>
    $(document).on("click", "#saveEditResponseBtn", function(e) {
        if(e.target === this){
            varnameid = ""
            vartypeid = ""
            type = ""
            vardesc = ""
            varid = ""
        
            //ignore
            vartype = document.getElementById(vartypeid).value
            varname = document.getElementById(varnameid).value
        
            VarMod(vartype, varname, type, vardesc, varid)
        }
    })
    function VarMod(vartype, varname, type, vardesc, id) {
        if(vartype && varname && type && vardesc && id) {} else { return alert("[VarMod] Missing parameters") }
        
        if(document.getElementById(id)){
            document.getElementById(id).remove()
        }
        var newLiHtml =
            '<li id="' + id + '"' + 'class="list-group-item py-0" vartype="' + type + '">';
        newLiHtml +=
            "<strong>" + vartype + "Vars." + varname + "</strong> - " + vardesc + " mod variable</li>";
        $("#UserVariableList").append(newLiHtml);
    }
</script>
```

# Example Mod

