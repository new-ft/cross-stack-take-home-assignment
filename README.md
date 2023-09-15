# Cross-stack Engineer Take-Home Assignment

## Introduction

Thank you for your interest in joining our team as a Cross-stack Engineer. As part of our hiring process, we'd like to assess your technical skills, problem-solving abilities, and attention to detail through a take-home assignment. This exercise is designed to evaluate not just your coding skills but also your understanding of user experience and design principles. While we estimate that this task should take a few hours, feel free to invest additional time to add any extra features or polish that you think would make your solution stand out.

## Objective

One of your primary tasks is to develop Dropdown Select component using React that pulls data from a ASP.NET Core web API. This component should allow users to select a single option from a list.

## Component API Example

Here's what the component API should look like:

```jsx
const options = [
    { value: 'b4cd5643-dfae-5a6a-9f03-ec13ec73a653', label: 'Jane Doe (1877-1941)' },
    { value: 'c32b846d-134e-5cd0-b465-07f252c9616b', label: 'Oliver Smith (-1910)' },
    { value: 'e385e979-38dd-51b6-86e7-db1f6457adcf', label: 'Emily R Atkinson (Living)' },
];

<DropdownSelect
    label="Select a person"
    options={options}
    onChange={value => console.log(value)}
/>
```

### Technology guidelines

- **Technology Stack:** You must use React and ASP.NET Core for this assignment. Feel free to bootstrap the project in the way you're most comfortable with (Vite, Next.js etc)
- **Styling:** You are free to use any styling solution you prefer (CSS, Tailwind, CSS-in-JS etc).
- **TypeScript:** It's not a mandatory requirement for this assignment.
- **Tests:** Implement tests covering the basic functionality of the component.

### Design guidelines

This section outlines the functionalities and features that the Dropdown Select component should possess.

- **Dropdown input UI:** Create the user interface for the dropdown input field. This is the element that users will interact with to trigger the dropdown menu.

- **Dropdown menu UI:** Develop the dropdown menu that will appear when the input field is clicked. This menu will display the list of selectable options. Additionally, the currently selected option should be highlighted within the menu to provide visual feedback to the user. The data for the options should be provided by the ASP.NET Core web API that you create.

- **Dropdown label:** The component should include a label that serves as a placeholder when no option is selected. Once an option is selected, the label should be replaced by the selected item.

- **Open/close menu handler:** Implement the functionality to open and close the dropdown menu.

- **Select:** Add the logic to handle the selection of items within the dropdown menu. The selected item should be displayed in the input field, and the `onChange` callback should be triggered.

- **Searchable Dropdown:** Implement a search feature within the dropdown menu that allows users to filter through the list of options.

- **onChange Callback:** Implement an `onChange` callback function that will be triggered when an item is selected or deselected. This function should pass the selected value as an argument.


### User Experience Guidelines

To assist you in understanding the desired user experience and interactions for the Dropdown Select component, we will provide a set of GIF images. These GIFs will serve as visual guides to demonstrate how the component should behave in various scenarios, such as:

- Opening and closing the dropdown menu

<div align="left">
  <img src="https://github.com/washingtonsoares/frontend-take-home-assignment/assets/5726140/8b1d3616-677e-49e7-b2d9-0e46ebd0482d" alt="open-close-menu" />
</div>

- Selecting items

<div align="left">
 <img src="https://github.com/washingtonsoares/frontend-take-home-assignment/assets/5726140/4ae24c61-65c0-4ea2-abce-6666bf0d0032" alt="selecting items" />
</div>

- Searching for items

<div align="left">
 <img src="https://github.com/washingtonsoares/frontend-take-home-assignment/assets/5726140/682afdb9-b4cc-4d7b-b0f0-a6bafcdff02b" alt="searching for items" />
</div>

<br />
<br />

**Color Palette**

- Dropdown item selected: #0d6efd
- Dropdown item hover: #9fc3f870

However you are totally free to choose your own color scheme if you believe it enhances the component's usability or aesthetics

### ASP.NET Core Web API

- Create an HTTP endpoint to return a list of people given a specific ID of a family tree to which the people belong. You should create sample data for multiple trees.
- The API should check for the presence of a custom header `x-client-id` with a known (constant) value and return `400` if the header is not present or `401` if the header has an unrecognized value
- A person should have the following data structure:
  - `Id` (Guid)
  - `GivenName` (String)
  - `Surname` (String)
  - `Gender` (Enum)
  - `BirthDate` (Date)
  - `BirthLocation` (String)
  - `DeathDate` (Date)
  - `DeathLocation` (String)
- The API should return the Id of the person as the value of the dropdown item and a string for display that provides the full name of the person and their life span using the following rules:
  - If the person has both a birth date and a death date, provide the lifespan as `(BirthYear-DeathYear)`
  - If the person has only a death date, provide the lifespan as `(-DeathYear)`
  - If the person has neither a birth date nor a death date, provide the lifespan as `(Living)`
  - If the person has no death date and has a birth date less than 120 years ago, provide the lifespan as `(Living)`
  - If the person has no death date and has a birth date 120 years ago or more, provide the lifespan as `(BirthYear-)`
  - Create sample data to illustrate each of these scenarios
- These life span rules should be implemented in the back end API, not in the front end code.

### Bonus Features

If you found the core task to be relatively straightforward and are interested in going the extra mile, consider implementing the following optional features:

- **Keyboard navigation:** Implement keyboard navigation to allow users to navigate through the dropdown menu using the arrow keys and select items using the enter key.
- **Online Demo:** Deploy a live demo of your component using platforms like Netlify, Vercel, CodeSandbox etc.

### Delivery Instructions

- **Repository:** Submit your solution by providing a link to a public GitHub repository.
- **README:** Include a README.md file in your repository with clear instructions on how to set up and run your project.
- **Questions:** If you encounter any uncertainties or ambiguities, feel free to reach out to us for clarification.

**We're excited to see what you come up with. Good luck!**
