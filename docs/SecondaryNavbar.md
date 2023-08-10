# SecondaryNavbar Component Documentation

## Summary 
The `SecondaryNavbar` component in the given script is a comprehensive Navigation Bar for a Web Application utilizing React.js to link different routes that falls within the predictions of rules, teams, circuits, drivers, chatbot functionality and user-login capability for a Formula 1 themed application.

## Inputs 
This component takes in `tabItems` as a prop, an array of objects. Each object represents a tab in the navigation bar with properties such as `title` and `navigateTo`.

Example of `tabItems`:

```
[
    { title: 'Home', navigateTo: '/home' },
    { title: 'About', navigateTo: '/about' },
    // ... other tabs
]
```

## Parameters 
- `event`: Standard SyntheticEvent passed to event handlers by React.
- `newValue`: The value of the tab that triggered the change event.
- `location`: The useLocation hook returns the state of the current location.
- `navigate`: The useNavigate hook allows for programmatic navigation.

## Outputs
The component renders a navigation bar with each tab corresponding to an item in the `tabItems` array. When clicked, each tab navigates to its corresponding route. 

## Functionality 
The function `getActiveTabIndex` goes through the list of tabs and compares current location's pathname to `navigateTo` property of each tab. If those match, it sets that tab's index to `activeTabIndex` and returns it.

The `handleChange` function sets the value state variable to a new tab index ensuring the correct tab is displayed as active while navigating through the app. 

The `useNavigate` and `useLocation` hooks from `react-router-dom` allow navigation and access to the current page location, ensuring that the current route matches up with the chosen tab index.

The component finally maps `tabItems` to `Tab` components, with a `Link` as the underlying component for each `Tab` so you can directly navigate to each tab's `navigateTo` link on click.