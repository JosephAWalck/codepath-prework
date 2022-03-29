# Pre-work - *Memory Game*

**Memory Game** is a Light & Sound Memory game to apply for CodePath's SITE Program. 

Submitted by: **NAME**

Time spent: **#** hours spent in total

Link to project: (insert your link here, should start with https://glitch.com...)

## Required Functionality

The following **required** functionality is complete:

* [x] Game interface has a heading (h1 tag), a line of body text (p tag), and four buttons that match the demo app
* [x] "Start" button toggles between "Start" and "Stop" when clicked. 
* [x] Game buttons each light up and play a sound when clicked. 
* [x] Computer plays back sequence of clues including sound and visual cue for each button
* [x] Play progresses to the next turn (the user gets the next step in the pattern) after a correct guess. 
* [x] User wins the game after guessing a complete pattern
* [x] User loses the game after an incorrect guess

The following **optional** features are implemented:

* [x] Any HTML page elements (including game buttons) has been styled differently than in the tutorial
* [ ] Buttons use a pitch (frequency) other than the ones in the tutorial
* [ ] More than 4 functional game buttons
* [x] Playback speeds up on each turn
* [x] Computer picks a different pattern each time the game is played
* [x] Player only loses after 3 mistakes (instead of on the first mistake)
* [ ] Game button appearance change goes beyond color (e.g. add an image)
* [ ] Game button sound is more complex than a single tone (e.g. an audio file, a chord, a sequence of multiple tones)
* [ ] User has a limited amount of time to enter their guess on each turn

The following **additional** features are implemented:

- [ ] List anything else that you can get done to improve the app!

## Video Walkthrough

Here's a walkthrough of implemented user stories:

![](https://i.imgur.com/uhB38Gb.gif)

![](https://i.imgur.com/bq655wY.gif)

![](https://i.imgur.com/vnmxMQP.gif)

## Reflection Questions
1. If you used any outside resources to help complete your submission (websites, books, people, etc) list them here. 

For the randomly populated array, I did review a few posts on stackoverflow to search an approach that suited this implementation.
For CSS on the buttons, I had used https://cssbuttons.io/ to find a button that I thought would fit the project.

2. What was a challenge you encountered in creating this submission (be specific)? How did you overcome it? (recommended 200 - 400 words) 

A challenge that I had encountered when implementing the optional requirements presented a few issues. One bug was that a valid guess would result in a losing game but on occasion this wouldn't happen. After the first clue had been guessed correctly, the guesses would consistently register correctly, since the clues were now displaying from the randomized array. This bug was caused by randomizing the array AFTER the starting clue had been played. Once I removed the shuffleArray function and its calls, and determined that the program consistently worked without that functionality, I was able to determine that the implementation of random clues was where I had gone wrong. Starting with the call to shuffleArray() in startGame(), I traced my code and wrote on a whiteboard exactly what was being executed. After tracing execution, I was able to quickly find my issue and correct it. I moved the shuffleArray() call before the playClueSequence() call in startGame(). 
A second issue that had been encountered was rather small. This was the approach to decrementing the timer after each clue. While the problem states that the playClueSequence() function should decrement the time playing the clue, I noticed that with the 3 mistakes implementation, the timer would be able to decrement below what would be possible if there were no mistakes. Since my implementation of the mistakes replayed the clue after a mistake, it would decrement the timer after a mistake. This prompted me to add a floor to the timer that way the timer never reaches a value that the user will not be able to comprehend. Also, initialization for the timer variable had to be added to the startGame() function so the shortened times did not persist after the first game.

3. What questions about web development do you have after completing your submission? (recommended 100 - 300 words) 

With all of the technologies that exist for web development, how could a simple project like this benefit from some of those technologies? What features could be added or improved upon? Are there and frameworks or tech-stacks that would add value to this project? At want point does something become bloated with features and functionality? A proof of concept project such as this is great for beginners to nail down the basics of web development. It even presents the possibility to add features such as a back end and database to track high scores like an arcade game. What intrigues me, which is beyond the scope of this project, is what the design process is like in industry. What sort of challenges are companies faced with before, during, and after taking on projects. How are those challenges consistently handled in a way to minimize time and money spent on these projects/challenges?

4. If you had a few more hours to work on this project, what would you spend them doing (for example: refactoring certain functions, adding additional features, etc). Be specific. (recommended 100 - 300 words) 
I would have to choose between implementing more of the optional features such as a timer and more buttons, and polishing what I already have implemented. If I were to polish what I have implemented, I would focus on the timer first. With the mistakes implementation, the timer seems to present a small issue metioned earlier (decrementing time when mistake is made). With more time, I would also be able to test more and possibly find more bugs to fix.
I would also like to add the feature of "infinitely" playing the game. The pattern would grow and the length of the pattern would be the user's score. Instead of winning, or losing, the player would get a score that they could always try to best. This also presents the need to track the scores of users which presents even more challenges to overcome.



## Interview Recording URL Link

[My 5-minute Interview Recording]
https://drive.google.com/file/d/1eMqYoAUBjkevivfGnb_2LkQHH1qfm0u8/view?usp=sharing


## License

    Copyright [YOUR NAME]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
