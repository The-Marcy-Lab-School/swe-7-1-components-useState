# Multilingual Lab

**Table Of Contents**
- [Assignment Overview](#assignment-overview)
  - [Set Up](#set-up)
- [Tech Checklist](#tech-checklist)
- [Tips: Proper Coding Style In React](#tips-proper-coding-style-in-react)
- [Challenges](#challenges)
  - [Optional: File Organization Challenge](#optional-file-organization-challenge)
  - [Optional: Styling Challenge](#optional-styling-challenge)

## Assignment Overview

In this assignment, you will be building out the project shown below. You should divide your UI into the appropriate components and should utilize state and the `useState` hook. 

![demo](./demo.gif)

In this project, you will practice the following skills:
- Creating a React project using Vite
- Creating functional components and rendering HTML using JSX
- Managing state with `useState`
- Handling events in React and updating state accordingly
- Organizing a React project

### Set Up

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

After cloning your repository, make sure to create a `draft` branch:

```
git checkout -b draft
```

Then, use [Vite](https://vitejs.dev/guide/) to create your starter code. You can run these commands to get started:

```sh
npm create vite@latest
# Choose Project Name like app
# Select React
# Select JavaScript

cd app
npm i
npm run dev
```

Open up the `App.jsx` file and remove the starter app.

Then get started building!

## Tech Checklist

Starting in this unit, we will be using a different form of grading. Rather than running automated tests, we will be testing your application as a user would. We'll run your application and see what features your app can do. Your score will be determined based on the number of completed requirements listed below.

There are 12 tasks to complete and 2 bonuses.

Your goal is to meet at least 75% of these requirements to complete the assignment. But don't stop there! Shoot for 100%! 

**Functionality:**
- [ ] Your app should render as a greeting (perhaps, "Good Morning") in English. 
- [ ] Beneath this greeting, there should be five buttons. 
- [ ] Each button should correspond to a different language (perhaps, "Spanish", "Haitian Creole", and "Portuguese"). 
- [ ] When a language button is clicked, the greeting above should be translated to the appropriate language.
- [ ] Above your greeting, there should be two buttons to change the font size.
- [ ] When the buttons are clicked, the greeting size should grow or shrink accordingly. 

**React Fundamentals**
- [ ] Component names use PascalCase (`MyComponent` instead of `myComponent`)
- [ ] Props are extracted in child components using destructuring
- [ ] `useState` is used to manage state

**Miscellaneous**
- [ ] Used Vite to create the project
- [ ] The size buttons, the greeting, and the language buttons should each be their own component for a total of 3 components (on top of the root `App`)
- [ ] At no point did you ever use any vanilla DOM JS methods (e.g. `document.querySelector` or `document.createElement`)
- [ ] Bonus: You have a `components` directory. Each component has its own file and is exported (1 export per file). The filename matches the name of the component being exported (`Header.jsx` exports a `Header` component).
- [ ] Bonus: Your project has some extra CSS styling!

## Tips: Proper Coding Style In React

Below is an example of a Counter application written using React and JSX. Note the following:
* Each component is a function that returns JSX. Function names are in UpperCamelCase.
* Components that return multiple elements are surrounded by `()` and must have a top-level element, even if it is just `<> </>`
* Components can take in "props" — data passed down from parent components.
* Data is injected into JSX using `{}`
* Event handlers are set directly on the element (for example, using `onClick={handler}`)

```jsx
// useState is imported at the top
import { useState } from 'react';

// component names use PascalCase
const CounterDisplay = ({ count }) => {
  return <p>{count}</p>
}

const CounterButtons = ({ increment, decrement }) => {
  // props are destructured ^          ^
  
  // multiple returned components are wrapped with () and <> </>
  return (
    <>
      <button onClick={increment}>+</button>
      <button onClick={decrement}>-</button>
    </>
  )
}

// App is exported (default or named is fine)
export const App = () => {
  // state is "lifted up" and passed down with props
  const [count, setCount] = useState(0);

  // helper functions can be passed down instead of the setter function itself
  const increment = () => { setCount(count + 1) }
  const decrement = () => { setCount(count - 1) }

  return (
    <>
      <CounterDisplay count={count} />
      <CounterButtons increment={increment} decrement={decrement} />
    </>
  )
}
```

## Challenges

### Optional: File Organization Challenge

Your app should utilize multiple components to organize its content. But maybe you put all of your components in the `App.jsx` file? This is honestly fine for a project of this size but as projects grow (and they will grow), you will need a more organized solution.

Here is what we think works well:
* Create a `components` folder in the `src` folder
* For each component, create a file called `MyComponentName.jsx` (note the capitalized file name. It should match the component that you create)
* The component file should export a single component as the default export.
* In `App.jsx`, import your components! You shouldn't need to update the `App` component itself.

### Optional: Styling Challenge

Ready to add some pizzazz to your website! Add some CSS styling to your website!

Check out this article from FreeCodeCamp on [styling react apps with css](https://www.freecodecamp.org/news/style-react-apps-with-css/).


