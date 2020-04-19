## Dialogflow chatbot

**Motivation:** Today most businesses struggle to support their customers. The time and relevance of information have a huge impact on customer support and due to the increasing presence and use of mobile devices, communication with a favorite brand via chat has become a part of everyday life. To save time, many are opting to deploy a chatbot that should be the first line of customer support. The result - satisfied and loyal customers. It is the fact that existing customers spend nearly 70% more than new customers. 
Rule-based chatbots are a thing of the past and there is a growing focus on making chatbots as similar as possible to humans, which is why the use of artificial intelligence has found tremendous use in this regard.

![Chatbot](/images/chatbot.gif) 

**Project description:** There is a large variety of AI Chatbot solutions on the market, including Google Dialogflow. Using the Dialogflow API, it became possible to integrate the AI chatbot solution with existing web and mobile applications. Within this project, the implementation of a mobile chatbot application will be demonstrated within which the Dialogflow SDK will be integrated.

### Project setup


![architecture](/images/graph_dialogflow (1).png)


### Scenario

There are three possible scenarios within a chatbot, which are very common for small/medium businesses:

1. Question about working hours

2. Schedule an appointment

3. Loyalty points check

On the picture below, there is simple example of how typical customer thinks. As salon customer before scheduling an appointment, person will check its' loyalty points. Then in case it decides to schedule appointment with simply saying __"I want to schedule an appointment"__ and providing details such as date and time, will do it quickly and easy. No need to enter data in specific format like (23/02/2020 10:00 AM), but saying "tommorrow 10am". 
The benefits are not only for this customer, but also for a salon and possibilty to integrate this solution with its Google Calendar, where customers will be able to simply schedule their appointments, with no human assistance. 

![use case](/images/shopping.png)

For each of the possible scenarios, the Dialogflow agent is trained with possible user queries, such as queries:
__"Are you still open?"__ and __"When do you close?"__ the agent will map the user query with __Intent -> working_hours__. This means NLP behind Dialogflow maps similar sentence structures to customer's intent.

For queries that require dynamic responses, such as scenario three, when searching for the status of a loyalty card, the agent will first need to ask the user for his card ID and then retrieve the number of points from the **database**.

If you want to dynamically create an appointment in Google Calendar via a chatbot, it will be necessary for the user to respond to queries about the date and time, after which appointment will be scheduled using the **Google Calendar API**.

A detailed scenario flow is shown on the graph below.

![use case](/images/dialogflow.png)

For more implementation details see [GitHub project](https://github.com/vildanap/DialogflowChatbot).

