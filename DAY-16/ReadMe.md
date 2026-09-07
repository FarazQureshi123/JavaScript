Day 16: JavaScript Loop Control Statements (break & continue)Today's focus is on mastering control flow inside JavaScript loops using the break and continue statements. These keywords allow you to alter the standard execution flow of loops based on specific conditions.Key Conceptsbreak: Immediately exits the loop, jumping straight to any code after the loop block.continue: Skips the rest of the current iteration and jumps directly to the next cycle of the loop.Code Breakdown & Explanations1. 


Stopping a Loop Early (for loop + break)JavaScriptfor (let i = 0; i < 20; i++) {
    console.log(i);
    if (i == 11) {
        break; // Stops the loop entirely when i reaches 11
    }
}
How it works: The loop is set to run from 0 to 19. However, as soon as i hits 11, the break statement runs and cancels the loop immediately.Output: Numbers 0 through 11 printed in the console.2. Skipping a Single Iteration (for loop + continue)JavaScriptfor (let i = 0; i <= 10; i++) {
    if (i == 4) {
        continue; // Skips printing 4 and moves to i = 5
    }
    console.log(i);
}
How it works: The loop runs from 0 to 10. When i is 4, the continue statement skips console.log(i) and jumps straight to incrementing i for the next cycle.Output: Numbers 0, 1, 2, 3, 5, 6, 7, 8, 9, 10 (Notice 4 is missing).3. Combining Control Statements in a while LoopJavaScriptlet i = 0;
while (i < 10) {
    i++;
    if (i == 3) {
        continue; // Skips 3
    }
    if (i == 8) {
        break; // Stops when i reaches 8
    }
    console.log(i);
}
How it works:i increments before logging.When i becomes 3, continue skips logging.When i becomes 8, break exits the loop before logging 8.Output: Numbers 1, 2, 4, 5, 6, 7.4. Active Code: Control Statements in a do...while LoopJavaScriptlet i = 0;
do {
    i++;
    if (i == 3) {
        continue; // Skips 3
    }
    if (i == 8) {
        break; // Exits the loop
    }
    console.log(i);
} while (i < 10);

How it works: A do...while loop always runs its code block at least once before checking the condition. Here, it increments i, skips logging when i is 3, and terminates as soon as i equals 8.Output: Numbers 1, 2, 4, 5, 6, 7.Summary MatrixStatementPrimary PurposeLoop BehaviorbreakTerminate loop executionAborts the entire loop immediatelycontinueSkip current stepJumps to the start of the next iteration