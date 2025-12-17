# Instructions for Automations

## amber_retrieve_data_timer.yaml

You will need to disable the automatic polling of the Amber integration, so you can implement the custom timers of the automation. This automation will hit the Amber API at 14s past every 5 minute period, and keep trying every few seconds until it receives live result. It will then wait until the next 5-minute period.


This greatly improves the time it takes to get a live result, and minimises unnecessary calls to the Amber API.

## amber_curtailment_trigger.yaml

Sets the grid export limit on Sigenergy plant to 0kw during zero or negative feed-in prices, and 20kw when >0.
Amber SmartShift also use this setting to set curtailment. This replicates the Amber Smartshift curtailment feature.
Use the amber_feed_in_price_no_estimates sensor but can use the sensor.your_sensor_name_feed_in_price