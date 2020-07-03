# Smart-Grid-Data-Analysis

What is Smart Grid? 
Let’s understand this by breaking up these two words. Starting with ”Smart” which means anything which can communicate in a two way form or in which the communication is bi-directional. 
For example our smartphones, smart T.V’s, smart-watches, etc. Another terminology is ”Grid” which is a network of an electricity consisting of power and providers which are synchronized. It also consists of user who are joined via transmission and distribution lines and are controlled by one or more control centres.
So, In Smart Grid the catch is that we have bi-directional communication between utility (Electricity Service Provider) and user, possible by the presence of PLC (PowerLine Carrier). 
The transmitting lines are used for sending both data and electricity at the same time. Due to which the grid monitoring and smart metering has been a boom to energy sector, as in grid monitoring the utility gets to know the amount of electricity consumed by the user in real time. 
Alongside, it also helps in scenario where there is a power breakdown in an area which can be measured by utility. In case of smart metering the user gets to know about the amount of energy consumed by them.

# Motivation

Motivation has been to improve the utilization of electricity in an efficient way considering the bi-directional communication, will actually help utility to identify and predict which components are likely to fail.  Since the monitoring of low/medium/high voltage is possible throughout this communication infrastructure which helps in reducing the energy losses in the network. 
Eventually helps in lowering down the carbon fuel consumption and lowers down the green house effects. Alongside, also helps to gain productivity and decrease the deployment and operational cost. But, the main motivation on top of everything is to increase the customer experience by improving the services offered, introducing the new services, improving the service reliability and quality to consumers. It would enable options for renewable generation and provide customers with the awareness and capabilities to reduce their energy consumption which would help them to reduce the cost. 
Motivation has also been helping out appliance production companies to increase their productivity.

# Objective
The objective of this research are as follows:-

i) Appliance Prediction – On the basis of energy consumed by an individual consumer,
we can eventually predict the specific appliances used by a consumer. It would be
helping out appliance producing companies to achieve targeted advertising of appliance
specific to season of the year.

ii) Energy consumption by individual appliance – We also want to predict the energy
consumed by a single appliance in order to predict whether the consumer should upgrade their appliance or not, which would eventually help to reduce cost and power
consumption.

iii) Predicting Star Rating of an individual appliance – We aim to predict the star rating
of an individual appliance as well, reason being if a consumer is using an appliance
with a lower star rating, he/she would be actually generating higher electricity cost, so
we can suggest them to switch to an appliance with a higher star rating and how much
cost would it be saving.

iv) Targeted Marketing For Appliance Developing Companies – The prediction of star
rating could actually help companies to predict that how many people would be possibly
opting to upgrade to a appliance with a higher star rating, so they can accordingly target
their sales.

# Work Done

The primary goal is to help out people to identify and understand their energy spending. The user would be able to identify how much energy is consumed by each of their household appliances. In, case the energy consumed by the appliance is more then what it should be really consuming, leading to the increase in overall cost of energy. For, which we started with exploring the field of Smart Grid, what it really is, what sort of hardware is required, and what sort of data is being generated, etc. Since analytics from data science is next big thing, we thought of finding the solution through analytics. 
For which we started exploring for public energy datasets. We came across many of them like:- REDD, GREEND, EMBED, AMPds, etc. These datasets comes under eventless categories, containing aggregated energy consumption, which makes them compatible for using them concurrently for both as testing and training data. 

The characteristics of the dataset are the key for the approach towards the solution. So, below mentioned are the characteristics that are usually watched carefully for each
dataset.
1. Released Year
2. Country
3. Total number of household considered
4. Continuous or Non continuous data, i.e, whether the data was received in successive time intervals, or does it had more gaps then specified.
5. Event based — EB or Event-less — EL data
6. Varieties of smart meters used for the purpose of data collection (aggregate, individual circuit, and if a list of power event labels is available)
7. Features of electric energy:-(current, voltage, active power, reactive power, apparent power), and
8. Time resolution

Implementing the raw data set on the NILM toolkit, which provides us with the FHMM and CO for the implementation. We considered CO for our experiment, to find
out the energy dissaggregation of each appliance and energy consumed by each of them.
Combinatorial Optimization helps in finding the optimal set of combination of appliance states, which further minimises the difference between the sum of the predicted appliance power and the observed aggregate power, in order to a set of appliance models.
Each time slice is assumed to be independent in CO. For the measuring the accuracy of which we considered two appliances:- Fridge and Microwave, for which we got the
accuracy as 58% and 66%. Further for the improvement in terms of accuracy we started with preprocessing of our data where we followed below mentioned strategies:-

1. Detection of gaps in the dataset - There can be a certain amount of gap which is being generated when the sensors are turned off and then on. So, we can remove
gaps, so as to get an contiguous stream of data.

2. Maintaining Up-Time - Up time is total amount of time for which the sensor was on. It can be obtained by subtracting the first recorded time stamp from last
recorded time stamp, and further subtraction duration of gaps from it.

3. Normalization of Voltage - Different places have different amount of voltage fluctuations. So, as to have a control over these voltage fluctuations as they can significantly impact for a power draw.

4. Top-k appliances - By considering the top-k energy consuming appliances instead
of considering all the appliances. As, the disaggregation of the appliances having
highest consumption provides with the most value. Also, by extracting out the
remaining appliances can help us in order remove noise and helps us to improve
our accuracy.

After, pre-processing the data and further implementing it to NILM, we got an improved accuracy for the fridge and microwave to be 63% and 72%. So, finally we are
having a list of appliances the are being used in a household along with it’s energy consumption.
