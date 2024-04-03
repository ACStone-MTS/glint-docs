# Quickstart Guide for Glint Analytics

Glint Analytics is a web-based platform for developing comprehensive analytical dashboards within the Web3 ecosystem. Using natural language queries, users with no prior coding knowledge can create visually appealing dashboards that convey critical information on some of the industry's top blockchains.

This quickstart guide outlines the initial steps for a new user looking to dive into their first Glint experience.

## Contents

1. [Creating your Glint Account](#1-creating-your-glint-account)

2. [The Glint Landing Page](#2-the-glint-analytics-landing-page)

3. [Querying Blockchain Data and Metrics](#3-querying-blockchain-data-and-metrics)

4. [Creating your First Visualization](#4-creating-your-first-visualization)

5. [Creating your First Dashboard](#dashboard)

6. [Next Steps](#nextsteps)

## 1. Creating your Glint Account

Access to the Glint platform currently requires joining the [Waitlist](https://www.glintanalytics.com/waitlist) on the main landing page.

The button can be found in the upper right, and you will be required to enter your **Name**, **Email Address** and the **Region** you are currently in.

Glint will respond to your request as soon as we are able, and dependent on your eligibility to join the early access program.

## 2. The Glint Analytics Landing Page

After gaining access and signing in, you will be brought to the **Discover** landing page, which showcases some of the most popular user-generated dashboards. These dashboards are curated data presentations, voted on by the community and available to browse.

Clicking the star toggle will add a dashboard to your favourites, which may be viewed in the "*My favourites*" tab shown in the upper left of the landing page. You can also view any dashboards you've created in the "*My dashboards*" tab.

To create your own visualization and dashboards, click the "*Create*" tab in the upper right of the landing page.

## 3. Querying Blockchain Data and Metrics

Glint provides two input options for users querying data:

### The Glint AI Assistant

The Glint AI Assistant provides users a no-code option for creating data-driven visualizations. Users can input natural language requests, and the AI assistant will convert these requests to SQL and create visuals based on the AI-generated code.

The AI Assistant appears in the upper left of the "Visual Editor" page.

![The Glint AI Assistant](/images/ai-assistant.png)

You'll see two icons in the upper right of the AI assistant window, a sweeping icon and an expansion icon. The sweeping icon removes all previous queries from the window. The expansion icon will expand the window, removing the SQL query and chart visual windows from view.

The AI assistant will build upon previous prompts, if they are not removed. If you find a sequence of queries unsuccessful, it can be useful to clear the prompt history to start from zero.

#### Examples

Several examples are provided above the query entry box and may be used as a guide for proper AI-prompt structure. For example, entering the query:

*"Show me the liquidity of each chain."*

Will return a chart showing the total liquidity available for every chain tracked by Glint's database.

When working with the AI assistant, you may need to try several prompts to get the exact data and representation you are looking for. As an example, querying:

*"Show me the price of ETH for each day of February"*

Will return the Ethereum prices for each day of February, for each year going back to the start of the database. In contrast, querying:

*"Show me the daily price of ETH for February 2024"*

Returns only the prices for each day in February of 2024.

### The SQL Query Window

To the right of the AI assistant window is the Redshift SQL Query window.

![Redshift SQL Query](/images/sql-query.png)

The Redshift SQL Query window serves two purposes:

- It allows the user to view the AI generated SQL that will be used to produce a visual chart.

- It allows advanced users to input SQL directly.

In the upper right of the window, there is a magnifying glass icon and an expansion icon.

The magnifying glass icon will expose the schema of data available for use in chart visualizations. This can be helpful for forming queries in the AI assistant, or for creating your own SQL code.

The expansion icon will expand the SQL query window at the cost of removing the AI assistant and chart visualization windows.

## 4. Creating your First Visualization

Entering a query in the AI assistant or hitting the `Run` button on the SQL query window will generate a chart visual in the lower window. To the right of the **Chart visual** tab, you will see **Chart data**, which shows the imported data in an easily human-readable table and can be used to determine the best visual chart type.

By default, this will be shown as a "Column Chart", but you can choose from a variety of visual representations through the dropdown menu to the right of the chart visual window. These visual representations and their advanced settings are described at length in the [Chart Options](tbd) documentation. Below the chart type, another drop down menu allows you to customize the color and brightness of the presented data.

The expansion icon in the upper right allows you to expand the chart visual at the cost of removing the AI assistant and SQL query windows from view. In the lower right, there is an indicator of the data's refresh time. Clicking it will refresh the data immediately.

If you are satisfied with the chart as provided, you can enter a descriptive name for the chart in the upper right under "My visuals". Clicking save well then store the new visualization under "My visuals" for future reference and use in the **Dashboard editor**

## 5. Creating your First Dashboard

After creating any visualizations you may need, you can click on the **Dashboard Editor** tab in the upper left of the page to move into the [WYSIWYG-style](https://en.wikipedia.org/wiki/WYSIWYG) editor for creating data presentations.

Clicking `Create` on the right of the editor will open a blank Dashboard, as well as listing all previously created visualizations under **"My visuals"** on the right side of the screen.

You can click-and-drag any visualizations from this list onto the available space. Once placed on the dashboard, you can increase or decrease their size by clicking along the exterior border of the widget. With a widget selected, you can change the title and add or remove the border and title from the right hand window.

Clicking anywhere outside the widget will deselect it and allow you to add additional visualizations.

The **"Other visuals"** tab will allow you to include text or images that are not connected to your visual charts, which can be used to create a more visually appealing dashboard - or to present static information as necessary.

As with your visualizations, once you are satisfied with the layout you've created you can enter a name and save the new dashboard, which will then appear on the left side of the screen in a visual list of your dashboards when viewing the **Dashboard Editor**.

The `Preview` button allows you to view created dashboards as they will appear to others. You can also choose to make any dashboard private by toggling the `Private Dashboard` button.

## 6. Next Steps

After familiarizing yourself with the basic features of both the **Visual Editor** and **Dashboard Editor**, you can view more in-depth documentation on the following topics:

- [Chart Options](tbd)
- [Leaderboard Mechanics and the Glint Community](tbd)