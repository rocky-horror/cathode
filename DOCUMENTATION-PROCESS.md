# Cathode Standard Library Documentation

## Namespace "process"

### Functions

#### ProcessName(pid)

*	Arguments: pid (integer)
*	Returns: string, void
*	Description: Attempts to determine the process name from the supplied process id. If this is impossible, void is returned

#### pKill(pid)

*	Arguments: pid (integer)
*	Returns: integer
*	Description: Attempts to kill a process and returns 1 if successful. Otherwise, 0 is returned

#### pGetModuleBase(pid, moduleName)

*	Arguments: pid (integer), moduleName (string, void)
*	Returns: integer
*	Description: Attempts to find the module base of a specified module within the process whose id is supplied. If moduleName is void, the function assumes you are requesting the main module of the process. If the function is successful, the base of the given module is returned. Otherwise, zero is returned

#### EnumProcesses()

*	Arguments: none
*	Returns: array
*	Description: Enumerates all processes on the system and returns them as an array of process ids. If enumeration is impossible, an empty array is returned

#### EnableDebug()

*	Arguments: none
*	Returns: integer
*	Description: Attempts to enable SeDebugPrivilege for the current process and returns 1 if successful. Otherwise, 0 is returned

#### pOpen(processId, perms)

*	Arguments: processId (integer), perms (string)
*	Returns: integer
*	Description: Attempts to open a process with the given perms ("r", "w", or "rw) and process id, and returns the handle index if successful. Otherwise, -1 is returned
*	Additional notes: Be wary when writing your error checking; this function *can* return zero from a successful call

#### pRead(handleIdx, base, offs, count)

*	Arguments: handleIdx (integer), base (longpointer), offs (integer), count (integer)
*	Returns: array
*	Description: Attempts to read the given count of bytes from the process with the given handle at base+offs and returns the read section as a byte array if successful. Otherwise, void is returned

#### pWrite(handleIdx, base, offs, byteArr)

*	Arguments: handleIdx (integer), base (longpointer), offs (integer), byteArr (array)
*	Returns: integer
*	Description: Attempts to write the given count of bytes to the process with the given handle at offset base+offs and returns 1 if successful. Otherwise, 0 is returned

#### pClose(handleIdx)

*	Arguments: handleIdx (integer)
*	Returns: void
*	Description: Closes the process handle from the supplied index