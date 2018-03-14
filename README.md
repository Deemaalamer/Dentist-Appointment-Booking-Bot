# Dentist-Appointment-Booking-Bot

This is a simple chatbot that can assist you in booking dentist appointments. Functionalities include greeting users in their timezone,simplified dental appointment booking and also introduces user to entities-regular expression pattern matching. Bot used from https://developer.ibm.com/code/exchanges/bots. 

## IBM Watson® Conversation
IBM Watson® Conversation is a question-and-answer system that provides a dialog interaction
between the conversation system and users. This style of interaction is commonly called a
chatbot

Now, let's build the conversation!

## Task 1: Login to your IBM Cloud account & create Conversation service

1. Login to your IBM Cloud account, if you don't have one already you can signup here. (tracked link)
2. Open the Catalog, click on **Watson** to refine search.
3. Scroll down and click on **Conversation** service.
4. Click on **Create** to create an instance of the service. Make sure you choose an **organization** and **space**.
5. Click on **Launch tool** to open the tool.

## Task 2: Create your bot workspace
1. Click on **(+) Create** to create the wrokspace.
2. Name your bot 'Dental Appointment Booking Bot'

## Task 3: Create your intents
An intent is a group of examples of things that a user might say to communicate a specific goal
or idea. To identify intents, start with something that a user might want and then list the ways
that the user might describe it.

Here we are going to crete two intents. For each intent, we will add examples to train the conversation for intent recognition.

1. Add the first inetent and call it #book_appoitment
2. Add user examples such as: Book an appointment, Book appointment, Can you pls help me book an appointment, cavity in my tooth, Help me book an appointment, I need to book an appointment immediately, I have a tooth pain, My tooth is aching, I need to book an appointment immediately... etc
3. Add the second intent and call it #thanks, this is to detect when the user is thanking the bot.
4. Add user examples such as: Thank you, Thank you very much, Thanks, Thanks a lot.. etc

You can test your intent, by clicking Ask Watson icon in the top, right-hand side of the conversation editor.

## Create your entities
Entity is a portion of the user's input that you can use to provide a
different response to a particular intent. Click Entities. On the Entities page, click Create new.

Each entity definition includes a set of specific entity values that can be used to trigger different
responses. Each value can have multiple synonyms that define different ways that the same value
can be specified in user input. Create entities to represent to the application what the user wants to access. Fuzzy logic is a
feature that allows Watson Conversation to accept misspelled words. You can enable this feature
at the entity level.

1. Add your first entity and call it @personal_details
2. Enter value **emailid**
3. Switch synonyms to patterns, and add this regular expression 
'''<b>^[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$</b>'''

to identify emails.

## Build the Dialog 
A dialog is made up of nodes that define steps in the conversation.

In the previous image, two dialog nodes are shown. The first node is the standard welcome
message. The other node is a catch-all node named "Anything else." Dialog nodes are chained in
a tree structure to create an interactive conversation with the user. The evaluation starts at the
top, so the welcome node is assessed before the "Anything else" node.

In the welcome node choose the intent “welcome” with the response "hey there welcome to
dental chatbot?" To validate how the flow works, you can click the Ask Watson icon.

8-Define Nodes
The first node addresses greetings in a response to a query such as "hello." Click the welcome
node and click Add node below
A new node is added between the welcome and "Anything else" nodes.

After you add the Greeting node, Customize the greeting and make sure the Multiple responses
tab is on

To let the chatbot welcome the user with good morning and good afternoon add the following
responses:

The now().before(‘12:00:00’) detects if the conversation is in the morning and triggers good
morning.
The now().before(‘16:00:00’) detects if the conversation is in the afternoon and triggers good
afternoon.
The now().before(‘24:00:00’) detects if the conversation is in the evening and triggers good
evening.
Add the Book Dentist Appointment node then customize it and make sure the slots is on then
hit Apply

Add the responses below, The @sys-date entity is defined by the system to detect the date in the
conversation and it will save it in the $appointmentDate intent. In the “If not response,ask” tab
add the response “please enter preferred appointment Date”.




Web Application Template for Watson Conversation API
Demonstration
Requirements:
1.
Install Nodejs http://blog.teamtreehouse.com/install-node-js-npm-windows
Main steps:
1.
"Clone or Download" this Repository from this link
https://github.com/NailahTayyar/WatsonConversation
2.
Take note of Watson Conversation Service's Credentials and workspace_id
3.
Edit the file app.js and fill the fields: username, and <workspace_id> with the data
collected in the last step.
