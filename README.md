# Text Analyzer

#### A simple text analyzer made while following Epicodus' "separation of logic" and "DRYing and refactoring code" lessons.

#### By Jacob Strong

## Technologies Used

* HTML
* CSS
* Bootstrap
* JavaScript
* jQuery
* Markdown

## Description

This application analyzes text to allow the user to easily figure out how many words are in a passage as well as how many times a word appears in a passage.

## Installation and Setup

* Make sure you have the latest versions of the related software installed on your machine.
* Clone this repository to your desktop by executing $ git clone https://github.com/JacobTStrong/text-analyzer in the command line.
* Locate the directory on your computer and open it in your text editor to view the code.
* Double-click on the "index.html" file within the project directory to open the web page in your browser.
* At this point, you can type or copy and paste a passage of text in the top text field. If you click "submit survey" now, the application will simply tell you how many words are in the passage.
* Once the previous step has been completed, you can type a word in the bottom text box and the application will tell you how many time that word appears in the passage. The inputted word will also appear beneath "selected word count" in bold font.
* That's about it! Again, this is a simple class excercise made to teach proper separation of logic, the "Don't Repeat Yourself" or "DRY" concept, and Test-Driven Development (all tests for this project can be viewed below).

## Known Bugs

* No known bugs at the moment.

## License

[MIT](https://en.wikipedia.org/wiki/MIT_License)

Copyright (c) 2021 Jacob Strong

## Contact Information

Jacob Strong <a href="mailto:rjts2896@gmail.com">rjts2896@gmail.com</a>

TESTS:

Describe: wordCounter()

Test: "It should return 1 if a passage has just one word."
Code:
const text = "hello";
wordCounter(text);
Expected Output: 1

Test: "It should return 2 if a passage has two words."
Code:
const text = "hello there";
wordCounter(text);
Expected Output: 2

Test: "It should return 0 for an empty string."
Code: wordCounter("");
Expected Output: 0

Test: "It should return 0 for a string that is only spaces."
Code:
wordCounter("             ");
Expected Output: 0

Test: "It should not count numbers as words."
Code:
wordCounter("hi there 77 19");
ExpectedOutput: 2

Describe: numberOfOccurencesInText()

Test: "It should return 0 occurences of a word for an empty string."
Code:
const text = "";
const word = "red";
numberOfOccurencesInText(word, text);
Expected Output: 0

Test: "It should return 1 occurence of a word when the word and the text are the same."
Code:
const text = "red";
const word = "red";
numberOfOccurencesInText(word, text);
Expected Output: 1

Test: "It should return 0 occurences of a word and the text are different."
Code:
const text = "red";
const word = "blue";
numberOfOccurencesInText(word, text);
Expected Output: 0

Test: "It should return the number of occurences of a word."
Code:
const text = "red blue red red red green";
constword = "red";
numberOfOccurencesInText(word, text);
Expected Output: 4

Test: "It should return a word match regardless of case."
Code:
const text = "red RED Red green Green GREEN";
const word = "red";
numberOfOccurencesInText(word, text);
Expected Output: 3

Test: "It should return a word match regardless of punctuation."
Code:
const text = "RED! Red. I like red, green, and yellow.";
const word = "Red";
numberOfOccurencesInText(word, text);
Expected Output: 3

Test: "If an empty string is passed in as a word, it should return )."
Code:
const word = "";
const text = "red RED Red!";
wordCounter(word,text);
Expected Output: 0

Describe: boldPassage()

Test: "It should return a non-matching word in a p tag."
Code:
const word = "hello";
const text = "yo";
boldPassage(word, text);
Expected Output: "<p>yo</p>"

Test: "It should return a matching word in a b tag."
Code:
const word = "hello";
const text = "hello";
boldPassage(word, text);
Expected Output: "<p><b>hello</b></p>"

Test: "It should wrap words that match in 'b' tags but not words that don't."
Code:
const word = "hello";
const text = "hello there";
boldPassage(word, text); 
Expected Outcome: "<p><b>hello</b> there</p>"
