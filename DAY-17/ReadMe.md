Day 17: JavaScript for...of Loop & String IterationToday's focus is on understanding the for...of loop in JavaScript—a modern, clean, and readable way to iterate over iterable objects like Strings, Arrays, Sets, Maps, and more.Key Conceptsfor...of Loop: Introduced in ES6, it automatically loops over values directly without requiring index tracking (like i = 0; i < len; i++).String Iteration: Since strings are iterable sequences of characters, for...of visits every individual character one by one, including spaces.Early Exit with Control Statements: You can use break or continue inside a for...of loop just like in a traditional for loop.Code Breakdown & Explanations1. Traditional for Loop (Index-Based)JavaScriptlet n = "code step by step";

for (let i = 0; i < n.length; i++) {
    console.log(n[i]);
}
How it works: Uses an explicit index variable i. It checks n.length and accesses characters via square bracket notation n[i].Output: Logs each character of "code step by step" on a new line (including spaces).2. Basic for...of Loop (Value-Based)JavaScriptlet n = "code step by step";

for (let char of n) {
    console.log(char);
}
How it works: Instead of managing an index i, JavaScript directly assigns each character of string n to the variable char in each iteration.Output: Produces the exact same output as the traditional loop, but with much cleaner syntax.3. Active Code: for...of Loop with breakJavaScriptlet n = "code step by step";

for (let char of n) {
    if (char == "b") {
        break; // Stops execution when it encounters the letter 'b'
    }
    console.log(char);
}
How it works:The loop starts reading characters from "code step by step".It prints c, o, d, e,  , s, t, e, p,  , a.When it reaches b (in "by"), char == "b" becomes true.break triggers and terminates the loop immediately.Console Output:Plaintextc
o
d
e

s
t
e
p

a
Comparison: Traditional for vs for...of LoopFeatureTraditional for Loopfor...of LoopSyntaxComplex / VerboseSimple / CleanUses Index✅ Yes (i, j, etc.)❌ NoReturnsIndex-based values (arr[i])Direct values (item)Best ForComplex logic, index manipulation, or custom increments (e.g., i += 2)Simple iteration over all elements/charactersPractical TakeawayUse for...of when you just need to access every item in a collection (array, string, etc.) without worrying about index numbers.Use a traditional for loop when you explicitly need index position or need to jump by custom step sizes.