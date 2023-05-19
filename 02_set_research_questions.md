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

>#### Example: my research goal  
>My research goal is to understand better how my wellness habits affect how well I feel.  
>This research goal is intentionally broad, which gives me lots of room to refine it after I review the potential data sources available to me.  
>Throughout this guide, I will use this research goal as an example.  

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

>#### Example: reviewing my Fitbit data download  
>In this example, I'll use my own Fitbit tracker data download and my research goal. If you use a Fitbit tracker, you can download your Fitbit data using [these instructions](https://help.fitbit.com/articles/en_US/Help_article/1133.htm) and follow along the steps in [this notebook](https://github.com/33eyes/trackers-analysis/blob/main/01_data_review.ipynb).  
>My research goal is to understand better how my wellness habits affect how well I feel. In this data review step, I want to see if my Fitbit tracker data can help me investigate my research goal.  
>
>I have a basic Fitbit tracker, the Inspire HR, and a free Fitbit account. My data download contains the following data:  
>- Physical Activity  
>- Sleep  
>- Menstrual Health  
>
>Your health tracker data may be very different, of course.  
>
>Reviewing my data download in [this notebook](https://github.com/33eyes/trackers-analysis/blob/main/01_data_review.ipynb), I've uncovered the following about the data:  
>- The documentation provided in the Fitbit data download is incomplete, but it's likely possible to find the missing information on community forums and through Fitbit support.  
>- Some datasets were empty or were for measurements I know I didn't track in Fitbit. I excluded such datasets.  
>- All relevant data is either time series or time ranges, as expected.  
>- The relevant datasets contain lots of timestamped data, but there may be irregular gaps between timestamps.  
>- I found roughly the following kinds of data:  
>  - Various heart rate measurements  
>  - Activity data: steps, distance, broad categories of activity level  
>  - Computed fitness data: demographic VO2 max  
>  - Sleep data  
>  - Breathing rate measurements  
>  - Menstrual cycles time ranges  
>
>I've summarized my data review findings and notes in [this spreadsheet](https://github.com/33eyes/trackers-analysis/blob/main/fitbit_tracker_data_review.csv).  

#### Assess how the health tracker data can be used in analyses  
In my [Fitbit data review spreadsheet](https://github.com/33eyes/trackers-analysis/blob/main/fitbit_tracker_data_review.csv) above, I assigned a potential role in analyses to each data measurement type. At a high level, the options for a role that data can play in analyses are explanatory, response or control variables.  

Here's what these roles mean.  
- ##### Response variable  
  The response variable is the data that researchers are trying to explain or predict in their research project. Typically there is only one response variable in a data model. However, there can be more than one data model in a research project, modeling different response variables, or a new response variable can be constructed by combining multiple response variables.  
- ##### Explanatory variable  
  The explanatory variables are the data researchers use to explain or predict the response variable in their research project. For explanatory analyses, these are the variables whose effect on the response the researchers are trying to study and explain. There can be one or more explanatory variables in a data model.  
- ##### Control variable  
  Control variables are the data that likely affects other variables in a research project, but the researchers are not interested in their effect on the response variable in this project. For explanatory analyses, these control variables need to be included in the data model so that their impact on the response data does not confuse the explanatory variables' effects. For prediction models, there is no significant distinction between explanatory and control variables: they both are inputs to a data model that makes predictions.  

Whether particular data is an explanatory, response or control variable in your research project depends on your research goal/question.  

> #### Example: assessing how my Fitbit data can be used my research project  
> I have the following broad research goal: to understand better how my wellness habits affect how well I feel.  
>
> In [my Fitbit data review file](https://github.com/33eyes/trackers-analysis/blob/main/fitbit_tracker_data_review.csv), I've marked physical activity data that captures my walking and exercise habits (e.g., steps, distance, activity level, exercise, etc.) as potential **explanatory variables** in my research project. This data reflects some of my wellness habits, and in this research project, I want to use them to see if they can explain or predict how well I feel.  
>
>I've marked physical health measures like resting heart rate, VO2 max, sleep quality, sleep breathing rate and sleep heart variability as potential **response variables** because they are indicators of physical health and wellness. These variables measure my overall physical wellness and, presumably, how well I feel, which is what I am trying to explain and predict in my research project.  
>
>I've marked menstrual cycle data as **control variables**. Menstrual cycles do not reflect any wellness habits that I can control, so I am not interested in their effect in this research project. However, menstrual cycles likely affect how well I feel and hence should be included in my data model to avoid conflating their impact with the explanatory variables.  
>
>I've marked some data as both explanatory and response variables. This is because, for some variables, I am so far unclear on how I might use them in my research, e.g., the raw heart rate data. Or it is because I plan to use some parts of that data as explanatory and other parts as response, e.g., sleep times are habits I can control and hence consider explanatory, while sleep quality seems more like a response variable candidate in my research project.  
>
>##### Do I have enough data for my research goal?  
>There are lots of useful data for investigating my research goal in my Fitbit data download. But is that data enough to fully address it? My subjective answer is no.  
>
>To me, how well I feel also includes my mood and subjective sense of how well I feel, and not just the specific heart and breathing rate metrics (although I'm guessing they are related). This means I need more data for my response variables, particularly data that captures my mood or how I feel.  
>
>I could also use more data for my explanatory variables. Fitbit steps, exercise intensity and other physical activity data capture only some of my wellness habits. I have hobbies, work habits and other life events that probably affect how well I feel. If I can get data on these other habits and events, my data model will probably be more accurate.  
>
>I could also improve on my control variables. I am guessing that weather and other environmental factors can affect both my wellness habits and how well I feel. These factors could confound my research findings if I don't account for them in my data model.  
>
>So, in conclusion, I need to gather more data.  

#### Consider supplemental data sources  
If your health tracker data is not enough to investigate your research goals, then it is a good idea to consider additional data sources.  
Where can you get the additional data to supplement your health tracker data? Here are some options:  
- Open source datasets and publicly available data  
- Combining data from other trackers, e.g., mood or productivity tracker app data  
- Tracking the data yourself  
  - This can be as simple as a spreadsheet, or even pen and paper, where you enter daily values for a couple of months.  
  - This approach is more manual and cumbersome, but it is also the most customizable. You can start a spreadsheet that tracks your daily answers to any question you want.  
  - You can use Google Forms to set up your own custom personal tracker and fill it out on your smartphone.  

>#### Example: potential supplemental data sources  
>I am missing the following data needed for my research goal:  
>analysis role | the needed supplemental data  
>--- | ---  
>response | data that captures my mood or how I feel  
>explanatory | more detailed qualitative data on exercise, e.g., the type of exercise  
>explanatory | hobbies, work habits, other life events and stressors  
>control | weather  
>control | environmental factors  
>
>
>I can collect the weather and environmental factors like air quality from publicly available data sources. The remaining missing pieces are all based on my individual behaviors and subjective assessments, and the only way to collect data on them is to track them somehow.  
>
>I could try to find existing tracker apps to collect that data, but because I am interested in many different kinds of data, that would mean finding and using a bunch of different apps, which can become unwieldy. In this case I think it is easier to create one solution to capture all the data I need rather than use a long list of tracker apps. Doing so also gives me the benefit of setting up my tracker however I want and not being limited by what is allowed in a given app.  

#### Collect supplemental data   
To collect supplemental data that is publicly available or open source, you could search for it online and follow data access instructions.  

To collect data from other tracker apps, please refer to their documentation for instructions.   

To track data yourself, all you need is a set of questions to ask yourself and a way to record your responses on a regular basis. This can be done in many ways, for example, in a spreadsheet or even with pen and paper.  
For many people, the easiest way to do it would be by tracking the data on their smartphone. The instructions below describe one way you could set up your own custom data tracker to use on your phone. 

##### How to make your own personal tracker for anything you want with Google Forms  
These instructions refer to Google Sheets and Forms as of May 2023.  

1. Start a new spreadsheet in Google Sheets  
1. Create a new form in it  
   - In the top navigation bar of the spreadsheet, go to Tools > Create a new form  
   - This form will contain your tracker questions

>###### Example: new Google form  
>![New Google form image](img/tracker_qq_setup_illustr_1.png | width=100)  

