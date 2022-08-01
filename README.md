# managing_state_information_and_security
JavaScript_for _Web_Warriors_7thEdition_Hand_on_Project9-4

Do the following:
1. Use your code editor to open the project09-04_txt.html and project09-04_txt.js files from the js09 c
project04 folder. Enter your name and the date in the comment section of each file and save them as 
project09-04.html and project09-04.js, respectively.
2. Go to the project09-04.html file in your code editor. A script element linked to the library.js file has already 
been added to the page to provide the interface to the puzzle. Add another script element linked to the 
project09-04.js file to provide code for the cookie will you create. Defer the loading of that script file until the 
page finishes loading. Review the contents of the file and then save your changes.
3. Go to the project09-04.js file in your code editor. Within the anonymous function for the event listener of the 
browser window’s load event, add the following code:
a. Insert an if statement testing whether the document.cookie object exists for this page.
b. If the if statement is true, change the text content of the bestText object to the text string “best
seconds” where best is the value returned by the getBestTime() function.
4. Create the getBestTime() function. The purpose of this function is to retrieve the user’s current best time to 
solve the sliding block puzzle. Add the following code to the function:
a. If the document.cookie object exists then i) Declare the cookieArray variable containing the text of the 
document cookie split at the occurrence of the "=" character. ii) Convert the cookie value to an integer by 
applying the parseInt() function to the value of cookieArray[1] and return it from the function.
b. If the document.cookie object does not exist, return a value of 9999.
5. Create the updateRecord() function. The purpose of this function is to replace the user’s best time with the 
time of their recent attempt if that attempt was better. Add the following commands to the function:
a. Declare the solutionTime variable, storing within it value of the document element with the id “timer”. 
Apply the parseInt() function to that value to convert it from a text string to an integer.
b. Call the getBestTime() function and store the returned value in the bestTime variable.
c. If solutionTime is less than bestTime then let bestTime equal solutionTime.
d. Change the text content of the bestText object to “best seconds” where best is the value of the 
bestTime variable.
e. Write the following text string to the document.cookie object, setting the max age of the cookie to 90 
days:
puzzle8Best=best
where best is the value of the bestTime variable.
6. Save your changes to the file and then load all the web page files for this project to a folder on your web server.
7. Start your server software if necessary, and then use your browser to open the project09-04.html from the 
folder on your server. Verify the following:
a. When you initially open the page, the page footer should display the message “Your best time is not yet 
recorded”.
b. Click the Start button and begin sliding the block pieces by clicking blocks adjacent to the open square. 
The timer will automatically stop when the blocks are in the correct order. Verify that the footer shows the 
updated best time.
c. Close the web page and your browser. Verify that when you reopened the web page in your browser the 
updated best time is displayed in the page footer.
d. Attempt to solve the puzzle several times, verifying that the page always shows the best time from all your 
attempts.
e. If you need to retest the web page, delete the puzzle8Best cookie using the tools in your browser



Hint:

/* Page Objects */
let bestText = ...
let clockTimer = ...

// Custom event that runs when the puzzle is solved
window.addEventListener...

// Event listener that is run when the page loads
window.addEventListener(... {
if ... {
...
}
});


function getBestTime() {
if (document.cookie) {
...
...
} else {
...
}
}

function updateRecord() {
let solutionTime = ...
let bestTime = ...
if ... {
...
}

bestText.textContent = ...
document.cookie = "puzzle8Best=" + bestTime + "; max-age=" + 60*60*24*90;
}
