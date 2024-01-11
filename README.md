Doa Ahmed CS 067
LAB 10
1. What test command should be used to test that /usr/bin is a directory or a file?
#!/bin/bash
if [ -d /usr/bin ]; then
echo "/usr/bin is a
directory"else
echo "/usr/bin is not a directory"
fi
2. Write a script that takes two strings as input comparesthem and depending upon the
results of the comparison prints the results.
#!/bin/bash
echo "Enter the first string: 
"read string1
echo "Enter the second string: 
"read string2
if [ "$string1" == "$string2" ]; then
echo "The strings are equal"
else
echo "The strings are not equal"
fi
3. Write a script that takes a number (parameter) from 1-3 as input and uses case to
display the name of corresponding month.
#!/bin/bash
echo "Enter a number from 1 to 3: 
"read number
case $number 
in1)
2)
3)
*)
esac
echo "January"
;;
echo "February"
;;
echo "March"
;;
echo "Invalid input"
;;
4. Write a script that calculates the average of all even numbers less than or equal to
your roll number and prints the result.
Doa Ahmed CS 067
#!/bin/bash
roll_number=9
count=0
 for ((i=2; i<=$roll_number; i+=2)); do sum=$((sum + i))
 count=$((count + 1)) done
 average=$((sum / count))
 echo "The average of even numbers up to your roll number is:$average"
5. Write a function that displays the name of the week days starting from Sunday if the
user passes a day number. If a number provided is not between 1 and 7 an error message
is displayed.
#!/bin/bash
function displayWeekday() {
dayNum=$1
if ((dayNum >= 1 && dayNum <= 7)); thencase
$dayNum in
1)
2)
3)
4)
5)
6)
7)
esac
else
echo "Sunday"
;;
echo "Monday"
;;
echo "Tuesday"
;;
echo "Wednesday"
;;
echo "Thursday"
;;
echo "Friday"
;;
echo "Saturday"
;;
echo "Error: Invalid day number. Please enter a number between 1 and 7."
fi
}
Doa Ahmed CS 067
echo "Enter a number from 1 to 7: 
"read userInput
displayWeekday $userInput
6.Write scripts that displays the parameters passed along with the parameter number 
using while and until statements.
Using while
#!/bin/bash 
count=1
while [ $# -gt 0 ]; do
echo "Parameter $count: $1" 
count=$((count + 1))
shift
done
Using until
#!/bin/bash 
count=1
until [ $# -eq 0 ]; do
echo "Parameter $count: $1"
count=$((count + 1))
shift
done
7.Write a script that displays the following menu:
Quotient 
Remainder Depending on user’s choice, the result of division must be displayed and the loop breaks. 
The two numbers (dividend and divisor) must be supplied at runtime as command line arguments. If 
user chooses an item that is not in the list, he must be prompted to make proper choice and the loop 
must restart (or continue)
#!/bin/bash calculate_quotient() {
dividend=$1 
divisor=$2
quotient=$((dividend / divisor))
echo "The quotient of $dividend divided by $divisor is: $quotient"
}
calculate_remainder() { 
dividend=$1 
divisor=$2
remainder=$((dividend % divisor))
echo "The remainder of $dividend divided by $divisor is: $remainder"
} while true; do 
echo "Menu:"
echo "1. Quotient"
echo "2. Remainder" 
echo "3. Quit" 
read -p "Enter your choice (1-3): " choice 
case $choice in
Doa Ahmed CS 067
1)
if [ $# -lt 2 ]; then
echo "Insufficient arguments. Please provide dividend and
divisor."continue
fi
dividend=$1
divisor=$2
calculate_quotient $dividend 
$divisorbreak
;;
2)
if [ $# -lt 2]; then
echo "Insufficient arguments. Please provide dividend and 
divisor."continue
3)
*)
esac
done
fi
dividend=$1
divisor=$2
calculate_remainder $dividend
$divisorbreak
;;
break
;;
echo "Invalid choice. Please enter a number from 1 to 3."
;;
Doa Ahmed CS 067
