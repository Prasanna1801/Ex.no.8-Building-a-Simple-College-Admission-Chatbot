# Ex.no.8-Building-a-Simple-College-Admission-Chatbot
## Aim :
 To design, implement and test a simple rule-based chatbot in Python that answers frequently asked questions related to college admissions, such as courses offered, eligibility criteria, fees, application process, required documents, important dates, hostel facilities and contact details.
### Introduction
A chatbot is a software application that simulates a conversation with a human user, typically through text. A rule-based (or pattern-matching) chatbot works by comparing the user's message against a predefined set of keywords or patterns and returning a suitable pre-written response. It does not require large training datasets or heavy computation, which makes it an easy and beginner-friendly starting point for understanding how conversational AI systems are built. In this experiment, a College Admission Chatbot is developed to act as a virtual help-desk assistant that instantly answers common queries asked by prospective students.

# THEORY
1. CHATBOT
A chatbot is a software application designed to simulate communication with users.

The basic function of a chatbot is:

User Input → Understand Query → Process Information → Generate Response

A chatbot receives an input from the user and processes the input to determine the required response.

Chatbots can be used in:

Education
Healthcare
Banking
Customer support
E-commerce
Travel services
College admission systems

2. COLLEGE ADMISSION CHATBOT
A College Admission Chatbot is designed specifically to answer questions related to college admission.

The chatbot can provide information such as:

Available courses
Eligibility criteria
Admission procedure
Application process
Required documents
Course duration
Fee information
Contact information
Important admission details

The chatbot acts as an automated assistant between the student and the college admission system.

3. WORKING PRINCIPLE OF THE CHATBOT

The chatbot works by receiving a message from the user and processing the input.

The general working process is:

The user enters a question.
The chatbot receives the input.
The input is processed.
Important keywords or user intent are identified.
The chatbot searches for a suitable response.
The appropriate response is generated.
The response is displayed to the user.

For example:

User Input:
```
"What is the eligibility for admission?"

          ↓

Text Processing

          ↓

Identify Keywords:
"Eligibility", "Admission"

          ↓

Search Response Database

          ↓

Generate Response

          ↓

"The eligibility criteria depend on the selected course."
```
4. COMPONENTS OF A COLLEGE ADMISSION CHATBOT

A simple College Admission Chatbot consists of the following components.

User Interface

The user interface allows the student or user to communicate with the chatbot.

The interface may contain:

Text input box
Send button
Chat window
Response display area
User Input

The user enters a question or message.

Example:

How can I apply for admission?
Input Processing

The chatbot processes the user's input.

Processing may include:

Converting text to lowercase.
Removing unnecessary spaces.
Identifying keywords.
Matching the query with predefined questions.

For example:

"HOW CAN I APPLY?"

can be converted to:

"how can i apply?"

This makes comparison easier.

Knowledge Base

The knowledge base contains information that the chatbot uses to answer questions.

For a College Admission Chatbot, the knowledge base may contain:

Category	Information
Courses	Available programs
Eligibility	Admission requirements
Fees	Course fee information
Documents	Required documents
Admission Process	Application steps
Contact	College contact details

The chatbot retrieves the required information from this knowledge base.

Response Generator

The response generator selects or creates an appropriate response.

For example:

Query → "What documents are required?"

Response:

Documents such as educational certificates, identification documents, and photographs may be required for admission.

5. TYPES OF CHATBOTS
RULE-BASED CHATBOT

A rule-based chatbot works using predefined rules and responses.

For example:

IF user asks about courses
    Display available courses

IF user asks about eligibility
    Display eligibility information

This type of chatbot is simple and suitable for frequently asked questions.

KEYWORD-BASED CHATBOT

A keyword-based chatbot searches for important words in the user's message.

For example:

User Input:
"What are the admission requirements?"

Keyword:
"admission"

The chatbot searches for information related to admission.

AI-BASED CHATBOT

An AI-based chatbot uses Artificial Intelligence techniques to understand user queries.

It can understand different ways of asking similar questions.

For example:

How can I apply?

How do I submit an application?

What is the admission process?

An AI-based chatbot can identify that all these questions are related to the admission process.

6. NATURAL LANGUAGE PROCESSING

