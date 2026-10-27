Today We Are Starting Learning Namaste JS - 27TH OCT 2026

Sabse pehle hum log smjhenge ke How JS Works ?
Sabse pehle hum log ek chez clear krlete hain ke jo bhi Cheez JS main hoti hai wo Execution Context ke andar hoti hai. Asal main kia hota hai ke JS jab bhi Code Run krta hai to wo ek Environment banata hai usi Enviroment ko hum Execution Context kehte hain.
hum log For Now ke liye Suppose krlete hain ke Execution context is lika a Box jiske andar poori JS Execute hoti hai.
Simple words mein:
Execution Context = Woh environment jahan JavaScript code execute hota hai.

Is environment ko samajhne ke liye 2 cheezein yaad rakho:
ab hum log Execution Context ke baare main thora prh lete hain ke:
Execution Context is Like a Box Which Has Two Components in it:
1. Memory Component:
yeh wohi jagah hoti jahan functions aur variables store hote hain in key value pairs. its also known as Variable Enviroment. Like this:
a : 10
b : 20

2. Code Component (Thread of Execution):
Yahan JavaScript code ko line by line execute karti hai. or One Line at a Time Execute krti hai. its Also Knows as Thread of Execution.

The Most Imp Thing is:
JavaScript is a Synchronous is a Single Threaded Language.

yahan par jo main Single Threaded bolrha hoon so that means ke JS can Execute one Command at a Time.
and When I Say Synchronous Single Threaded that means JS Can Run one Command at a Time and in a Specific Order. So That Means JS Will go On Next Line when the Current Line Finish Executing.

Phase 1
Memory Creation Phase
- Variables ke liye memory prepare hoti hai.
- var variables ko initially undefined milta hai.
- Function declarations ki definition available hoti hai.

Phase 2
Code Execution Phase
- Code line by line execute hota hai.
- Assignments hoti hain.
- Expressions calculate hoti hain.
- Functions call hone par execute hote hain\

Now We'll Talk on How JS Code is Executed?
