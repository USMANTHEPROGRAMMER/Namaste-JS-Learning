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

Now We'll Start Episode 4 (How functions work in JS & Variable Environment ):
Hum Logon ne is Episode main ye seekha ke Function kaise Work krte hain.
hum logon ne yeh Code likha hai:
var x = 1;
a()
b()
console.log(x)

function (a) {
    var x = 10;
    console.log(x)
}

function (b) {
    var x = 100;
    console.log(x);
}

ab hum yeh dekhte hain ke BG main yeh Code kaise work krrha hota hai:
Sabse pehle to ek ek GEC(Global Execution Context) banta hai:
jahan code run hota hai and us GEC main 2 Phases main kam hota hai sabse pehle:
1. Memory Creation Phase
2. Code Execution Phase

Memory Creation Phase

Sabse pehle GEC ki memory mein:
- x → undefined
- a → poora function store hoga.
- b → poora function store hoga.

Code Execution Phase

1. var x = 1 execute hoga, toh x = 1.
2. a() call hoga, toh naya FEC banega. Usmein local x = 10 hoga aur 10 print hoga.
3. a() complete hoga, toh uska FEC remove ho jayega.
4. b() call hoga, toh naya FEC banega. Usmein local x = 100 hoga aur 100 print hoga.
5. b() complete hoga, toh uska FEC bhi remove ho jayega.
6. Aakhir mein console.log(x) global x ki value 1 print karega.

Final Output:

10
100
1

Yaad rakho: a() aur b() ke andar apna local x hai, isliye global x = 1 change nahi hota aur nahi Console hota hai.

Now We'll Start Learning Episode 5:
Shortest JS Program

sabse pehle yeh Code dekho:
// Empty JavaScript File
Ismein kuch bhi nahi likha. Lekin jab browser is file ko run karta hai tab bhi JavaScript kaafi kaam karti hai.
jaisa ke humne pehle prha tha ke sabse pehle GEC banta hai.
Us Waqt Browser main humen 2 cheezen Free main deta hai.
window object 
this keyword
1. Window Object: Browser ka global object. Browser bohot saari cheezen iske andar rakhta hai.
2. this: Global level par browser mein this isi window ko point karta hai.

Window Browser ka Global Object hai
Browser bht saari cheezen iske andar rkhta hai.
console.log(window);
Iske andar tumhe bohot saari cheezen milengi:
- alert
- setTimeout
- console
- document
- location
- history
Yaani ye sab browser humein window ke through deta hai.

Step 3: this keyword kya hai?
Global level par browser mein:
console.log(this);
Output:
Window {...}

Aur agar likho:
console.log(this === window);

Output:
true

Matlab: Browser ke global scope mein this aur window same object ko refer karte hain.

this humara ek alag and seperate concept hai Global Level par to this Global Object ko Target krta hai lekin functions main iska case different hota hai jo ke hum baad main seekhenge.

Step 4: var aur window
Ye bohot important interview point hai.
var a = 10;
console.log(window.a);
console.log(this.a);

Output:
10
10

Kyun?

Kyuki global var browser ke window object ki property ban jaata hai.

Step 5: let aur const ke saath
let b = 20;
const c = 30;

console.log(window.b);
console.log(window.c);

Output:
undefined
undefined

Kyun?

Kyuki let aur const global hone ke baad bhi window ki property nahi bante.


jab bhi hum kisi cheez ko access krte hain to wo Global Object main Check krta hai like jo cheez hum Global likh rhe hain and then hum ko Output Return krta hai.

let aur const ke saath
let b = 20;
const c = 30;

console.log(window.b);
console.log(window.c);

Output:
undefined
undefined

Kyun?

Kyuki let aur const global hone ke baad bhi window ki property nahi bante.

Now We'll Start Episode 6:
Undefined vs Not Defined:
undefined kya hota hai?
Jab variable declare ho chuka ho, lekin usko abhi value assign na hui ho, toh uski value undefined ho sakti hai.
var a;

console.log(a);

Output:
undefined

Kyun? Variable a exist karta hai, lekin usko value assign nahi ki.

