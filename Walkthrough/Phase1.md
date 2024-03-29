Note: Use Bomb.i64 as a reference and Bomb1.i64 as the solution for this phase.

It is seen that the function sub_401870 is called repeatedly. Inspecting this function, IDA shows that most of the output
comments are regarding input validation. This makes sense as this function is called repeatedly after every input. Hence, we
can rename this function as input_validator.

The next unknown function is sub_401190. Inspecting this function, we see 2 unknown functions, sub_401740 and sub_401960.

The function sub_401960 is clearly the function that prints the failure string, hence we can rename it as bomb_explode.

The function sub_401740 calls another unknown function sub_401700, which on inspection clearly returns the length of a
string. Hence sub_401700 can be renamed as string_length. 

Using this to understand sub_401740, it is clear that this function compares two input strings and returns 0 only if the
two strings are equal. Hence we can rename this as string_compare.

Using this to understand sub_401190, this function compares the user input string to ``` Public speaking is very easy ```
and returns true only if they are equal. Hence, we have the first password, ``` Public speaking is very easy ```.

The function sub_401190 can be renamed as Phase1.


