# Project Themes

Following are some themes you can use as inspiration for projects, but you do not have to necessarily stick to them. The themes are divided into two categories: "Simple" and "Advanced". The "Simple" themes are easier to implement and are more suitable for students who are new to programming. The "Advanced" themes are more challenging and might be suitable for students who have some experience in programming. But the classification is arbitrary, and one's "advanced" might be another's "simple" or the other way around!

## 1. **Detrend timelines** *(Simple)*:

Detrend a time series data set. We are also happy to provide timeseries data, if you don't want to find your own. The detrending can be done using any method, e.g. polynomial fitting, moving average, etc. Provide at least two options to the user to choose the method of detrending. The detrended data should be plotted along with the original data.

Examples:

1. Detrend the global temperature data set for the past 150 years and compare the detrended data with the original data
2. Given the timeline of precipitation data in the Netherlands, detrend the seasonal variation and compare the detrended data with the original data 
 
## 2. **Simple (but chaotic) numerical models** *(Advanced)*:

Develop a simple numerical model. The model should be able to take initial conditions and parameters as input and should be able to simulate the model for a given time period. The model should be able to plot the results.

Examples:

1. Given the initial conditions of a double pendulum, simulate the motion of the double pendulum for a given time period
2. Provided the initial conditions of a predator-prey model, simulate the population dynamics of wolves and rabbits for a given time period
3. Given the initial conditions of a simple (Lorenz 1963) weather model, simulate the weather for a given time period

## 3. **Analyses in frequency domain** *(Advanced)*:

Perform frequency domain analyses on a 1D or 2D data set. The data set can be any data set, e.g. a time series data set, an image, etc. The code should be able to convert the data to frequency domain (e.g. FFT) and then, perform one method of analysis, e.g. filtering, power spectrum analysis, etc. The code should be able to plot the results.

Examples:

1. Characterize the spectra of El Nino and La Nina given historical data
2. Create a low-pass filter to remove high-frequency noise from time-series data
3. Given a 2D portrait image (i.e. clear subject and plain background), identify which frequencies in the image belong to the subject and which belong to the background

## 4. **Access webpages** *(Simple / Advanced)*:

Access a webpage and extract information from it. The webpage can be any webpage, e.g. a news website, a weather website, etc. The code should be able to extract information from the webpage, e.g. the headlines, the weather forecast, etc. The extracted information should be stored in a file.

## 5. **Statistical predictions** *(Simple)*:

For given real-world data, retrieve a statistical model. Compare the performance of the statistical prediction when provided inputs not seen by the statistical model before. Plot the prediction overlaid on actual data.

1. Given annual growth in global GDP and that of the US, predict the price of the iPhone for September 2024.
2. For autumn and winter, given the amount of solar radiation and the temperature recorded in the Netherlands in the past 5 days, predict the rainfall for the next 2 days.

## 6. **Project based on user input** *(Simple)*:

Develop a code that takes user input and makes a decision based on the input or performs quick computations. The decision can be anything, e.g. a decision to select which project theme to work on for a course, a decision to go out or stay in, etc. The code should be able to take multiple user inputs and provide the decision along with a reason for the decision.

Examples:

1. Develop a code that takes a list of expenses borne by roommates (in the form of a CSV), and calculates the amount each roommate owes to the others.
2. Make a decision tree to determine given the symptoms if a patient should be treated as an emergency case or not.

## 7. **Dashboard visualization** *(Simple/Advanced)*:

Make a visualization dashboard for a data set. The data set can be any data set, e.g. a time series data set, a 2D data set, etc. The dashboard should be able to display the data in multiple ways, e.g. a time series plot, a histogram, etc. The dashboard should be able to accommodate user's wishes, such as the number, size and type of plots. It can be interactive, but not necessarily.

Examples:

1. Given global data about cloud amount for the past 20 years, create a dashboard that shows the cloud amount in different regions of the world as maps, as corresponding time-series and as histograms.
2. If provided with sea-ice and shelf-ice data, create a dashboard that shows the variations in ice coverage in the Arctic and Antarctic regions in different ways.

## 8. **Real-time reading and writing data** *(Advanced)*:

Read data from a sensor in real-time and write the data to a file. In this case, the sensor can just be another script creating the data, instead of an actual, physical sensor. The code should be able to read the data from the "sensor" at regular intervals and write the data to a file. The code should also be able to update plots of the data at regular intervals.

Examples:

1. Read the air temperature data from a script that generates temperature data at 10 Hz. Write the data to a file at 1 Hz frequency after a quality check where temperature passes sanity checks in upper and lower bounds.
2. Given the position data of a moving object from a script that generates  data at 1 Hz, compute the velocity and acceleration of the object and write the data to a file at 0.1 Hz frequency.