Natural Language Processing (NLP) is an important area of Artificial Intelligence that enables computers to process and understand human language.

NLP can help a chatbot understand:

Words
Sentences
User intent
Context
Different forms of questions

For example:

"What courses are available?"

and

"Tell me the programs offered by the college."

have different wording but may represent the same intention.

NLP techniques can help the chatbot recognize such similarities.

7. USER INTENT

Intent refers to the purpose or meaning behind a user's query.

For a College Admission Chatbot, common intents may include:

Course Information
What courses are available?
Eligibility
What are the eligibility requirements?
Fee Information
What is the course fee?
Admission Procedure
How can I apply?
Required Documents
What documents are required?
Contact Information
How can I contact the admission office?

The chatbot identifies the intent and provides an appropriate response.

8. WORKING OF KEYWORD-BASED CHATBOT

A simple chatbot can use predefined keywords.

For example:

Input Keywords → Chatbot Response

"course"      → Course information
"eligibility" → Eligibility information
"fee"         → Fee information
"apply"       → Application procedure
"document"    → Required documents
"contact"     → Contact information

The chatbot compares the user's input with these keywords.

If a keyword is identified, the corresponding response is displayed.

If no suitable keyword is found, the chatbot can display:

Sorry, I could not understand your question.
Please ask about courses, eligibility, fees, documents, or admission.

# BLOCK DIAGRAM
COLLEGE ADMISSION CHATBOT
```
┌──────────────────────┐
│        STUDENT       │
│        / USER        │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│      USER QUERY      │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   INPUT PROCESSING   │
│ Lowercase Conversion │
│ Keyword Identification│
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  INTENT IDENTIFICATION│
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│    KNOWLEDGE BASE    │
│ Courses             │
│ Eligibility         │
│ Fees                │
│ Documents           │
│ Admission Process   │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  RESPONSE GENERATOR  │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   CHATBOT RESPONSE   │
└──────────────────────┘
```

### Procedure

### Step 1: Import Required Libraries
●	re – Python's regular expression module, used to search for keyword patterns inside the user's message.
●	random – used to randomly pick one response when more than one reply is available for the same intent, so the chatbot does not sound repetitive.
<img width="605" height="37" alt="image" src="https://github.com/user-attachments/assets/5d19fe62-e644-4676-805b-2fe23826e1da" />

