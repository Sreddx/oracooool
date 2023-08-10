# SimulationPage Component

## Summary
This is a component in a web application that fetches and displays the characteristics of different Formula 1 teams. 

## Inputs
The SimulationPage component takes one prop:
- `secondaryNavbar`: This is a React component that provides secondary navigation options to the user. 

## Parameters
This component uses state for `teams` which is an array object updated with the fetched team data. The `setTeams` function is used to update the state accordingly.

## Outputs
The component will render a grid interface showcasing different formula 1 teams with their details like image, name, description and car's description.

## Functionality
First, `useState` hook is used to define and manage state for the list of teams.

The `useEffect` hook is then used to fetch details of the teams asynchronously when the component mounts. This makes a GET request to the '/teams' endpoint of an API running at 'http://0.0.0.0:5001'. If the response is positive, the received data is set as the state of `teams` using the `setTeams` function.

The component returns a fragment (`<>`) containing the secondaryNavbar prop and a layout made with the Grid component from the MUI library. 

Each team from the `teams` state is mapped to the dynamic Grid structure which contains team's data. Including team's image, name, the description of the team and the description of the team's car. The `index` of each mapped team and its `name` are used as a unique `key` for each grid item. Appendices to the grid items are styled appropriately with the help of the sx prop of the MUI components.