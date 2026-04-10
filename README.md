> [!NOTE]
> This is a community-maintained fork of a MIT-licensed student project in the *Effective Programming with Effects* course in winter semester 2025/2026.
> Be warned that this is not an officially endorsed project, the code in this repository may be not idiomatic Effekt.
> 
> The original repository is https://github.com/LeoZieger/LinkedIn-Games-in-Effekt

# LinkedIn Games Simulator

While LinkedIn itself is full of mediocre tech-content, excessive work-life-influencers and a lot (really a lot) of AI generated content that wants to show me how to create a perfect resumee, there is one corner i frequently visit: LinkedIn Games! ([https://www.linkedin.com/games/](https://www.linkedin.com/games/))
Similar to the the [nytimes](https://www.nytimes.com) or even [spiegel](https://www.spiegel.de/games/) LinkedIn offers its own collection of puzzle games:

* Zip (fill a grid with a continuos line while reaching cells in the correct order)
* Mini Sudoku (6x6 Sudoku)
* Tango (fill a grid with 2 symbols, with certain rules in place)
* Queens (n-queens problems, but also with areas where the same rules apply, i.e. one queen per row, column, area)
* Pinpoint (find the connection between 5 words)
* Crossclimb (find the correct words that only change one letter, with the help of crossword-like hints)

While the idea is probably to connect with collegues, professors (yes there are some that play daily) and peers, I often play these games on the bus. On one hand, this is because I built up a streak solving all these puzzles, but also because I genuinely enjoy solving them (especially Queens and Zip). Over the months, I found rulesets, algorithms to solve these puzzles in my mind, but I always wanted to implement some of them for a computer to solve and check, if my they make even sense or how I can improve them (this is also to improve my times in comparison to some professors).

My goal would be, to have a menu where the player can chose a game, play it (they are all singeplayer) or get one solved by the computer. For this, I would run the games in the terminal, since they are all 2d / grid based, and the user can input the next move (`⭡`, `⭢`, `⭣`, `⭠` for zip, `⭡`, `⭢`, `⭣`, `⭠`, `x`, `Q` for Queens, ...). The mechanics depend on the games I would implement:

* Zip, Tango, Queens: Here I would really like to implement a puzzle generator, which has the difficulty that the puzzle has to be possible. This would probaby be for the single player option. For an Computer-Solver-Mode, I might store a puzzle-file on the disk and let the computer solve it. This would also be the way to get the daily solution of the *actual* game.
* Mini Sudoku: I will probably not implement this, since we already did a sudoku and this will not be that different.
* Pinpoint, Crossclimb: I will probably not implement those, since they depend on creativity. I might be interested in writing a puzzle generator for Crossclimb, since this seems to be possible (when having the whole english dictionary and search paths of length n between words, where only one char differs) but since I cant provide the hints, this would not make much sense.

I am looking forward to implementing interesting solvers and generators for the puzzles that I solve each day by hand.

## Must-have

* Games are playable in the terminal
* Navigation-Menu (might be very simple) to switch between puzzlegames and decide how to play
* Singleplayer, solver and generator for Zip, Tango and Queens
* Possibility to store puzzles in some file and play them.

## Can-have

* Puzzle-Editor: Option for the player to create the puzzle in the terminal itself. Is possible and not too annoying for Tango and Zip (Queens is probably to overloaded with setting regions and colors...)
* *LinkedIn-Scraper*: It might be possible to get the daily game from the website and offer it to play
* Some help actions while playing (filling the next cell, giving hints, etc.)
* Maybe some new kind of puzzle game I find along the way ...
* LinkedIn-like banners after you win 'You are smarter than 60% of CEOs' (yes this one really exists)
* Different color-schemes (maybe have fun characters for Queens and Tango)
* Timer and scoreboard to compare to others.

## Will-not-have

* Any kind of mulitplayer
* GUI

## Effects and Handlers

* File In- and Output
* Something to visualise the game in the terminal. Since they are all grid-based, a `update_grid()` effekt would be usefull
* Something to get the user Input and check if its valid, this could mean, the game throws an effekt `playerinput(options)`, the handler checks if the user input is in `options` and then resumes with the input (and waits for valid input).
* Some Puzzle and Solver specific effekts and handlers, like `direction(options)` for Zip - here the effekt can be handled by getting some user input (see above) or by handling it with a computer solver.
* many more (also depending on the *Can-have*s)
