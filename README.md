# Events and Debugging Assessment

Time to assess how well you have learned to use the debugging tools in Chrome Dev Tools, and writing click event listeners. This application is to show kids with illnesses and the memories the would like to make. Celebrities sign up to help kids make memories.

> 🧨 Make sure you answer the vocabulary and understanding questions at the end of this document before notifying your coaches that you are done with the project

## Event Listeners to Create

1. When the kid name is clicked, it should display their wish.
1. When the celebrity name is clicked, it should display their sport.
1. The pairings list should should contain the pairing in the following format.
    ```html
    {child name} will be making memories with {celebrity name}, a {celebrity sport} star, by {child wish}
    ```

Below is an animation showing how the application should look when complete and how the event listeners should work.

<img src="./images/debugging-events-assessment.gif" width="700px">

## Setup

Your instruction team will provide a link for you to create your assessment repository. Once your repo is created, clone it to your machine.

1. Make sure you are in your `workspace` directory.
1. `git clone {github repo SSH string}`.
1. `cd` into the directory it creates.
1. `code .` to open the project code.
1. Use the `serve` command to start the web server.
1. Open the URL provided in Chrome.

Make sure your Developer Tools are open at all times while working on this project. Use the messages provided in the Console to determine what code needs to be fixed or implemented, and use breakpoints in the Sources tab to step through your code as you debug.

## Vocabulary and Understanding

Before you click the "Complete Assessment" button on the Learning Platform, add your answers below each question and make a commit.

1. When a child is clicked on in the browser, which module contains the code that will execute on that event happening? Can you explain the algorithm of that logic?
   > The module that contains the click event code is Kids.js. The first check is for the data type and to see if it matches the "child" data type attribute `itemClicked.dataset.type === "child"`. The for loop then asks if the item that was clicked was "child" data type. If the answer is yes, the item returns a pop up relating to that data type and checks the specific Id of the data type relating to which item was clicked. The pop up shows the specific child name(returned if it matches the id for the child, using the specific properties of that child) and returns the property ".name" and ".wish".
2. In the **Pairings** module, why must the `findCelebrityMatch()` function be invoked inside the `for..of` loop that iterates the kids array?
   > `findCelebrityMatch()` cannot find the specific kid's celebrity match unless it is inside the for..of loop. `kid` only lives inside this loop, so without being inside the same loop, findCelebrityMatch() cannot return that information.
3. In the **CelebrityList** module, can you describe how the name of the sport that the celebrity plays can be displayed in the window alert text?
   > The first step is finding the celebrities in the database. This is found by locating getCelebrities in the database,  which is a function returning a structuredClone holding the  (database.celebrities) properties. celebrity is an object in an array, and each celebrity has the property "sport:".  The window alert's for loop runs through the celebrities objects, checking if the clicked object id property matches the celebrity.id property. If it does, it returns the window alert with the ${celebrity.sport}, which locates the sport property assigned to that specific celebrity.
4. Can you describe, in detail, the algorithm that is in the `main` module?
   > First step is importing the functions Pairings from ./Pairings.js, Celebrities from ./CelebrityList.js, and Kids from ./Kids.js. The method document.querySelector("#container") locates the id of container in the HTML file (DOM) and assigns it to the mainContainer variable. Next, we invoke the const applicationHTML string, holding the HTML for the page invoking the functions imported above. This allows for that information to appear on the local server page. Lastly, mainContainer.innerHTML = applicationHTML injects into the `#container` element on the actual page. This allows for the HTML to be shown on the page.
