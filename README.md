# soaren_ping_tree_assesment

Soaren Ping Tree Assessment
Corey Coole
03-07-2021

	Assessing the data,  request of the task, and total bid amount requirement, it was determined that the most efficient approach to the bidding structure would be a process that optimizes the expected net return for each bid price point per bid. 
	
To begin the task, the data was loaded into a Jupyter Notebook written in python. The data types were found to be as expected, as well as the data missingness was found to be contained completely in the BidPrice column, representing instances that were not bid on. Bidding prices were validated to be as the expected price points. There was a duplicate id that was found, 59826378. It was determined that it was a duplicate row given that each row of the id instance had matching data. In this way, I made the decision to remove one of the duplicate rows from the data. I moved on to create another row in the data that would be the expected return of each bid instance. Some preliminary analysis on the provided data reflected a number of bids had been placed on instances with expected return amounts totally less than the bid price. The net loss on these bids totaled $1055.02. Going forward, it will be important to ensure that bids are only placed on opportunities with an expected return greater than the bid cost. 
	
	To further investigate the data, I compared the expected revenue, expected conversion, and expected return distributions of the accepted and rejected bids. It was found that 55.6% of the total expected net return came from the bids of the 75 group of accepted bids, 37.3% of the total came from the accepted bids at 35, 4.1% came from the accepted bids at 50, and 3% came from the accepted bids at 3. 

	Conducting t-tests with alpha set at the .05 level, I compared the samples of accepted and rejected expected revenue distributions at each bid price, it was found that there was not a significant difference between the distributions at the 75 bid price. However, I did find that the remaining distributions of accepted and rejected expected revenues at 50, 35, and 3 to be statistically distinct. Conducting t-tests at the .05 level comparing expected conversion distributions at each bid price, the results of statistical significance at each bid price mirror the results of the expected revenue distributions. 

	Conducting analysis on the expected return distributions, it was found that the 75 group sample just miss statistical significance at a p-value of .0564. However, the distribution at 50 has been concluded to be statistically distinct. And further, expected return distributions at 35 and 3 were not found to be statistically distinct. Comparing the statistical significance of these distribution sets returns valuable data when determining which distribution groups would be reasonably expected to respond to changes to the bidding model.

 	Exploring the potential modifications to the bidding model started with calculating the expected net return per bid given the example rules provided. The expected return per bid based on the example rule set returns at 59.70 dollars, with a total count of bids placed at 21916. I created a process to increment these thresholds of expected return based on the resulting expected return per bid for each bid price. It was found through multiple iterations that the 35 and 50 expected revenue threshold converged to 650 dollars. I then tested whether removing the 35 price point negatively affected the expected net return per bid. The calculations determined that removing the bid price did not affect the expected net return, so I made the decision to remove it. Thusly, resulting in the final model thresholds of applying the 75 dollar bid if the expected return is greater than 690 dollars, applying the 50 bid when the expected return is greater than 650 dollars, and finally applying the 3 dollar bid when the expected return is greater than 64 dollars. This configuration results in an expected net return per bid of 133.12 dollars for a total of 15,318 bids. 

	In conclusion, if I was to continue on this project, I would like to create a model that would aid in the determination if a proposed bid would be accepted based on previous market history. I feel that such an asset would give a great perspective towards experimenting with different configurations of expected revenue thresholds. 
