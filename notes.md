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
Humne kabhi socha hoga ke JS Execute kaise hoti hai hum waise pehle bhi baat krchuke hain ke JS humari Execution Context ke andar Run hoti hai.
var n = 2
function square(num) {
let ans = num \* num
return ans;
}
var square2 = square(n);
var square4 = square(4);
yeh humara ek chota sa Program hai JS ka:
Now ab hum Smjhenge he How this Entire Code is Run yaani iske Behind the Scenes:
jab hum is Code ko Run krte hain to ek Global Execution Context Create hota hai its like a Big Box and it has Two Components these Two Components are the Memory Component and the Code Component. Now The Important Thing is this Execution Context is Created in Two Phases the First Phase is known as the Creation or Memory Creation Phase and the Second Phase is Code Execution Phase.
Memory Component Code Component
n: undefined
square: (Whole Code of the Function)
square2: undefined
square3: undefined

and then in Second Phase:
Memory Component Code Component
n: 2
square: (Whole Code of the Function)
square2: undefined
square3: undefined

ek Cheez hai ke jab JS apna Program krleti hai to Execution Context Delete hojata hai ab wo Global Context ho ya Function Context!
or Function main Return ka matlanb hota hai ke jahan Function Invoke hua ho wahan wapis chle jaoo!

Now ab hum Call Stack ko Smjhenge:
Call Stack ek aisi jagah hai jahan JavaScript Engine Execution Contexts ko manage karti hai. And yeh LIFO(Last in First Out) Follow krta hai.
Call Stack mein aisa hi hota hai: jo function call sabse last mein aata hai, uska execution complete hone par woh sabse pehle stack se remove hota hai.
ab isko Zara Code se smjhlete hain:
var a = 10;

function greet() {
console.log("Hello");
}

greet();
Jab JavaScript program start hota hai, toh Global Execution Context (GEC) create hokar Call Stack mein push hota hai.
Ab jab JavaScript greet() par pohanchti hai, toh function ka Execution Context create hokar Call Stack mein push hota hai.

Current CallStack:
greet() — Function Execution Context
Top of stack

Global Execution Context
Function ka context sabse upar hai, isliye pehle ye execute hoga.

Function console.log("Hello") execute karega. Jab greet() ka kaam complete ho jaata hai, uska Execution Context stack se pop ho jaata hai.
Execution Context vs Call Stack
Execution Context Call Stack
Code execute karne ka environment Execution Contexts ko manage karta hai
Memory aur execution setup hota hai Contexts push aur pop hote hain
Function call par naya context banta hai Naya context stack ke top par aata hai
Yaad rakhna: Execution Context batata hai code kahan execute ho raha hai, aur Call Stack manage karta hai ke kaunsa context abhi execute ho raha hai.
Call Stack ka Core Concept hai:
CallStack Maintains the Order of Execution of Execution Contexts.

Now We'll Start Episode 3:
Hoisting in JS:
Hoisting JavaScript ka behaviour hai jahan code execute hone se pehle variables aur functions ki declarations process hoti hain.

Var ke saath:
console.log(a);
var a = 10;
console.log(a);

Output:
undefined
10

ab sawaal hai ke a ki ki val 10 hone ke Bawajood bhi undefined kyun aya.
is Cheez ko jawab hai na humen Execution Context se pata chalega
Sabse pehle humen yeh Smjhna parega ke JS Code ko Kaise Execute krti hai:
Jab JS Code ko Exercute krti hai, toh Execution Context main 2 Phases hote hain:

1. Memory Creation: JavaScript variables ke liye memory banati hai. var ke case mein shuru mein value undefined hoti hai.
2. Code Execution: JavaScript code ko line by line execute karti hai aur actual values assign karti hai.

ab isi Example ko dekhte hain:
console.log(a);
var a = 10;
Step 1:
Memory Creation Phase:
JS a ke liye Memory Banati hai.
a = undefined

Step 2:
Code Execution Phase:
console.log(a); // undefined
kyun ke abhi a = 10 wali Line Execute nahi hoti hai.
phir yeh wali Line Execute hoti hai:
var a = 10
then a ki Val 10 Assign hojaati hai.

Hoisting Easy definition:

Hoisting JavaScript ka behaviour hai jahan code execute hone se pehle variables aur functions ki declarations ko Execution Context ke creation phase mein handle kiya jata hai.

ab Function main Hoisting ko smjhte hain:
yeh Code dekho:
greet();

function greet() {
    console.log("Hello!");
}

Output:
Hello!
Tum sochoge: “Lekin humne greet() ko function banane se pehle call kar diya!”

aisa isliye hua ke Memory Creation Phase main key ka name fn ka name hota hai and key main poora function store hote hain or jab humen isko invoke krte hain to yeh Work krjata hai bas yehi reason hai.

hum log ab Arrow Function ko bhi dekhlete hain

Arrow Function main nuhh Case thora different hota hai 

greet();
var greet = () => {
    console.log("Hello!");
};
is main hum ko Type Error ka Error Return krdega.
kyun ke Memory Creation Phase main ek Function nahi balke ek variable store horha hai or uski Value Undefined hai
now ab hum sochenge ke unefined ana chahye Type Error kyun arha hai baat to sahi hai lekin hum log kia krrhe hain ke memory creation phase main a ki value undefined hoti hai correct soo hum yeh krne ki koshish krrhe hain "unefined()" isliye hum ko Type Error ka Error Throw krrha hai.

Toh undefined aur TypeError mein difference kya hai?
Case 1: Value print karna
console.log(greet);
Output: undefined

Hum sirf value dekh rahe hain.

Case 2: Function ki tarah call karna
greet();
Output: TypeError

Hum undefined ko function ki tarah call kar rahe hain, jo possible nahi hai.

Akshay Sir ne isi Episode main Demo of CallStack in the Browser bhi prhaya hai.
