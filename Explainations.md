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

## vardesc: This will be a small description about your variable.

## id: Id of variable. This id is used to find the variable and replace on change. Recomended to use mod name(Ex. MyModNameVar1)

# Picture

![image](https://user-images.githubusercontent.com/55946112/163659511-81458107-8d09-4377-978c-3c845be61e5e.png)


# Copypaste this under the html of your mod.

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
        
            varFunc(vartype, varname, type, vardesc, varid)
        }
    })
    function varFunc(vartype, varname, type, vardesc, id) {
        if(vartype && varname && type && vardesc && id) {} else { return alert("[varFunc] Missing parameters") }
        
        if(document.getElementById(id)){
            document.getElementById(id).remove()
        }
        var newLiHtml = '<li id="' + id + '"' + 'class="list-group-item py-0" vartype="' + type + '">';
        newLiHtml += "<strong>" + vartype + "Vars." + varname + "</strong> - " + vardesc + " mod variable</li>";
        $("#UserVariableList").append(newLiHtml);
    }
</script>
```

# Example Mod wtih this function

```js
module.exports = {
    // Set this to the name of the mod. This is what will be shown inside of Discord Bot Studio.
    // THIS FILE NAME MUST BE THIS VALUE WITH SPACES REMOVED
    name: "VarExample",

    // Place the author of the mod here. This is an array so you can add other authors by writing ["Great Plains Modding", "New User"]
    author: ["PlayboyPrime#3839"],

    // Place the version of the mod here.
    version: "1.0.0",

    // Whenever you make a change, please place the changelog here with your name. Created Send Message ~ Great Plains Modding\n
    changelog: "",

    // Set this to true if this will be an event.
    isEvent: false,
    
    isResponse: true,

    // Set this to true if this will be a response mod.
    isMod: true,

    // If you want to modify a core feature, set this to true.
    isAddon: false,

    // Here you can define where you want your mod to show up inside of Discord Bot Studio
    section: "Message",
  
    // Place your html to show inside of Discord Bot Studio when they select your mod.
    html: function(data) {
        return `
        <div class="form-group">
            <label>Variable Name *</label>
            <input class="form-control needed-field" id="varname" name="varname">
            <div class="form-group">
                <label>Variable Type *</label>
                <select class="form-control" id="vartype" name="vartype">
                    <option value="temp" selected>Temp Variable</option>
                    <option value="server">Server Variable</option>
                    <option value="global">Global Variable</option>
                </select>
            </div>
        </div>

        <script>
            $(document).on("click", "#saveEditResponseBtn", function(e) {
                if(e.target === this){
                    varnameid = "varname"
                    vartypeid = "vartype"
                    type = "guild"
                    vardesc = "This variable is sus"
                    varid = "VarExampleVar1"
                
                    //ignore
                    vartype = document.getElementById(vartypeid).value
                    varname = document.getElementById(varnameid).value
                
                    varFunc(vartype, varname, type, vardesc, varid)
                }
            })
            function varFunc(vartype, varname, type, vardesc, id) {
                if(vartype && varname && type && vardesc && id) {} else { return alert("[varFunc] Missing parameters") }
                
                if(document.getElementById(id)){
                    document.getElementById(id).remove()
                }
                var newLiHtml = '<li id="' + id + '"' + 'class="list-group-item py-0" vartype="' + type + '">';
                newLiHtml += "<strong>" + vartype + "Vars." + varname + "</strong> - " + vardesc + " mod variable</li>";
                $("#UserVariableList").append(newLiHtml);
            }
        </script>
        `;
    },

    // When the bot is first started, this code will be ran.
    init: function() {
        console.log("Loaded VarExample");
    },
    
    // Place your mod here.
    mod: function(DBS, message, action, args, command, index) {
        
        DBS.callNextAction(command, message, args, index + 1);
    }
};
```
