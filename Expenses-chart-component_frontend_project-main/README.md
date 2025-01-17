# Expenses Chart Component

## Welcome! 👋

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [How to setup the project](#how-to-setup-the-project)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

The challenge is to create an Expenses Chart Component, part of a website designed to calculate and track expenses. 

Users should be able to 
- View the bar chart.
- Hover over individual bars to see the correct amounts for each day.
- See the current day's bar highlighted in a different color.
- View the optimal layout for the content depending on their device's screen size.
- See hover states for all interactive elements on the page.
- A bonus challenge is to dynamically generate bars based on the data provided in a local JSON file.

### How to setup the project

To set up the project locally, follow these steps:

1. Clone the repository using GitHub Desktop or Git Bash:
   ```bash
   git clone https://github.com/SartHak-0-Sach/Expenses-chart-component_frontend_project.git
   ```
2. Open the project folder in your code editor.
3. Run the project using a live server extension or deploy it using Netlify, Vercel, or another web hosting and deployment service.

### Screenshot

![Design Preview](./design/active-states.jpg)

### Links

- Solution URL: [GitHub Repository](https://github.com/SartHak-0-Sach/Expenses-chart-component_frontend_project)
- Live Site URL: [Live Site](https://expense-chart-app-frontend.netlify.app/)

## My process

### Built with

- HTML5
- CSS3
- JavaScript

You will find all the required assets in the `/images` folder. The assets are already optimized.

There is also a `style-guide.md` file containing the information you'll need, such as color palette and fonts.

### What I learned

Through this project I learnt how one makes a website/web app dynamic with different content customized/personalized for each and every user using math operations in JavaScript as shown-

```js
function populateBars(jsonArr) {
    const maxAmount = jsonArr.reduce(
        (max, obj) =>
            Number(max) < Number(obj.amount) ? Number(obj.amount) : Number(max),
        0
    );

    let height;
    if (window.innerWidth >= 700) {
        height = (ratio) => `${ratio * 150}px`;
    } else {
        height = (ratio) => `${(150 / 375) * ratio * 100}vw`;
    }

    for (const obj of jsonArr) {
        const bar = document.querySelector(`#${obj.day}`);
        const ratio = obj.amount / maxAmount;
        bar.style.height = height(ratio);
        bar.style.transitionDuration = `${ratio * 2}s`;
        bar.dataset.amount = `$${obj.amount}`;
    }

    // Highlight current day with a different color
    const weekDayIndex = (new Date().getDay() - 1 + 7) % 7;
    const currBar = document.querySelectorAll(".bar")[weekDayIndex];
    currBar.style.backgroundColor = cyan;
    currBar.onmouseover = () => (currBar.style.backgroundColor = fadedCyan);
    currBar.onmouseout = () => (currBar.style.backgroundColor = cyan);
}
```

### Continued development

The continuously learning journey of a programmer never ends. This project made me realize that there are many concepts that I need to work upon including fundamentals like flex-box and its properties, to more complex concepts like working with fetch and async await in javascript. These areas are some that I think I need to work more upon in the upcoming future as they highlight some of the most significant regions of web development that are important for every developer to know of. 

These key points mentioned here will help me grow accountable and consistent towards improving at writing good quality code and be a successful full stack developer one day.

### Useful resources

- [Harkirat Singh course notes](https://github.com/SartHak-0-Sach/harkirat-singh-course_code_and_notes) - I have added notes of all lectures along with code and lecture insights of all weeks along with bonus lectures to help you all as much as I can.
- [My development code and notes](https://github.com/SartHak-0-Sach/cwh-web-dev-playlist_code_and_notes) - These are my notes that I made while working on my development skills in initial days and did these courses. Make sure to star the repository if you like it.✨💫
- [mdn documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) - This is an amazing article which helped me finally understand promises, async and await syntax. I'd recommend it to anyone still learning this concept.

## Author

<b><strong>Sarthak Sachdev</strong></b>
- Website - [Sarthak Sachdev](https://itsmesarthak.netlify.app/)
- LeetCode - [@sarthak_sachdev](https://leetcode.com/u/sarthak_sachdev/)
- Twitter - [@sarthak_sach69](https://www.twitter.com/sarthak_sach69)

## Acknowledgments

I feel like the solutions provided on the website and the continuous doubt solving by industry experts on discord for free is something that is unmatched by anyone else and need to be acknowledged for their efforts in improving me as a developer by suggesting the best practices in your respective tech stack.

## Got feedback for me?



If you found this project helpful, consider sharing it with others to spread the knowledge!

**Happy budgeting!** 💰🚀