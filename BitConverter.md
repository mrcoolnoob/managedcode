Yes, the `BitConverter` class is available in C++/CLI. It’s part of the .NET Framework, which C++/CLI is built on. [This class contains methods that convert base data types to an array of bytes, and an array of bytes to base data types](https://learn.microsoft.com/en-us/dotnet/api/system.bitconverter?view=net-7.0)[1](https://learn.microsoft.com/en-us/dotnet/api/system.bitconverter?view=net-7.0). Here’s how you can use it:

```cpp
double value = 1234.56;
array<Byte>^ bytes = BitConverter::GetBytes(value);
double result = BitConverter::ToDouble(bytes, 0);
```

In this code, `BitConverter::GetBytes` converts a `double` into an array of bytes, and `BitConverter::ToDouble` converts an array of bytes back into a `double`. [The second argument to `ToDouble` is the start index in the array](https://learn.microsoft.com/en-us/dotnet/api/system.bitconverter?view=net-7.0)[1](https://learn.microsoft.com/en-us/dotnet/api/system.bitconverter?view=net-7.0).

Please note that this code assumes that the bytes in the array are in the same endianness as the system. If you’re communicating between different systems, you might need to reverse the array.

I hope this helps! Let me know if you have any other questions. 
