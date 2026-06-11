# React Assignment

Congratulations on being selected for our React assignment! This document will guide you through the steps to complete the assignment successfully.

## Objective

The objective of this assignment is to evaluate your knowledge in web development using React and Typescript. We will be assessing your ability to create a functional and visually appealing web application. We have a set of required features that you must implement in the given time frame, as well as some bonus feature that you can choose to implement for extra credit.

You will have a total of **50 minutes** to complete the assignment, during this time you need to be sharing your screen with us. We will not be providing any assistance during the assignment (only if any technical issues arise).

You can continue to work on the assignment after the 50 minutes at your own pace, but the initial 50 minutes will be the main focus of our evaluation. We will be looking at how you approach the problem, how you structure your code, and how you implement the required features.

Please remember that the main focus of this assignment is to evaluate your coding skills and problem-solving abilities. We are not looking for a perfect solution, but rather how you approach the problem and how you implement the required features. We encourage you to write clean, maintainable, and well-documented code.

If you don't complete all the required features within the given time frame, don't worry. We will still evaluate your work based on what you have completed and how you approached the problem.

If you find any issues with the assignment or have any questions, please let us know, we want to make sure you have all the information you need to complete the assignment successfully.

## Our Stack

- React
- Typescript
- Styled Components
- React Router
- SWR
- Redux

This project will have all the necessary dependencies and configurations setup for you, you are free to use any additional libraries or tools that you think will help you complete the assignment.

Your are encouraged to modify the project structure and code as you see fit. We want to see your approach on how to structure a React application and how you implement the required features.

**Important:** Please be aware that adding any additional dependencies or tools may require extra time for setup and integration, so plan accordingly to ensure you can complete the assignment within the given time frame.

**Important:** Moderate use of AI tools (e.g. GitHub Copilot, Claude, ChatGPT) is allowed and reflects real-world development practices. However, we will also evaluate *how* you use AI. We expect you to understand, review, and take ownership of any AI-generated code. Blindly copying output without understanding it will be apparent during the evaluation.

## API

We have provided you with a mock API that you can use to fetch data and make requests. The API is available at `http://localhost:3000` and you can find the documentation for it on `http://localhost:3000/docs`.

To run the API you can use the following command:

```bash
npm run api
```

Please be sure to have the API dependencies installed and running before you start working on the assignment.

### Running without authentication

If you want to skip the login flow and test protected endpoints without needing to call `POST /login` first, you can start the API in no-auth mode:

```bash
npm run api:no-auth
```

When running in this mode:

- All protected endpoints (`POST /bet`, `GET /my-bets`, `DELETE /my-bet/:id`, `GET /my-transactions`) will no longer require an `Authorization` header.
- Requests will automatically be scoped to the first registered player.
- You still need to call `POST /register` once to create a player before using the protected endpoints.
- You do **not** need to call `POST /login` or handle any token — just register a user and start using the protected endpoints directly.
- Since there is no login flow to retrieve the initial balance, you should mock the user's balance either in local component state or in your store.

> **Note:** All API data is stored in memory. If you stop the process and restart it, all previously registered users, bets, and transactions will be lost.

## Required Features

### 1. User Balance

You will need to create a component that displays the user's current balance. This component should be updated whenever the user makes a bet or wins a game.

The component should handle the Brazilian Real currency format.

### 2. Making a Bet

You will need to create a form that that allow a player to bet a certain amount of money, the bet should be subtracted from the user's balance and added to the total bet amount.

The form should call the api endpoint `POST /bet`

After making a bet, there should be a feedback to the user indicating whether the bet was successful or if there was an error (e.g. insufficient balance).

The endpoint will return if the bet was won or lost, if the bet was won the amount won should be added to the user's balance and a feedback should be given to the user indicating that they won and how much they won.

### 3. Bet History

You will need to create a page that displays the user's bet history. This page should show a list of all the bets the user has made, including the amount, the result (win/loss), and the date of the bet.

The list should be paginated.

The list should have filters of type (win/loss) and Id.

The list should fetch from the api endpoint `GET /my-bets`

### 4. Canceling a Bet

You will need to implement a feature that allows the user to cancel a bet that they have made. This should be done by calling the API endpoint `DELETE /my-bet/:id`.

When a bet is canceled, the amount of the bet should be added back to the user's balance and the bet should be removed from the bet history.

## Bonus Features

### 1. Login and Registration

You can implement a login and registration flow for the user. This should be done by calling the API endpoints `POST /register` and `POST /login`.

### 2. List of Wallet Transactions

You will need to create a page that displays the user's wallet transactions. It should use the API endpoint `GET /my-transactions` to fetch the transactions and display them in a list. Each transaction should show the amount, type (bet, win, cancel), and date.

### 3. Responsive Design

You can make the application responsive so that it works well on different screen sizes and devices.

### 4. Token Persistence

You can implement a feature that allows the user to stay logged in even after refreshing the page. This can be done by storing the authentication token in local storage or cookies and checking for it when the application loads.

### 5. Private and Public Routes

You can implement private and public routes in the application. Private routes should only be accessible to authenticated users, while public routes should be accessible to all users.

### 6. WebSocket Integration

You can implement a feature that allows the application to receive real-time updates from the server using WebSockets. This can be used to update the user's balance and bet history in real-time without needing to refresh the page.

### 7. Internationalization (i18n)

You can implement internationalization in the application to support multiple languages. This can be done using libraries like `react-i18next` or `react-intl`.

### 8. Animations and Transitions

You can add animations and transitions to the application to enhance the user experience. This can be done using libraries like `react-spring` or `framer-motion`.

### 9. Theme Switcher

You can implement a theme switcher that allows the user to switch between light and dark themes. This can be done using styled-components' Theming capabilities or by using a state management solution to toggle between themes.

## Delivery

Please submit your completed assignment by sharing a link to a public GitHub repository containing your code. Make sure to include a README file with instructions on how to run the application and any additional notes you think are necessary.
