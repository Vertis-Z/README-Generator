# README Generator

## User Story

```
AS A developer
I WANT a README generator
SO THAT I can quickly create a professional README for a new project
```

## Acceptance Criteria

```
GIVEN a command-line application that accepts user input
WHEN I am prompted for information about my application repository
THEN a high-quality, professional README.md is generated with the title of my project and sections entitled Description, Table of Contents, Installation, Usage, License, Contributing, Tests, and Questions
WHEN I enter my project title
THEN this is displayed as the title of the README
WHEN I enter a description, installation instructions, usage information, contribution guidelines, and test instructions
THEN this information is added to the sections of the README entitled Description, Installation, Usage, Contributing, and Tests
WHEN I choose a license for my application from a list of options
THEN a badge for that license is added near the top of the README and a notice is added to the section of the README entitled License that explains which license the application is covered under
WHEN I enter my GitHub username
THEN this is added to the section of the README entitled Questions, with a link to my GitHub profile
WHEN I enter my email address
THEN this is added to the section of the README entitled Questions, with instructions on how to reach me with additional questions
WHEN I click on the links in the Table of Contents
THEN I am taken to the corresponding section of the README
```

### Node.js Functionality

```
The generator was written in Node.js utilizing mostly the Inquirer module for a large portion of its functionality.

The app starts with the user being given a welcome message. This is an array of one inquirer confirm object. I wanted to present the user with a bit of a greeting before throwing them right into the meat of the app. Once the user is ready and hits 'y', I have a console log display a very small syntactical cheat sheet just in case the user wants to add some flair, links, or images as they generate the README.

Next, the user is walked through a set of questions that requires their input. I utilized regex to use validate to make sure the use puts in a valid email. The sections title, table of contents, description, license, & questions are required. In the remaining sections, the user is given the choice if they would like to like to add each section. If they select yes the next question asks for them to input their data. If they choose no a confirm for the next section appears and the section they are not including does not appears in the table of contents.

Once the majority of the section selections are completed the user is presented with the license options. They can choose from eight of the most popular open-source licenses. After choosing a license a the respective license badge will be at the top of the README and a license section with text stating what license was chosen will be created. There is also a copyright added with a year. That year is brought in via `newDate()` to not have the date hardcoded for future use of the app.

Lastly, the user is prompted with adding a credits section. This section was the most difficult because I wanted the user to be able to put in as many credits as they see fit. With that, I had to create a loop of some sort and I could not find the solution with Inquirer alone. I initially found an inquirer plug-in that allowed for the recursion I needed but much to my chagrin, the UI of the output was not polished. I then was able to find a chunk of code in that plug-ins issues section of its repo that, not only, did what I needed but looked correct. I decided to use that code (credits below) and create my own module to call on this functionality. Now the user can add as many or as few credits as they need.

The instructions to generate the README are a custom module as well. I would like to take credit for this but I cannot as that framework was set up in the assignment when given to me. I did, however, write all the necessary code to take in the user input data and add it to the `generateMarkdown()` function to create the file.

Lastly, I used an async/await function to handle the promises and then finally generate the README which is written to the './output/' folder in the repo.
```
<<<<<<< HEAD
=======


## Demo Video
https://user-images.githubusercontent.com/48894365/168934584-15677553-3719-45df-8754-ef8663190b23.mp4

>>>>>>> bd8afd73235ce6df2850018a8659872e0082a718
