Glowsticks5 - Password Generator 

Inserted code using variables that focuses on the function of the password generator; used array to hold lowercase, upper case, numbers and symbols

var generateBtn = document.querySelector("#generate");

var lowercase = [
  "a",
  "b",
  "c",
  "d",
  "e",
  "f",
  "g",
  "h",
  "i",
  "j",
  "k",
  "l",
  "m",
  "n",
  "o",
  "p",
  "q",
  "r",
  "s",
  "t",
  "u",
  "v",
  "w",
  "x",
  "y",
  "z",
];

var uppercase = [
  "A",
  "B",
  "C",
  "D",
  "E",
  "F",
  "G",
  "H",
  "I",
  "J",
  "K",
  "L",
  "M",
  "N",
  "O",
  "P",
  "Q",
  "R",
  "S",
  "T",
  "U",
  "V",
  "W",
  "X",
  "Y",
  "Z",
];

var symbols = [
  "!",
  "#",
  "$",
  "&",
  "%",
  "'",
  "*",
  "+",
  "-",
  "/",
  ":",
  ";",
  "<",
  "=",
  ">",
  "?",
  "@",
  "^",
  "_",
  "~",
  "`",
  "{",
  "|",
  "}",
  ".",
];

var numbers = ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9"];

To create a password length, I started using functions so that the user can access any type of length between the numbers 8 and 128

function generatePassword(params) {
  var passwordLengthFromInput = prompt(
    "please choose a password between 8 and 128 letters"
  );

  var passwordLength = parseInt(passwordLengthFromInput, 10);

  if (passwordLength < 8 || passwordLength > 128 || isNaN(passwordLength)) {
    alert("Please choose a a number between 8 and 128 for the Password Length");
    return;
  }

  var isLowercase = confirm(
    "Do you want lowercase characters in your password?"
  );

  var isUppercase = confirm("Do you want upper characters in your password?");

  var isNumbers = confirm("Do you want numbers characters in your password?");

  var isSymbols = confirm("Do you want symbols characters in your password?");


added finalArray to indicate that if the user doesn't  none of the suggested elements, a window alert will pop up asking for you to choose one of the options.

var finalArray = [];
if (isLowercase === true) {
    finalArray.push(...lowercase);
  }
  if (isUppercase === true) {
    finalArray.push(...uppercase);
  }
  if (isNumbers === true) {
    finalArray.push(...numbers);
  }
  if (isSymbols === true) {
    finalArray.push(...symbols);
  }

  if (finalArray.length === 0) {
    alert("Please choose at least one type of characters");
    return;
  }

To generate a loop, I used a function like Math.floor and Math. random to generate the random password to select the random characters that wwe will use for the random password)

 let password = " ";
  for (let i = 0; i < passwordLength; i++) {
    password += allChar.charAt(Math.floor(Math.random() * allChar.length));
  }

  return password;
}


Added event listener as the final JAVAScript code to make the password generator a functioning website.

generateBtn.addEventListener("click", writePassword);
console.log(generateBtn);


