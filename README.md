**Project Overview:**

CyberSecurity_JobScaper is a job search and data collection scraper specifically built for entry-level cybersecurity jobs. It uses the Jobs API, a worldwide job finder on RapidAPI that can effortlessly retrieve an extensive list of employment opportunities from a diverse array of renowned providers.

**Features:**

1. **Fetching Jobs from Multiple Providers**: Through the Jobs API and the requests library, the script sends a GET request to multiple job providers and retrieves data from each site based on the search query (e.g. entry-level cyber security).

2. **Extracting the Data:** The job information obtained is then organized into JSON format and for each job listing, the script extracts relevant information like job title, company, job description, and more.

3. **Saving the Data:** The script then saves all of this data in a CSV file called ‘jobscraper_results’. Each time it saves 10 jobs into CSV file at a time.


**Requirements:**

- Python 3.9+
- Works on windows
- Installed libraries:
  - Requests
  - Pandas
  - To install the required libraries:
    - Pip install requests
    - Pip install pandas

**API Key:**

Since the script uses JobsAPI on Rapid API, you’ll be required to:

- Create an account on the RapidAPI website, search for and subscribe to the Jobs API
- Obtain your API key from your account to be added to the ‘headers’ section of the script.

**Usage:**

1. Download the repository.
2. Open the script and replace **‘place your api key here’** with your RapidApi key in the headers section shown below.

headers = {

   "x-rapidapi-key": "place your api key here",

  "x-rapidapi-host": "jobs-api14.p.rapidapi.com",

}

3. By editing the **‘querystring’** parameter, you can change each of the boundaries to retrieve different job roles, change the location of your search and more.

4. Run the script with python.

5. The API saves a maximum of 10 jobs in a single request. To loop through multiple pages of jobs, increase **‘index’** by increments of 1 in **‘querystring’** and run the script again. For e.g an index of ‘0’ gives the first page of 10 job results, an index of 1 will give the next page of 10 job results and so on.


**Output:**

Each job and its associated details will be saved in the CSV file as shown in the snippet below:

Job Title	        Company	   Location	  Employment Type	 Description	 Salary	   Posted     URL
Security Analyst	TechCorp	 Remote	    Full-time	   Analyze...   $70K-$90K/year 2 days ago	Link
Penetration Tester	CyberSafe	 NY	        Internship	    Penetration...	 N/A	   5 days ago	Link


**Precautions/Considerations**

- As this scraper pulls from multiple job sites, be careful not to run the script too often as you may risk violating a site’s terms of service and being blocked from pulling data
- If you subscribe to the free plan of JobsAPI, be sure to monitor the API usage on your account as the free subscriptions come with usage limits.
- This API may sometimes not pull data on salaries as the employers themselves may not have posted them or they might be located in the job description


**Prompt Engineering Techniques:**

As this webscraper was developed with some input from AI models such as ChatGPT, good prompt engineering practices were required to get the best possible results. Some of the that would have been used are as follows:

**Structuring prompts such that they are clear, precise and provide context when necessary**: Providing the AI model with prompts that have specific instructions help it to narrow its scope and provide more relevant information.  For example, in this exercise, simply asking the ChatGPT to “Write some code to make a webscraper”, would not yield significant enough results to progress with the task. This is as opposed to ‘Write a python script that can be used to scrape LinkedIn for jobs. The webscraper should pull information on open cyber security job lisitngs along with details such as location, experience level and salary.” Such prompts helped us to understand the components of a basic webscraper and propelled the development of our project.

**Prompt Refinement**: Even after having a satisfactory prompt, the response from the AI may still not meet expectations. Therefore, asking the model to explain certain lines of code it suggested helped to give an idea of where things might have been led astray and aid in refining subsequent prompts for better results.

**Chaining Prompts**: Splitting complex tasks into multiple smaller ones can lead to a better result than providing one detailed, verbose prompt. In the exercise, this would have manifested in splitting the creation of the webscraper into smaller, simpler steps. The first step would be to prompt the AI model to create code to fetch the job data through the API. The second prompt would ask the model to create code that parses the collected data and extracts the required details. The prompting would in this way have continued until the project was completed and allowed for easier adjustments or enhancements before moving on.

**Following up the prompts for continuity**: Using follow up prompts to help the AI model to keep track of the interactions and fulfill tasks while maintaining the established context. This technique thus ensures that outputs continue to be relevant and mitigates against errors. Prompting in this way was mostly used to add additional code to enhance the already made webscraper.