not defined kya hota hai?
Jab hum aise variable ko access karte hain jo exist hi nahi karta, toh JavaScript ReferenceError deti hai.
console.log(b);


Output:
ReferenceError: b is not defined


Kyun? Humne b naam ka variable declare hi nahi kiya.

Simple Meaning:
Undefined: Variable declared hai, lekin uski value abhi assign nahi hui.
Not defined: Variable ko declare hi nahi kiya gaya, isliye access karne par ReferenceError aata hai.

Now We'll Start Episode 7 The Scope Chain Scope, Lexical Environment:
sabse pehle hum yeh Code Dekhte hain:
function a() {
    onsole.log(b);
};
var b = 10;
a()
iska Output aayega 10
This is How it proves ke b can access outside of its Function
ab hum log yeh wala Code dekhte hain like nuhh:
function a() {
    c()
    function c() {
        console.log(b)
    }
}
var b = 10;
a()
Iska bhi Output Aayega 10
that means ke if function inside in another function can still access the Global Scope Variables

function a() {
    var b = 10;
    c()
    function c() {

    }
}
a()
console.log(b);
so is ka Output Aayega humare paas Not Defined there is a thing where er invent something which is Called Scope:
So Scope Means ke Variable ya function ko hum apne Code main kahan Access krskte hain!
Example:
var a = 10;

function greet() {
    var b = 20;
    console.log(a);
    console.log(b);
}

greet();

10
20
a global variable hai, isliye function ke andar access ho raha hai.
b function ke andar declare hua hai, isliye woh us function ke andar accessible hai.

Another Example:
function greet() {
    var b = 20;
}

console.log(b);

Output: ReferenceError
Kyun? Kyunki b sirf greet() ke scope mein available hai.

Now ab hum dekhte hain ke Lexical Environment kia hota hai:
Lexical Enviroment hota hai ke Local Memory ka Access bhi hota hai and Lexical Enviroment of the Parent ka bhi Access hota hai.

Simple Words main hum ise yeh bhi kehskte hain:
Lexical Environment woh environment hai jisme JavaScript apne variables aur outer environment ka reference rakhti hai.

ab hum ek dafa Visually smjhlete hain Example se like ke:
jab bhi Execution Context Create hota hai so hum ko ek Reference bhi milta hai or its Lexical Environment of its Parent
So Memory Component main Variables or Functions ke ilawa humen ek Orange Thing bhi milti hai jise hum Assume krskte hain ke yeh Lexical Environment hai of its Parent.
Like this:
function a(){
    var b = 10;
    c();
    function c() {

    }
}
a();
console.log(b)
ab jaise humare paas c Function hai to Lexical Environment ka matlab hota hai ke use apne Variables ka bhi Access milega and Lexical Environment of the Parent ka bhi Access hota hai means function a ke bhi variables and functions ka access hota hai. and the a function ka Lexical Enviroment hai uska Local Memory Space and its Parent As Well Which is Global Scope

and Global Space ke Case main Lexical Parent hoga null kyun ke uska koi Parent nahii but usko Global Scope ki har cheez k Access milega but kyun ke uska koi Lexical Parent nahi hai this is why wo null dega.

Easy example:
var a = 10;

function outer() {
    var b = 20;

    function inner() {
        var c = 30;
        console.log(a, b, c);
    }

    inner();
}

outer();

inner() ke paas apna variable c hai. Lekin woh apne parent function outer() ka b aur global scope ka a bhi access kar sakta hai.

Aisa kyun?

Kyunki JavaScript ka har function apne surrounding (jahan function likha gaya hai) environment se connected hota hai. Is connection ko Lexical Environment kehte hain.

Now We'll See Scope Chain:
Scope Chain woh process hai jisme JavaScript kisi variable ko apne current scope mein dhoondhti hai. Agar nahi milta, toh outer scope mein dhoondhti hai.

Teeno ka difference
Concept	                    Simple meaning
Scope	                    Variable kahan accessible hai?
Lexical Environment	        Variables aur outer environment ka reference
Scope Chain	                Variable ko current se outer scopes tak search karna

