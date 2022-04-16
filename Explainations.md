# Explainations

vartype: (temp, server, global) This is the variable type

varname: Name of your variable

type: member, row, number, string, channel, emoji, guild, message, role, user, buttoninteraction, selectinteraction, commandinteraction

|Type|Explain|
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

# Copy Paste

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
