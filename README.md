# take-home-assessment
A take home assessment designed for Full-stack or Backend developers
## Best matched restaurants
### Introduction
This assessment is designed to test your thinking process and coding skills when facing a real industry problem. We will assess you based on the requirements listed in the problem description below. Please note that we're looking for code that is clean, readable, testable, robust, performant, and maintainable. If you continue to our interview panel stage, we will ask you questions about your implementation.

Since this assessment includes a searching function, we kindly ask you to avoid out of box search engines such as ElasticSearch. Instead, you should write the searching logic by yourself. Other than that, please feel free to use any languages or frameworks you are familiar with. We are focusing on your idea and your code quality, hence will not make judgments on what technologies you choose. All the data you will need in this assessment will be provided to you as **.csv** files.

When you are done, please return the task by email, or via Github. We expect to receive your response within 3 days after you received this assessment.

*Note: We expect you to do this assessment by yourself without other people's help. We ask you to keep this assessment private and not to share it with others. All data provided are fake and used only for this assessment.*

### Find the best-matched restaurants
You have data about local restaurants located near your company, which you can find in the **restaurants.csv** file. You would like to develop a basic search function that allows your colleagues to search those restaurants to help them find where they would like to have lunch. The search is based on five criteria: **Restaurant Name, Customer Rating(1 star ~ 5 stars), Distance(1 mile ~ 10 miles), Price(how much one person will spend on average, $10 ~ $50), Cuisine(Chinese, American, Thai, etc.).** The requirements are listed below.

1. The function should allow users to provide up to five parameters based on the criteria listed above. *You can assume each parameter can contain only one value.*
2. If parameter values are invalid, return an error message.
3. The function should return up to five matches based on the provided criteria. If no matches are found, return an empty list. If less than 5 matches are found, return them all. If more than 5 matches are found, return the best 5 matches. The returned results should be sorted according to the rules explained below. Every record in the search results should at least contain the restaurant name.
4. “Best match” is defined as below:
   - A Restaurant Name match is defined as an exact or partial String match with what users provided. For example, “Mcd” would match “Mcdonald’s”.
   - A Customer Rating match is defined as a Customer Rating equal to or more than what users have asked for. For example, “3” would match all the 3 stars restaurants plus all the 4 stars and 5 stars restaurants.
   - A Distance match is defined as a Distance equal to or less than what users have asked for. For example, “2” would match any distance that is equal to or less than 2 miles from your company.
   - A Price match is defined as a Price equal to or less than what users have asked for. For example, “15” would match any price that is equal to or less than $15 per person.
   - A Cuisine match is defined as an exact or partial String match with what users provided. For example, “Chi” would match “Chinese”. You can find all the possible Cuisines in the **cuisines.csv** file. *You can assume each restaurant offers only one cuisine.*
   - The five parameters are holding an “AND” relationship. For example, if users provide Name = “Mcdonald’s” and Distance = 2, you should find all “Mcdonald’s” within 2 miles.
   - When multiple matches are found, you should sort them as described below.
     - Sort the restaurants by Distance first.
     - After the above process, if two matches are still equal, then the restaurant with a higher customer rating wins.
     - After the above process, if two matches are still equal, then the restaurant with a lower price wins.
     - After the above process, if two matches are still equal, then you can randomly decide the order.
     - Example: if the input is Customer Rating = 3 and Price = 15. Mcdonald’s is 4 stars with an average spend = $10, and it is 1 mile away. And KFC is 3 stars with an average spend = $8, and it is 1 mile away. Then we should consider Mcdonald’s as a better match than KFC. (They both matches the search criteria -> we compare distance -> we get a tie -> we then compare customer rating -> Mcdonald’s wins)
5. The final submitted work should include a README file. No UI is required in this assessment, but you may implement one if you would like. **The steps to run and test your program should be clearly introduced in the README file.** If you have made any additional **Assumptions** besides what we have listed above while working on this assessment, please document them so that we can better understand your solution.
