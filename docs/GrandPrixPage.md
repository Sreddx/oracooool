## Summary

This is a React component for the SimulationPage in a Formula 1 information and prediction application that allows users to select a specific track, view detailed information about it, and make predictions.

## Inputs

The SimulationPage component accepts the following input:

- `secondaryNavbar`: An optional component to be rendered above the main content.

## Parameters

The SimulationPage component uses the following state variables:

- `selectedTrackId`: Identifier of the currently selected track.
- `trackOptions`: An array of track objects that users can select from.
- `trackDetails`: An object containing detailed information about the currently selected track.

The component also declares several functions:

- `fetchCircuits`: An asynchronous function that fetches circuit data from a server endpoint.
- `handleTrackSelect`: Changes the `selectedTrackId` and `trackDetails` state variables according to user selection.
- `handlePredictClick`: Handles the action performed when the user clicks the “Show details” button.

## Outputs

This component renders a layout containing a selection dropdown with track options, a "Show Details" button that reveals detailed information about the selected track, and showcases track information such as its image, city, country, and length.

## Functionality

The `useEffect` hook is used to fetch circuit data when the component mounts. 
If the network request is successful, the retrieved data is stored in 'trackOptions' for future rendering in the track selection dropdown menu.

The `handleTrackSelect` function updates the state when a new track is selected from the dropdown, updating both the `selectedTrackId` and `trackDetails`.

The `handlePredictClick` function is responsible for initiating a prediction task when the user clicks "Show Details". This function currently remains to be fully implemented.

The render method constructs and returns an interactive form-like interface featuring track selection and further details about the selected track displayed in a separate section of the page. It efficiently updates this interface based on changes in component state, especially `trackDetails` and `selectedTrackId`.