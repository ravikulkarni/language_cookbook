# Language Cookbook

## 1. Language Basics
* [Variables](Basics/Basics_Variables.md#variables)
  * [Getting environment variables](Basics/Basics_Variables.md#getting-environment-variables)
  * [Setting environment variables](Basics/Basics_Variables.md#setting-environment-variables)
  * [Looping over arguments passed to a script](Basics/Basics_Variables.md#looping-over-arguments-passed-to-a-script)
  * [Counting total arguments](Basics/Basics_Variables.md#counting-total-arguments)
* [Operators](Basics/Basics_Operators.md)
* [Conditionals](Basics/Basics_Conditionals.md)
* [Loops](Basics/Basics_Loops.md)
* [Subroutines/Functions](Basics/Basics_SubRoutines.md)
   * [Accessing subroutine arguments](Basics/Basics_SubRoutines.md#accessing-subroutine-arguments)
   * [Making variables private in a function](Basics/Basics_SubRoutines.md#making-variables-private-in-a-function)
   * [Return information to caller](Basics/Basics_SubRoutines.md#return-information-to-caller)
   * [Error handling](Basics/Basics_SubRoutines.md#error-handling)

## 2. Working with Strings 
* [Accessing substrings](Strings/Strings_AccessingSubstrings.md)
* [Replacing Substrings](Strings/Strings_ReplacingSubstrings.md)
* [Converting Between Characters and Values](Strings/Strings_ConvertingBetweenCharsAndValues.md)
* [Processing String One Character At A Time](Strings/String_ProcessingOneCharAtTime.md)
* [Reverse String](Strings/String_ReverseString.md)
* [Converting Between Uppercase And Lowercase](Strings/String_ConvertingCase.md)
* [Trimming white spaces around the string](Strings/String_TrimmingBlanks.md)
* [Printing string with formatting control](Strings/String_PrintStringWithFormatting.md)
* [Sorting strings](Strings/String_SortingString.md)

## 3. Working with Numbers
* [Rounding floating point numbers](Numbers/Numbers_RoundingFPNumbers.md)
* [Comparing floating point numbers](Numbers/Numbers_ComparingFPNumbers.md)
* [Generating random numbers](Numbers/Numbers_GenerateRandomNumbers.md)
* [Making numbers even more random](Numbers/Numbers_EvenMoreRandomNumbers.md)
* [Converting binary, octal and hexadecimal](Numbers/Numbers_ConvertBinOctHex.md)
* [Sorting numbers](Numbers/Numbers_Sort.md)
* [Checking whether a string is a valid number](Numbers/Numbers_StringIsValidNumber.md)

## 4. Working with Arrays
* [Overall Array Support](Arrays/Arrays_SupportFunctions.md)
* [Defining/creating arrays](Arrays/Arrays_CreateArray.md)
* [Adding element to array](Arrays/Arrays_AddToArray.md)
* [Deleting element from array](Arrays/Arrays_DeleteFromArray.md)
* [Array iteration](Arrays/Arrays_IterateArray.md)
* [Iterating over array by reference](Arrays/Arrays_IterateArrayByReference.md)
* [Extracting unique elements from a list](Arrays/Arrays_ExtractUniqueElements.md)
* [Appending one array to another](Arrays/Arrays_AppendArrays.md)
* [Reversing array](Arrays/Arrays_Reverse.md)
* [Sorting array](Arrays/Arrays_Sort.md)

## 5. Working with Hash
* [Overall Hash Support](Hashes/Hashes_OverallHashSupport.md)
* [Defining/creating hash](Hashes/Hashes_Create.md)
* [Adding element to hash](Hashes/Hashes_AddElement.md)
* [Deleting element from hash](Hashes/Hashes_DeleteElement.md)
* [Iterating over hash](Hashes/Hashes_Iterate.md)
* [Testing for presence of key in hash](Hashes/Hashes_TestForKey.md)
* [Sorting hash](Hashes/Hashes_Sort.md)
* [Merging hash](Hashes/Hashes_Merge.md)
* [Inverting hash](Hashes/Hashes_Invert.md)

## 6. Working with Directories
* [Deleting a file](Directories/Directories_DeleteAFile.md)
* [Copying a file](Directories/Directories_CopyAFile.md)
* [Moving a file](Directories/Directories_MoveAFile.md)
* [Processing all files in a directory](Directories/Directories_ProcessingAllFiles.md)
* [Removing a directory and its contents](Directories/Directories_Remove.md)
* [Renaming a files](Directories/Directories_RenameFiles.md)
* [Finding files](Directories/Directories_FindFiles.md)
* [Finding current working directory](Directories/Directories_FindCWD.md)
* [Getting information about files.](Directories/Directories_FileInformation.md)
* [Listing hidden files in directory.](Directories/Directories_ListHiddenFiles.md)

## 7. Working with Files
* File Reading
* File Writing
* Searching for a string in a file
* Using Standard output handle
* Using Standard error handle
* Keeping files from accidental overwriting.
* Counting lines, words or characters in file
* Removing duplicate lines
* Locking a file
* Flushing output
* Doing a non blocking IO
* Finding number of unread bytes.
* Using random access IO

## 8. Working with Dates and Time
* [Getting default dates](DatesAndTime/DatesAndTime_GetDefaultDate.md)
* [Converting dates and times into epoch seconds](DatesAndTime/DatesAndTime_ConvertIntoEpoch.md)
* [Converting epoch seconds into dates and times](DatesAndTime/DatesAndTime_ConvertFromEpoch.md)
* [Date and Time arithmetic](DatesAndTime/DatesAndTime_DateTimeArithmetic.md)
* [Difference of two dates](DatesAndTime/DatesAndTime_DiffTwoDates.md)
* [Formatting dates](DatesAndTime/DatesAndTime_FormatDates.md)
* [Sleep](DatesAndTime/DatesAndTime_Sleep.md)

## 9. Working with System commands
* [Writing output to terminal window](Systems/System_WritingToTerminalWindow.md)
* [Reading input from terminal window](Systems/System_GetInputFromTerminalWindow.md)
* [Getting input from a file](Systems/System_GetInputFromFile.md)
* [Writing output to a file](Systems/System_WriteOutputToFile.md)
* [Executing/Running any command](Systems/System_ExecuteAnyCommand.md)
* [Telling if command succeeded or not](Systems/System_TestIfCommandSucceeded.md)
* [Running several commands in Sequence](Systems/System_ExecuteSeveralCommandsInSequence.md)

## 10. Working with Network
* [Finding your own IP address](Network/Network_FindOwnIPAddress.md)
* [Finding your own name of the machine](Network/Network_FindingYourMachineName.md)
* [Implementing TCP client](Network/Network_TCPClient.md)
* [Implementing TCP server](Network/Network_TCPServer.md)
* [Implementing UDP client](Network/Network_UDPClient.md)
* [Implementing UDP server](Network/Network_UDPServer.md)