### Step 2: Design the Knowledge Base (Intents and Responses)
●	The knowledge base is stored as a Python dictionary, where every key is an intent (topic) such as courses, eligibility, fees or hostel.
●	Each intent stores a list of patterns (keywords/phrases likely to appear in a user's question) and a list of possible responses.
●	Organising the data this way makes the chatbot easy to extend — a new admission topic can be added simply by adding one more entry to the dictionary.
<img width="642" height="222" alt="image" src="https://github.com/user-attachments/assets/146afc71-fa16-4c84-a959-c91bbc2842eb" />
<img width="618" height="359" alt="image" src="https://github.com/user-attachments/assets/6b976de7-7dce-4418-a526-d25b31c66e79" />
Knowledge Base Summary
The table below summarises the complete knowledge base used by the chatbot:
<img width="669" height="403" alt="image" src="https://github.com/user-attachments/assets/991481a9-e6a3-4ce8-a3d0-2f07c4c7adf2" />

### Step 3: Function to Match User Input to an Intent
●	Converts the user's sentence to lower case so that matching is not case-sensitive.
●	re.search() scans the message for each pattern of every intent; the first intent whose pattern is found is returned.
●	If no pattern matches any intent, the function returns None so the fallback response can be used.
<img width="632" height="115" alt="image" src="https://github.com/user-attachments/assets/b4e8db5f-7e9c-4e48-9aeb-82d4c9e43097" />

### Step 4: Define the Chatbot Response Function
●	Calls match_intent() to identify what the user is asking about.
●	random.choice() picks one response from the matched intent's response list.
●	Returns a fallback message when the intent could not be identified, instead of leaving the user without a reply.
<img width="623" height="95" alt="image" src="https://github.com/user-attachments/assets/ab6895ac-bba4-4e66-9c51-cacf8d828286" />

### Step 5: Build the Interactive Conversation Loop
●	input() continuously reads the user's message from the console.
●	get_response() generates the reply for every message typed by the user.
●	The loop ends automatically once the matched intent is “goodbye” (e.g. the user types bye / exit / quit).
<img width="632" height="126" alt="image" src="https://github.com/user-attachments/assets/ae562d77-2461-4bed-b4c1-461b1cea5728" />

### Step 6: Test the Chatbot with Sample Queries
●	A list of realistic sample questions is used to automatically test every intent in the knowledge base.
●	Each query and the chatbot's corresponding reply are printed, which makes it easy to verify that every category of question is answered correctly.
<img width="622" height="113" alt="image" src="https://github.com/user-attachments/assets/4fdb6b4b-c684-4033-94e1-0d51fa19e99b" />
<img width="583" height="251" alt="image" src="https://github.com/user-attachments/assets/2ba37096-9575-4164-b4c3-ebca74ca9aab" />

### Step 7: Run the Chatbot
The complete script is executed in Python. Since input() cannot be used for automated testing, the sample_queries list from Step 6 is run first to validate every intent; the same get_response() function also powers the live chat() loop for real-time conversation with a user. The output produced on running the program is shown below.
Output
### Sample Conversation Output (Part 1)
●	The chatbot correctly greets the user and identifies the courses, eligibility, fees, application process and documents intents from the keywords present in each question.
<img width="646" height="470" alt="image" src="https://github.com/user-attachments/assets/016e1f31-dd01-4348-8815-70b3577b1391" />
### Sample Conversation Output (Part 2)
●	The remaining queries about dates, hostel facility and contact details are correctly matched to their respective intents.
●	The conversation ends gracefully with a goodbye message once the user types “Bye”, terminating the chat loop.
<img width="660" height="380" alt="image" src="https://github.com/user-attachments/assets/698ac90d-7962-406c-b381-03d16bedfb3b" />

# APPLICATIONS
A College Admission Chatbot can be used in various educational applications.

Student Support

The chatbot can answer common student questions.

Admission Assistance

It can provide information about admission procedures.

Course Information

Students can obtain details about available programs.

24-Hour Information Support

A chatbot can provide automated responses at any time.

Frequently Asked Questions

The chatbot can handle common questions without requiring manual staff intervention.

Website Integration

The chatbot can be integrated into a college website to assist students and parents.

# ADVANTAGES
The advantages of a College Admission Chatbot include:

Provides quick responses.
Available at any time.
Reduces repetitive work.
Improves communication with students.
Provides information automatically.
Handles frequently asked questions.
Reduces the workload of admission staff.
Can support multiple users.
Provides a simple and interactive interface.
Can be improved by adding more questions and responses.

# LIMITATIONS
The limitations include:

A simple chatbot may only answer predefined questions.
It may not understand complex sentences.
Incorrect keyword matching can generate inappropriate responses.
The chatbot depends on the information available in the knowledge base.
Regular updates are required when admission information changes.
It may not understand every form of user query.
Complex admission-related issues may require human assistance.

# FUTURE ENHANCEMENTS
The College Admission Chatbot can be improved by adding:

Natural Language Processing.
Machine Learning techniques.
Voice-based interaction.
Multilingual support.
Online application assistance.
Database connectivity.
Real-time admission information.
Personalized responses.
Integration with the college website.
AI-based question understanding.

# RESULT
The Simple College Admission Chatbot was successfully designed and developed.

The chatbot was able to receive user queries related to college admission and provide appropriate responses based on predefined keywords and information. The chatbot was tested using different queries related to courses, eligibility, admission procedures, fees, and required documents.

The experiment demonstrated how a chatbot can be used to automate communication and provide quick information to students.

## Conclusion
Thus, a simple rule-based College Admission Chatbot was successfully designed, implemented and tested using Python. The chatbot uses a keyword/pattern-based knowledge base to identify the intent behind a user's question and responds with an appropriate, pre-defined answer covering courses, eligibility, fees, application process, documents, dates, hostel and contact information. The experiment demonstrates the fundamental building blocks — knowledge base design, intent matching and response generation — on which more advanced NLP-based and AI-based chatbots are built.
