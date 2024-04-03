# Chart Options

The Glint Analytics platform offers eight distinct chart options for visual representation of queried data and metrics. Users can use any combination of these chart types to express trending data on their dashboard.

Alongside the basic, default chart settings that are automatically applied in the querying process, users may also enter into the `Advanced Settings` menu to further calibrate the chart to their needs.

![Advanced Settings](/images/advanced-settings.png)

All example charts in this document can be found in the [Tutorial Dashboard](https://github.com/ACStoneCL/glint-docs/blob/main/beta.glintanalytics.com/users/ACStone/dashboards/tutorial-dashboard).

## Chart Types

- [Column Chart](#column-chart)

- [Line Chart](#line-chart)

- [Area Chart](#area-chart)

- [Pie Chart](#pie-chart)

- [Scatter Chart](#scatter-chart)

- [Race Chart](#race-chart)

- [Animated Line Chart](#animated-line-chart)

- [Tables](#tables)

## Column Chart

![Column Chart](/images/column-chart.png)

![Column Chart Example](/images/column-chart-example.png)

The example column chart shown above displays the number of Ethereum transactions for each month in the year of 2023. It was generated using the following SQL code:

```sql
SELECT DATE_TRUNC('month', ethereum_transaction_timestamp) AS month,
       COUNT(*) AS transaction_count
FROM ethereum_schema.ethereum_transactions
WHERE ethereum_transaction_timestamp >= '2023-01-01' AND ethereum_transaction_timestamp < '2024-01-01'
GROUP BY 1
ORDER BY 1;
```

Column charts offer the following advanced settings:

- `X-Axis` This drop down chooses which data set will make up the X-Axis(Horizontal) of the chart.

    - `Y-Axis` This drop down chooses which data set will make up the Y-Axis (Vertical) of the chart.

    - `Group By` This drop down chooses a third data set to group information within each column.

    - `Series` This option allows you to choose a data set to use as a series to organize the columns.

- `Stacking` Offers three options to stack data within each column:

    - `None` Data is not stacked, but grouped in a series of columns.

    - `Normal` Overall column height is represented as the combined value of the grouped data within the column.

    - `Percent` All columns are equal, but the subdivisions represent percentage of the total value for that data point.

- `Direction` This changes the visual representation of the columns. `Vertical` shows vertical columns, where `Horizontal` shows horizontal columns.

- `X-Axis Label` This box allows you to enter a custom label for the X-Axis that will replace the name of the data set used for the axis.

- `X-Axis Type` This drop down allows you to choose between grouping columns by `Datetime` for time or `Category` for another means of grouping data.

- `X-Axis Time Unit` Allows you to choose a specific unit of time for grouping columns that may be different than the specific data set.

- `Y-Axis Label` This box allows you to enter a custom label for the Y-Axis that will replace the name of the data set used for the axis.

- `Y-Axis Type` This drop down allows  you to choose the scale used on the Y-Axis from the following options:

    - `Linear` A standard linear scale that uses equidistant intervals.

    - `Logarithmic` A logarithmic scale that shows intervals as exponentially increasing over time.

    - `Datetime` A scale of time.

- `3D` These three sliders allow you to shift the view of your chart for a more dynamic visual representation.

    - The first slider changes the `angle`, with the left side of the scale being straight on and the right side being a view from above.

    - The second slider changes the `rotation`, with the left side show the left of the chart closer and the right side of the slide showing the right side of the chart closer.

    - The third slider changes the `focal length` with the left side of the slider pushing the focal length back and the right side bringing it closer.

## Line Chart

![Line Chart](/images/line-chart.png)

![Line Chart Example](/images/line-chart-example.png)

The example line chart shown above displays the price of Bitcoin beginning in April of 2023. It was generated using the following SQL code:

```sql
SELECT DATE_TRUNC('month', price_date) AS month, AVG(price) AS bitcoin_value
FROM coingecko.prices
WHERE coin_id = 'bitcoin'
AND price_date >= DATEADD(year, -1, GETDATE())
GROUP BY DATE_TRUNC('month', price_date)
ORDER BY month;
```

Line charts offer the following advanced settings:

- `X-Axis` This drop down chooses which data set will make up the X-Axis(Horizontal) of the chart.

    - `Y-Axis` This drop down chooses which data set will make up the Y-Axis (Vertical) of the chart.

    - `Group By` This drop down chooses a third data set to group information within each line.

    - `Series` This option allows you to choose a data set to use as a series to organize the lines.

- `X-Axis Label` This box allows you to enter a custom label for the X-Axis that will replace the name of the data set used for the axis.

- `X-Axis Type` This drop down allows you to choose between grouping lines by `Datetime` for time or `Category` for another means of grouping data.

- `X-Axis Time Unit` Allows you to choose a specific unit of time for the X-Axis that may be different than the specific data set.

- `Y-Axis Label` This box allows you to enter a custom label for the Y-Axis that will replace the name of the data set used for the axis.

- `Y-Axis Type` This drop down allows  you to choose the scale used on the Y-Axis from the following options:

    - `Linear` A standard linear scale that uses equidistant intervals.

    - `Logarithmic` A logarithmic scale that shows intervals as exponentially increasing over time.

    - `Datetime` A scale of time.

- `3D` These three sliders allow you to shift the view of your chart for a more dynamic visual representation.

    - The first slider changes the `angle`, with the left side of the scale being straight on and the right side being a view from above.

    - The second slider changes the `rotation`, with the left side show the left of the chart closer and the right side of the slide showing the right side of the chart closer.

    - The third slider changes the `focal length` with the left side of the slider pushing the focal length back and the right side bringing it closer.

## Area Chart

![Area Chart](/images/area-chart.png)

![Area Chart Example](/images/area-chart-example.png)

The example area chart above shows trade volumes on the KuCoin, Bithumb and Gate.io exchanges through 2023. It was generated using the following SQL code:

```sql
SELECT exchange, DATE_TRUNC('month', volume_by_exchange_time) AS month, SUM(volume) AS total_volume
FROM volume_by_exchange
WHERE exchange IN ('kucoin', 'gate.io', 'bithumb') AND EXTRACT(year FROM volume_by_exchange_time) = 2023
GROUP BY exchange, month
ORDER BY exchange, month;
```

Area charts offer the following advanced settings:

- `X-Axis` This drop down chooses which data set will make up the X-Axis(Horizontal) of the chart.

    - `Y-Axis` This drop down chooses which data set will make up the Y-Axis (Vertical) of the chart.

    - `Group By` This drop down chooses a third data set to group information within each area.

    - `Series` This option allows you to choose a data set to use as a series to organize the areas.

- `X-Axis Label` This box allows you to enter a custom label for the X-Axis that will replace the name of the data set used for the axis.

- `X-Axis Type` This drop down allows you to choose between grouping lines by `Datetime` for time or `Category` for another means of grouping data.

- `X-Axis Time Unit` Allows you to choose a specific unit of time for the X-Axis that may be different than the specific data set.

- `Y-Axis Label` This box allows you to enter a custom label for the Y-Axis that will replace the name of the data set used for the axis.

- `Y-Axis Type` This drop down allows  you to choose the scale used on the Y-Axis from the following options:

    - `Linear` A standard linear scale that uses equidistant intervals.

    - `Logarithmic` A logarithmic scale that shows intervals as exponentially increasing over time.

    - `Datetime` A scale of time.

- `3D` These three sliders allow you to shift the view of your chart for a more dynamic visual representation.

    - The first slider changes the `angle`, with the left side of the scale being straight on and the right side being a view from above.

    - The second slider changes the `rotation`, with the left side show the left of the chart closer and the right side of the slide showing the right side of the chart closer.

    - The third slider changes the `focal length` with the left side of the slider pushing the focal length back and the right side bringing it closer.

## Pie Chart

![Pie Chart](/images/pie-chart.png)

![Pie Chart Example](/images/pie-chart-example.png)

The example pie chart shows trade volumes on the Binance, KuCoin, Gate.io and Bithumb exchanges. It was generated using the following SQL code:

```sql
SELECT exchange, SUM(volume) AS total_volume
FROM volume_by_exchange
WHERE exchange IN ('binance', 'gate.io', 'kucoin', 'bithumb')
GROUP BY exchange;
```

Pie charts offer the following advanced settings:

- `Series` This option allows you to choose a data set to use as a series to organize the slices.

- `Values` This option allows you to choose which values will be used to calculate slice size.

- `Donut` This option allows you to create a space on the interior of the pie, converting it to a donut. The slider increases or decreases the internal blank space. Placing the slider to the left will be closer to a pie shape, while the right will give you a thinner ring.

- `Label Position` This slider shifts the label positions from the interior of the pie chart on the left to the exterior at the far right.

- `Border Radius` This slider shifts the border of the individual slices. At the left, it will be a continuous ring. On the right, it will form a rounded edges for each slice.

- `Shadowed` This option will place a shadow beneath the pie chart to aide in visual clarity.

- `3D Depth` Enabling this option will switch the pie chart view to a higher angle, looking down on the chart. The slider will change the chart's thickness.

## Scatter Chart

![Scatter Chart](/images/scatter-chart.png)

![Scatter Chart Example](/images/scatter-chart-example.png)

The example scatter chart shown above displays the price of Bitcoin Cash over the past 60 days. It was created using the following SQL code:

```sql
SELECT price, price_date
FROM coingecko.prices
WHERE coin_id = 'bitcoin-cash'
AND price_date >= CURRENT_DATE - INTERVAL '60 days';
```

Scatter charts offer the following advanced settings:

- `X-Axis` This drop down chooses which data set will make up the X-Axis(Horizontal) of the chart.

    - `Y-Axis` This drop down chooses which data set will make up the Y-Axis (Vertical) of the chart.

    - `Group By` This drop down chooses a third data set to group information within each scatter plot.

- `X-Axis Label` This box allows you to enter a custom label for the X-Axis that will replace the name of the data set used for the axis.

- `X-Axis Type` This drop down allows you to choose between plotting dots by `Datetime` for time or `Category` for another means of grouping data.

- `X-Axis Time Unit` Allows you to choose a specific unit of time for the X-Axis that may be different than the specific data set.

- `Y-Axis Label` This box allows you to enter a custom label for the Y-Axis that will replace the name of the data set used for the axis.

- `Y-Axis Type` This drop down allows  you to choose the scale used on the Y-Axis from the following options:

    - `Linear` A standard linear scale that uses equidistant intervals.

    - `Logarithmic` A logarithmic scale that shows intervals as exponentially increasing over time.

    - `Datetime` A scale of time.

- `3D` These three sliders allow you to shift the view of your chart for a more dynamic visual representation.

    - The first slider changes the `angle`, with the left side of the scale being straight on and the right side being a view from above.

    - The second slider changes the `rotation`, with the left side show the left of the chart closer and the right side of the slide showing the right side of the chart closer.

    - The third slider changes the `focal length` with the left side of the slider pushing the focal length back and the right side bringing it closer.

## Race Chart

![Race Chart](/images/race-chart.png)

![Race Chart Example](/images/race-chart-example.png)

The example race chart shown above will show the progressive price of exchange tokens KCS, UNI, CAKE and GATE over the course of the first quarter of 2024. It can be viewed in motion in the [Tutorial Dashboard](https://github.com/ACStoneCL/glint-docs/blob/main/beta.glintanalytics.com/users/ACStone/dashboards/tutorial-dashboard). It was generated with the following SQL code:

```sql
SELECT *
FROM coingecko.prices
WHERE coin_id IN ('kucoin-shares', 'uniswap', 'pancakeswap-token', 'gate-token')
AND price_date BETWEEN '2024-01-01' AND '2024-03-01'
ORDER BY coin_id, price_date;
```

Race charts offer the following advanced settings:

- `Time X-Axis` This drop down chooses the data set that will be used to depict time passing, or the 'race' for the chart.

- `Bars` Determines what data will be used to form the racing bars within the chart.

- `X-Axis` This drop down chooses which data set will make up the X-Axis(Horizontal) of the chart.

    - `Group By` This drop down chooses a third data set to group information within each bar.

    - `Series` This option allows you to choose a data set to use as a series to organize the bars.

- `Stacking` Offers three options to stack data within each bar:

    - `None` Data is not stacked, but grouped in a series of bars.

    - `Normal` Overall bar height is represented as the combined value of the grouped data within the bar.

    - `Percent` All bars are equal, but the subdivisions represent percentage of the total value for that data point.

- `Shown bars number` This option determines how many bars will natively be shown our of a larger data set. Example: If there are five potential bars, but this is set to `3`, it will only show the top three at any given time.

- `Direction` This changes the visual representation of the bars. `Vertical` shows vertical bars, where `Horizontal` shows horizontal bars.

- `X-Axis Label` This box allows you to enter a custom label for the X-Axis that will replace the name of the data set used for the axis.

- `X-Axis Type` This drop down allows you to choose between grouping bars by `Datetime` for time or `Category` for another means of grouping data.

- `X-Axis Time Unit` Allows you to choose a specific unit of time for grouping bars that may be different than the specific data set.

- `Y-Axis Label` This box allows you to enter a custom label for the Y-Axis that will replace the name of the data set used for the axis.

- `Y-Axis Type` This drop down allows  you to choose the scale used on the Y-Axis from the following options:

    - `Linear` A standard linear scale that uses equidistant intervals.

    - `Logarithmic` A logarithmic scale that shows intervals as exponentially increasing over time.

    - `Datetime` A scale of time.

- `3D` These three sliders allow you to shift the view of your chart for a more dynamic visual representation.

    - The first slider changes the `angle`, with the left side of the scale being straight on and the right side being a view from above.

    - The second slider changes the `rotation`, with the left side show the left of the chart closer and the right side of the slide showing the right side of the chart closer.

    - The third slider changes the `focal length` with the left side of the slider pushing the focal length back and the right side bringing it closer.

## Animated Line Chart

![Animated Line Chart](/images/animated-line-chart.png)

![Animated Line Chart Example](/images/animated-line-chart-example.png)

The example line chart shown above displays the price of Ethereum through the first quarter of 2024. It can be viewed in motion in the [Tutorial Dashboard](https://github.com/ACStoneCL/glint-docs/blob/main/beta.glintanalytics.com/users/ACStone/dashboards/tutorial-dashboard). It was generated with the following SQL code:

```sql
SELECT price, price_date
FROM coingecko.prices
WHERE coin_id = 'ethereum'
AND price_date >= '2023-12-01'
AND price_date < '2024-03-01';
```

Animated line charts offer the following advanced settings:

- `X-Axis` This drop down chooses which data set will make up the X-Axis(Horizontal) of the chart.

    - `Y-Axis` This drop down chooses which data set will make up the Y-Axis (Vertical) of the chart.

    - `Group By` This drop down chooses a third data set to group information within each line.

    - `Series` This option allows you to choose a data set to use as a series to organize the lines.

- `X-Axis Label` This box allows you to enter a custom label for the X-Axis that will replace the name of the data set used for the axis.

- `X-Axis Type` This drop down allows you to choose between grouping lines by `Datetime` for time or `Category` for another means of grouping data.

- `X-Axis Time Unit` Allows you to choose a specific unit of time for the X-Axis that may be different than the specific data set.

- `Y-Axis Label` This box allows you to enter a custom label for the Y-Axis that will replace the name of the data set used for the axis.

- `Y-Axis Type` This drop down allows  you to choose the scale used on the Y-Axis from the following options:

    - `Linear` A standard linear scale that uses equidistant intervals.

    - `Logarithmic` A logarithmic scale that shows intervals as exponentially increasing over time.

    - `Datetime` A scale of time.

- `3D` These three sliders allow you to shift the view of your chart for a more dynamic visual representation.

    - The first slider changes the `angle`, with the left side of the scale being straight on and the right side being a view from above.

    - The second slider changes the `rotation`, with the left side show the left of the chart closer and the right side of the slide showing the right side of the chart closer.

    - The third slider changes the `focal length` with the left side of the slider pushing the focal length back and the right side bringing it closer.

## Tables

![Table](/images/table.png)

![Table](/images/table-example.png)

The example table shown above displays the all-time high prices for the top ten coins available in the database. It was generated using the following SQL code:

```sql
SELECT coin_id, MAX(price) AS all_time_high_price
FROM coingecko.prices
GROUP BY coin_id
ORDER BY all_time_high_price DESC
LIMIT 10;
```

There are no advanced settings for tables and they are identical to the `Chart data` available in the visualization creation tab.