1. What did you predict for Warmup.java, and what did it actually print? Explain the lines that surprised you.

My predicted output was:
7 5.0 127
"Two" "Three"


The actual output was:
7 5.0 -126
"Two" "Three"


I predicted that byte casting would truncate the bits and produce the highest value within the byte range. However, the actual result was -126 because Java's byte is a signed 8-bit data type. When the value exceeds its maximum range of 127, it wraps around and is interpreted as a negative number.

2. What is the difference between the static variable totalProducts and the instance variable name?

A static variable belongs to the class rather than an individual object, and it can be accessed using the class name. Any changes made to it are shared across all objects of that class.

An instance variable belongs to an individual object. Each object maintains its own separate copy, so changes made to one object's instance variable do not affect other objects.

3. What does the copy constructor do, and why does changing p2.name not change p1.name?

A copy constructor takes an existing object as an argument and copies its field values into a newly created object. This creates a separate object with its own instance variables.

Changing p2.name does not affect p1.name because name is an instance variable, and both objects maintain their own separate copies of it.

4. Why does Java force you to write (int) average when converting a double to an int, and what happens to the decimal part?

We use (int) for explicit type casting, especially when converting a larger data type to a smaller one, such as double to int. Java requires this because there is a possibility of losing data during the conversion.

The decimal part is truncated (removed), not rounded off. For example, converting 5.9 to int results in 5.