# Set your research questions  

When you analyze your health tracker data to unearth health insights beyond general stats and dashboards, you are essentially conducting empirical research. Empirical research is a research approach that draws conclusions from the observation and measurement of events. Note that an event here simply means anything you want to observe and measure for your research. For example, how many steps you took in a day can be considered an event here.  
In empirical research, a very important first step is to define the main question, or questions, of your research. Setting your research questions is vital because it helps ensure that the research work you are about to do actually addresses meaningful questions that genuinely matter to you. Equally important, it helps reduce the risk of biases and errors in your findings.  

## How to set research questions  
The approach to setting research questions can vary by domain and use case. For the specific use case of a person wanting to leverage their health tracker data to answer their own unique health questions, here are the steps I recommend.  

### Steps for setting your research questions:  
1. Brainstorm your general research goal  
2. Review potential data sources  
3. Refine your general research goal into specific research questions  
4. Review  
5. Rinse and repeat as needed  

Let's walk through these steps in detail and with an example.  

### 1. Brainstorm your general research goal  
Start with figuring out what exactly you want to learn through your research, and do not worry about looking at your data just yet. Spend some time brainstorming research ideas and putting them down in writing. Feel free to keep those ideas vague and general for now, you will refine them later.  
An important pitfall in this step is accidentally limiting yourself to only researching what you think your data can answer for you. If you limit yourself that way, you might end up doing a lot of work to answer a research question that does not really matter to you. You might also be introducing biases and errors into your research that way because you may have conscious or unconscious assumptions and expectations about the data you plan to use. To avoid this pitfall, start brainstorming for broad research goal ideas before looking at your data.  

#### Here are some guiding questions for your brainstorming:  
- What do you want to learn about your health?  
- Why do you want to learn this? Why does it matter to you?  
- What are the potential ways you could use the knowledge you are trying to learn? How will it help you? Can it help others?  
- Are there pre-existing answers or research done to answer your question? If yes, why are those answers or research not enough for you? What can you add to the existing answers?  

#### Example: my research goal  
My research goal is to understand better how my wellness habits affect how well I feel.  
This research goal is intentionally broad, which gives me lots of room to refine it after I review the potential data sources available to me.  
Throughout this guide, I will use this research goal as an example.  

### 2. Review potential data sources  
Now that you have a general research goal, consider your potential data sources. What data do you need for your research goal? Let your research goal guide you to the relevant data, and not vice versa.  

#### Guiding questions for this data review:
- What kind of data is available?  
- What is the format of the data?  
- For time series data, what are the frequency and date ranges of the data?  
- Does the data appear to have lots of missing values?  
- Is this data relevant to the research goal? How can it help investigate the research goal?  
- Is this data enough for the research goal? If not, what information is missing?  

#### Review your health tracker data download  
One obvious potential data source for your health tracker data research project is, of course, your health tracker data download. However, it might not be enough to meet your research goal. In that case, you need to consider additional data sources.  

#### Example: reviewing my Fitbit data download  
In this example, I'll use my own Fitbit tracker data download and my research goal. If you use a Fitbit tracker, you can download your Fitbit data using [these instructions](https://help.fitbit.com/articles/en_US/Help_article/1133.htm) and follow along the steps in [this notebook](https://github.com/33eyes/trackers-analysis/blob/main/01_data_review.ipynb).  
My research goal is to understand better how my wellness habits affect how well I feel. In this data review step, I want to see if my Fitbit tracker data can help me investigate my research goal.  

I have a basic Fitbit tracker, the Inspire HR, and a free Fitbit account. My data download contains the following data:  
- Physical Activity  
- Sleep  
- Menstrual Health  

Your health tracker data may be very different, of course.  

Reviewing my data download in [this notebook](https://github.com/33eyes/trackers-analysis/blob/main/01_data_review.ipynb), I've uncovered the following about the data:  
- The documentation provided in the Fitbit data download is incomplete, but it's likely possible to find the missing information on community forums and through Fitbit support.  
- Some datasets were empty or were for measurements I know I didn't track in Fitbit. I excluded such datasets.  
- All relevant data is either time series or time ranges, as expected.  
- The relevant datasets contain lots of timestamped data, but there may be irregular gaps between timestamps.  
- I found roughly the following kinds of data:  
  - Various heart rate measurements  
  - Activity data: steps, distance, broad categories of activity level  
  - Computed fitness data: demographic VO2 max  
  - Sleep data  
  - Breathing rate measurements  
  - Menstrual cycles time ranges  

I've summarized my data review findings and notes in [this spreadsheet](https://github.com/33eyes/trackers-analysis/blob/main/fitbit_tracker_data_review.csv). 

