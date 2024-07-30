## FunctionName

`⏰ Yields` `🌎 Global` `🪲 Inconsistent` `🔎 Needs Investigation` `📌 Custom Tag`

```lua
function FunctionName(param: any): ()
```

Describe the function in a understandble and a nice way.

You may write a whole documentation about the Function if you like to.
You can make it have info cards.

> ### 🔎 Notes, tips, info
> Additional information or URLs that lead to a documentation of the Function.

> ### ⚠️ Warnings, risks
> Exercise caution.

> ### ⛔ Danger!
> Avoid making this mistake.

> ### 🪲 Bugs, issues
> Document known issues or possible issues.

### Parameters

 * `param` - The parameter description.
```lua
FunctionName(param: any)
```

### Aliases

 * `functionAlias`
 ```lua
FunctionName(param: any)
FunctionName2 = FunctionName or FunctionName(param: any)
```

 * `badAlias` - Optional justification.

### Example

A description of the example that follows.

```lua
print(FunctionName()) --> (string, void or etc...)

local ReturnString = function(str)
    return str
end

print(ReturnString("Hello World!")) --> (string)
```

Here is another example on how it should be:

```lua
GetThread = function() -- Environment Functions should always be Global and never Local.
	return coroutine.running() -- Current Running Thread.
end

CloseThread = function()
    coroutine.running():Close() -- It is better to remake the GetThread function here or else if you nil GetThread it will break CloseThread. And lets at least make one work if someone nils the other Functions that CloseThread uses.
end

GetCurrentThread = GetThread or function() -- This is a Alias, if GetThread doesnt exist, it makes a new function.
	return coroutine.running()
end

CloseCurrentThread = CloseThread or function() -- This is a Alias, if CloseThread  doesnt exist, it makes a new function.
    coroutine.running():Close()
end

getgenv().GetThread = GetThread
getgenv().CloseThread = CloseThread
getgenv().GetCurrentThread = GetCurrentThread -- Alias
getgenv().CloseCurrentThread = CloseCurrentThread -- Alias


print(GetThread()) --> (Thread)
CloseThread() -- If you Close the Current Thread, you cant Connect back to it, because we are Closing the Thread. You can Yield the Thread to be able to still make the Thread run. You can go to: https://raw.githubusercontent.com/OfficialValkyrie/Lua/main/ImmortalThread for a Script that can revive the Current Yielded Thread.
```
