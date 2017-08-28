# Real Time Electricity Forecaster

The purpose of this application is to present a simple way to forecast future energy consumption based on data received from an MQTT stream from an electricity meter. The application will publish its generated forecast to a new MQTT stream which can be used by a utility provider to manage their electricty production. This example uses a locally hosted MQTT system and uses an example set of data. It uses polynomial fitting to predict the next data. In the future this application can be extended using a trained model abtained through using machine learning techniques to more accurately predict future consumption. 
 

## Getting Started

### Prerequisites

For the forecaster to work, you must ensure that you have the appropriate dependencies. 

Python 2.7, Mosquitto, paho-mqtt, numpy

### Setting up local MQTT system

Run a local mosquitto server by entering the following command:
```
	mosquitto
```
Subscribe to MQTT stream of energy production forecasts by opening a terminal window and typing the following command:
```
	mosquitto_sub -v -t 'predictions/lyse-test-01'
```

### Running the application

Run the forecasting application by entering the following command:
```
	python forecaster.py
```
Finally start publishing energy consumption data every 10 seconds to an MQTT stream by entering the following command into a new terminal window:
```
	python publisher.py
```
The output from the publisher should now appear on the mqtt subscriber. 


## Testing the application

The following test datasets will be provided: 

- sinusoidal consumption
- linear increasing consumption
- gausiann distributed consumption 


## Authors

* **Eirik Johannes Ramstad** 


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details