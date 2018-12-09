
# LIRI Bot

  

This is an app that allows users to search for, Movies, Concerts, Music by selecting commands from a list and then typing in a search term. This program runs only in the CLI (like Bash).

  

## Getting Started

  

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

  

### Prerequisites

The following must be installed on your machine:

  

- Git Bash

- NodeJS

- NPM

  

### Installing Dependencies

Use NPM to install all required dependencies:

  

npm install

  

## Running the App

  

Use the following command to start the app:

  

node liri.js

  

## Using the App:

### Demo:

![Alt Text](https://github.com/byronthe123/liri-bot/blob/master/LiriGIF.gif)

The user will be prompted with the following:

  

---------------------- NEW SEARCH ------------------------

? what do you want to do? (Use arrow keys)

> movie-this

concert-this

spotify-this-song

do-what-it-says

  

The user must select one of the options to proceed. Next the user will be shown the following:

  

? what do you want to search?

The user must type in a **search term**. Depending on the action and search term, the app will fetch and display data to the user in the following format:

  

---------------------- NEW SEARCH ------------------------

? what do you want to do? movie-this

? what do you want to search? the fellowship of the ring

Title: The Lord of the Rings: The Fellowship of the Ring

Year: 2001

Country: New Zealand, USA

Language: English, Sindarin

Plot: A meek Hobbit from the Shire and eight companions set out on a journey to destroy the powerful One Ring and save Middle-earth from the Dark Lord Sauron.

Actors: Alan Howard, Noel Appleby, Sean Astin, Sala Baker

imdbRating: 8.8

Rotten Tomatoes Rating: 91%

  

The `do-what-it-says` command is a special command that displays search results from a txt file in the program called `random.txt` .

  
  

## Programming Methodology

  

### Approach

The goal was to break down each main function of the app into a separate module. Thus, the **movie, spotify, doWhatItSays**, and **log** functions were all placed in their own separate modules that are imported into **liri.js**. The `bandsSearch` function was placed into liri.js because exporting the data returned by the `https.get()` function was not possible (as of now). It was probably possible to use **Axios** to get data from the **Bands in Town API**, but `https.get()` was chosen for the sake of using more functions. 


**Inquirer.js** was also integrated into the program once the core functionality was built. Using Inquirer.js, it was possible to prompt the user to choose an action and to input a search term. This resulted in a better use interface than having to manually type in both actions and search terms.

  

The `promptAction()` method starts the app by prompting the user to select an action. The selected action is passed into the `promptSearch(action)` function as the parameter in the `.then()` section of the `promptAction()` method. The `promptSearch(action)` method then **recursively** calls the `promptAction()` method to keep the program running in a loop. The `log` module uses the `writeLog` function to log all user searches to the **log.txt** file.

  

The `doWhatItSays` module uses the `doWhatItSaysFunction()` as a **callback**. There was probably a simpler way of writing up this function, but for the sake of experimenting with callbacks, this approach was chosen.

  

## Built With

  

- NodeJS

- NPM

- MomentJS

- Node-Spotify-API

- Axios

- OMDB API

- Bands In Town API

## Syntax and Conventions

The app is written in ES6. 
