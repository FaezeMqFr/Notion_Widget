# HTML Widget

## Overview

This repository contains a simple HTML and JavaScript project that displays the current date and weekday in a visually appealing calendar format. The calendar updates automatically every minute to ensure the displayed information is always current.
## Live Demo

You can view the live demo of the widget below:

<iframe src="https://faezemqfr.github.io/Widget/" width="100%" height="500px"></iframe>

## Features

- Displays the current day, month, and year.
- Shows the full weekday name.
- Auto-updates every minute to reflect the current date and time.
- Simple and modern design with a dark-themed calendar.

## Installation

1. Clone the repository to your local machine:
    ```bash
    git clone https://github.com/your-username/date-display-with-weekday.git
    ```
2. Navigate to the project directory:
    ```bash
    cd date-display-with-weekday
    ```

## Usage

1. Open the `index.html` file in your preferred web browser:
    ```bash
    open index.html
    ```

2. The webpage will display the current date and weekday in the calendar format.

## Code Explanation

### HTML Structure

The HTML file contains the basic structure for the webpage, including a `div` element with the class `calendar` that holds the date and weekday information.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Date Display with Weekday</title>
    <style>
        /* CSS styles go here */
    </style>
</head>
<body>
    <div class="calendar">
        <p>
            <div id="day">--</div>
            <div class="separator"></div>
            <div id="month">--</div>
            <div class="separator"></div>
            <div id="year">--</div>
        </p>
        <p>
            <div class="weekday">Weekday</div>
        </p>
    </div>
    <script>
        // JavaScript code goes here
    </script>
</body>
</html>
 ```

## CSS Styling
The CSS provides a modern and clean design for the calendar. The .calendar class styles the calendar container, while individual elements like div and .separator are styled to display the date and weekday correctly.

```
body {
    font-family: 'Arial', sans-serif;
    background-color: none;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}
.calendar {
    background-color: #333;
    color: white;
    padding: 10px;
    border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}
.calendar div {
    font-size: 2em;
    padding: 5px;
    margin: 0 2px;
}
.separator {
    border-left: 2px solid black;
    height: 40px;
    margin: 0 2px;
}
.weekday {
    font-size: 1em;
    margin-top: 5px; /* Add margin to separate from the date elements */
}
```

JavaScript Functionality
The JavaScript code updates the date and weekday elements every minute using the setInterval function. The updateCalendar function gets the current date, formats it, and updates the HTML elements accordingly.

```
// Function to update the calendar
function updateCalendar() {
    const now = new Date();
    const monthNames = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
    const dayElement = document.getElementById('day');
    const weekdayElement = document.querySelector('.weekday');

    // Update the date elements with the current date values
    dayElement.textContent = String(now.getDate()).padStart(2, '0');
    document.getElementById('month').textContent = monthNames[now.getMonth()];
    document.getElementById('year').textContent = now.getFullYear();

    // Update the weekday element with the full weekday name
    weekdayElement.textContent = now.toLocaleDateString('en-US', { weekday: 'long' });
}

// Set an interval to update the calendar every minute
setInterval(updateCalendar, 60000);

// Initial update of the calendar
updateCalendar();
```
