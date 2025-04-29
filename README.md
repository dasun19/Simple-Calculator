# Simple-Calculator

#Explain the Javascript code

let input = document.getElementById('inputBox');
👉 Meaning:
Finds the HTML element with the ID inputBox (probably an <input> tag) and saves it into a variable called input.
(So now you can use input to change or get the text inside the box.)

javascript
Copy
Edit
let buttons = document.querySelectorAll('button');
👉 Meaning:
Finds all <button> elements on the page and saves them in a list (NodeList) called buttons.

javascript
Copy
Edit
let string = "";
👉 Meaning:
Creates an empty string (text) to keep track of what the user types by clicking buttons.

javascript
Copy
Edit
let arr = Array.from(buttons);
👉 Meaning:
Converts the list of buttons into a real array called arr, making it easier to use array functions like forEach.

javascript
Copy
Edit
arr.forEach(button => {
👉 Meaning:
For each button in the arr (one-by-one), do something — meaning we will attach a "click" listener to every button.

javascript
Copy
Edit
    button.addEventListener('click', (e) => {
👉 Meaning:
Listens for when someone clicks the button, and runs the code inside when clicked.
e means "event" — it has information about which button was clicked.

Inside the click event:

javascript
Copy
Edit
        if (e.target.innerHTML == '='){
👉 Meaning:
If the clicked button has text = (equals sign)...

javascript
Copy
Edit
            string = eval(string);
👉 Meaning:
Evaluate the string as math and replace string with the answer.
(Example: if string was "2+3", it becomes 5.)

javascript
Copy
Edit
            input.value = string;
👉 Meaning:
Show the new string (the result) inside the input box.

javascript
Copy
Edit
        } else if (e.target.innerHTML == 'AC'){
👉 Meaning:
If the clicked button has text AC (All Clear)...

javascript
Copy
Edit
            string = "";
👉 Meaning:
Empty the string.

javascript
Copy
Edit
            input.value = string;
👉 Meaning:
Also clear the input box (nothing will be shown).

javascript
Copy
Edit
        } else if (e.target.innerHTML == 'DEL'){
👉 Meaning:
If the clicked button has text DEL (Delete)...

javascript
Copy
Edit
            string = string.substring(0, string.length-1);
👉 Meaning:
Cut the last character from string.
Example: if string = "123", after deleting, it becomes "12".

javascript
Copy
Edit
            input.value = string;
👉 Meaning:
Update the input box with the new string.

javascript
Copy
Edit
        } else {
👉 Meaning:
If the button is any other button (like numbers or operators + - * /)...

javascript
Copy
Edit
            string += e.target.innerHTML;
👉 Meaning:
Add the button's text to the end of the string.

Example:

Click 2, string becomes "2".

Click +, string becomes "2+".

Click 3, string becomes "2+3".

javascript
Copy
Edit
            input.value = string;
👉 Meaning:
Show the new updated string inside the input box.

javascript
Copy
Edit
    })
}),
👉 Meaning:
Closes the forEach loop and the click event listener.

🎯 Summary in simple words:
Find the input box and all buttons.

Listen for clicks on each button.

If user clicks:

= → Calculate and show the result.

AC → Clear everything.

DEL → Remove the last character.

Anything else → Add button text to the current string and show i
