# OADS
OADS, For **O**dna **A**PI **D**ocumentation **S**tandards, is a proposal for a javascript unified documentation writing style.

## Quick Example

```javascript
presentMe("name", #age*) => "msg"
```
Gives a textual presentation of a person.

- "name": The person's name.
- #age*: The person's age.

Eg:
 ```javascript
var p = presentMe('Mohamed', 25);
// p: 'This is Mohamed, he/she is 25 years old'
```


This means, *presentMe* is a function that has two parameters:
1. name: that is a **string** because it's quoted.
2. age: that is an **integer** because it is preceded by `#`. And is **optional** because it is followed by `*`.

And returns a string result.

**_Do you Like the idea?_** So let's continue reading the guide:
## Guide
### Global Structure
```javascript
fnName(param1, param2) => result
```
Here is the function description
- param1: The description of param1.
- param2: The description of param2.
- result: The description of result if needed.

Eg:
```javascript
var v = fnName(param1, param2);
// v: newValue
```

#### Explanation
1. You start by writing the function line just as if were calling it in the code, with one more thing, the return part.

    So the line has 3 parts:
    1. Function name
    2. Parameters list: We'll see later how to add more informations to this part.
    3. Return value: This part is the one more thing added to what you used to see.

        It starts with `=>` followed by the returned variable that you name as you like (Try to give it a clear name in order to make it understandable).
2. Write the function's description just under the function line.
3. List your function's parameters with their descriptions.

    > If you need to describe the return value, put it at the end of this list.

4. Now write an example of your function use, If you want every reader to be happy.

    The recommended way to write examples is:
    1. Write 'Eg:'
    2. Write your function example.
    3. In a comment, write the variables that changed with your function.

### Optional & Required parameters
To mark a parameter as **optional**, just follow it by `*`.

Eg:
```javascript
array.join(separator*)
```
> You understand from this, that if the parameter isn't followed by `*`, it means that it is **required**.

### Rest parameters

Just as you write it in your code, just add `...` before the parameter name to mention that the variable takes all the rest arguments.

Eg:
```javascript
sort(...numbers)
```

### Variable Types
Now will be discussing variable types, this includes parameters and return values.
#### String
To mark a variable as a string, just quote it.

Eg:
```javascript
array.join("separator"*)
```

> You can use single quotes too

#### Number
To mark a variable as number, precede it by `%`.

Eg:
```javascript
Math.abs(%x);
```

##### Integer & Float

You can be more precise and mark variable as an integer or a float.

For **integers**, use `#`.

Eg:
```javascript
toFixed(#digitsNumber*)
```

For **floats**, use `.`.

Eg:
```javascript
Math.floor(.x)
```

#### Boolean
To mark a variable as boolean, use `?`.

Eg:
```javascript
alertIfTrue(?shouldAlert)
```

#### Array
To mark a variable as array, put it in brackets `[]`.

Eg:
```javascript
[myArray].join()
```

##### Elements Type
You can specify the array elements' type by specifying it inside the brackets.

Eg:
For an array of strings
```javascript
setNames(["names"])
```

#### Plain Objects
To mark a variable as plain object, put it in curly brackets `{}`.

And describe its properties under its description.

Eg:
```javascript
setUser({user})
```
Sets a user.
- {user}: The user to set.
    - "firstName": The users first name.
    - "lastName": The users last name.

#### Enum
To mark a variable as enum, use `|`.

And list its values under its description.

Eg:
```javascript
dateOfNext(|day)
```
Gives the date of the next day passed.
- |day: The day you want to get its date.
    "Monday"|"Tuesday"|"Wednesday"|"Thursday"|"Friday"|"Saturday"|"Sunday"

#### Function
To mark a variable as function, add `()`.

Put inside the parentheses, the function parameters and describe them under the function's description.

Eg:
```javascript
load(callback("element"))
```
Loads element.
- callback(): The callback function.
    - "element": The element loaded.

#### Other
For any other type you can write the type name before the variable.

Eg:
```javascript
stringFormat(Date myDate)
```

#### Unspecified
If the variable's type is not specified, use nothing.

Eg:
```javascript
Array.isArray(myVariable)
```
#### Combining Types
To combine multiple types in one variable, use them together.

Eg: In this example, our variable can be either a string or a number
```javascript
parseInt(%"x")
```

##### Combining with array
If you want to combine a type with array, use it outside the array brackets to avoid confusion with array elements type.

Eg:

- Array of strings or string
    ```javascript
    "['names']"
    ```
- Array of strings or number
    ```javascript
    %['names']
    ```

### Default Value
Mention the variable default value, if it has one, next to its name in description between dashes `--`.

Eg:
```javascript
getUsers(?onlyMen)
```
Gets users' list.
- ?onlyMen: -false- If set to true will get only male users.
