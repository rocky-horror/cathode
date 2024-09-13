# Cathode Standard Library Documentation

## Namespace "core"

*	The core namespace is included automatically in every context. It contains the essential functions of the language, along with the ability to import more namespaces

### Functions

#### RandomBytes(length)

*	Arguments: length (integer)
*	Returns: array
*	Description: Returns a pseudorandom array of bytes with the given length
	
#### BytesToStr(bytes, encoding)

*	Arguments: bytes (array), encoding (string)
*	Returns: string, void
*	Description: Converts the given binary data to a string with the given encoding and returns the resulting string. Encoding value must be "ascii", "unicode", or "utf8". This function will return void if unsuccessful
	
#### StrToBytes(str, encoding)

*	Arguments: str (string), encoding (string)
*	Returns: array, void
*	Description: Converts the given string to a byte array with the given encoding and returns the resulting array. Encoding value must be "ascii", "unicode", or "utf8". This function will return void if unsuccessful
	
#### Arraylen(arr)

*	Arguments: arr (array)
*	Returns: integer
*	Description: Returns the length of the given array
	
#### Strlen(str)

*	Arguments: str (string)
*	Returns: integer
*	Description: Returns the length of the given string
	
#### Format(str, objs)

*	Arguments: str (string), objs (array)
*	Returns: string
*	Description: Fills a formatted string of the format "Item 0: $0, Item 1: $1, [etc...]" with the objects supplied and returns the result. If a variable number in the string does not correspond to an array element, it will be left unchanged

#### Strcat(arr, separator)

*	Arguments: arr (array), separator (string or void)
*	Returns: string
*	Description: Concatenates the strings in the array with each other and returns the result. The separator parameter can be used for its nominal purpose or will be ignored if void is passed
	
#### HasField(strct, name)

*	Arguments: strct (struct), name (string)
*	Returns: integer
*	Description: Checks if the supplied struct has a field of the given name. A nonzero value is returned if the field is present, and zero is returned if it is not
	
#### Field(strct, name)

*	Arguments: strct (struct), name (string)
*	Returns: anything
*	Description: Returns the value of a given struct's field of the given name
	
#### SetField(strct, name, obj)

*	Arguments: strct (struct), name (string), obj (anything)
*	Returns: void
*	Description: Sets the value of a given struct's field of the given name
	
#### Struct()

*	Arguments: None
*	Returns: struct
*	Description: Returns a new empty struct
	
#### Assert(test, failureMsg)

*	Arguments: test (integer), failureMsg (string)
*	Returns: void
*	Description: Ends the program with an error message if the logical test test fails
	
#### Except(msg)

*	Arguments: msg (string)
*	Returns: void
*	Description: Ends the program with the supplied error message
	
#### Negate(value)

*	Arguments: value (integer)
*	Returns: integer
*	Description: Negates the given logical value and returns the result
	
#### Both(first, second)

*	Arguments: first (integer), second (integer)
*	Returns: integer
*	Description: Returns a nonzero value if both arguments are nonzero. Otherwise, zero is returned
	
#### Either(first, second)

*	Arguments: first (integer), second (integer)
*	Returns: integer
*	Description: Returns a nonzero value if either argument is nonzero. Otherwise, zero is returned
	
#### LessThan(first, second)

*	Arguments: first (integer, float, or byte), second (integer, float, or byte)
*	Returns: integer
*	Description: Returns a nonzero value if the first argument is less than the second. Otherwise, zero is returned
	
#### GreaterThan(first, second)

*	Arguments: first (integer, float, or byte), second (integer, float, or byte)
*	Returns: integer
*	Description: Returns a nonzero value if the first argument is greater than the second. Otherwise, zero is returned
	
#### Equal(first, second)

*	Arguments: first (anything), second (anything)
*	Returns: integer
*	Description: Returns a nonzero value if the arguments are equal. Otherwise, zero is returned
	
#### NotEqual(first, second)

*	Arguments: first (anything), second (anything)
*	Returns: integer
*	Description: Returns the negated result of Equal(first, second)
	
#### Exit(code)

*	Arguments: code (integer)
*	Returns: does not return
*	Description: Immediately exits the program with the given code
	
#### Byte(obj)

*	Arguments: obj (any)
*	Returns: byte, void
*	Description: Converts the supplied object to a byte and returns the result. If conversion is impossible, void is returned
*	Additional notes: Conversion is defined for the following types: integer, float, byte, filehandle, and alphanumeric string
	
#### Integer(obj)

*	Arguments: obj (any)
*	Returns: integer, void
*	Description: Converts the supplied object to an integer and returns the result. If conversion is impossible, void is returned
*	Additional notes: Conversion is defined for the following types: integer, float, byte, filehandle, and alphanumeric string

#### String(obj)

*	Arguments: obj (any)
*	Returns: string
*	Description: Converts the supplied object a string and returns the result
	
#### Float(obj)

*	Arguments: obj (any)
*	Returns: float, void
*	Description: Converts the supplied object to a float and returns the result. If conversion is impossible, void is returned
*	Additional notes: Conversion is defined for the following types: integer, float, byte, and alphanumeric string
	
#### Strcmp(str1, str2)

*	Arguments: str1 (string), str2 (string)
*	Returns: integer
*	Description: Compared the two supplied strings and returns zero if they are equal. Otherwise, a nonzero value is returned
*	Additional notes: Be careful using this function in comparisons since it follows the opposite pattern of normal comparison. Remember to compare the result to zero