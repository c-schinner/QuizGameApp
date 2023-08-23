# Quiz Game App
This README provides an overview of the structure and functionality of a simple quiz game app.
The app is composed of four files: MAIN.py, data.py, question_model.py, and quiz_brain.py. The app presents a series of true or false questions to the user and calculates their final score based on their answers.

# Files
'MAIN.py'
This file serves as the entry point for the quiz game app. It imports the required modules and implements the main logic for the game.

1. Imports the necessary classes:
from question_model import Question
from data import question_data
from quiz_brain import QuizBrain

2. Creates a list of Question objects from the data provided in question_data:
question_bank = []
for question in question_data:
    question_text = question['text']
    question_answer = question['answer']
    new_question = Question(question_text, question_answer)
    question_bank.append(new_question)

3. Initializes a QuizBrain object with the question_bank:
quiz = QuizBrain(question_bank)

4. Implements the game loop that iterates through questions:
while quiz.still_has_questions():
    quiz.next_question()

5. Displays the final score to the user:
print("You have finished the Quiz!")
print(f"Your final score is: {quiz.score}/{quiz.question_number}")

'data.py'
This file contains the data used to populate the question bank for the quiz game. It consists of a list of dictionaries, each containing a question text and its corresponding answer.

'question_model.py'
This module defines the Question class, which represents individual questions within the quiz.
class Question:
    def __init__(self, q_text, q_answer):
        self.text = q_text
        self.answer = q_answer

'quiz_brain.py'
This module contains the QuizBrain class, responsible for managing the quiz's logic and flow.
class QuizBrain:
    def __init__(self, q_list):
        # ...

    def still_has_questions(self):
        # ...

    def next_question(self):
        # ...

    def check_answer(self, user_answer, correct_answer):
        # ...

# How to Use the Quiz Game App
1. Ensure you have the required files (MAIN.py, data.py, question_model.py, and quiz_brain.py) in the same directory.

2. Run the MAIN.py script using a Python interpreter.

3. The quiz will begin, presenting a series of true or false questions. Enter your answer as "True" or "False" when prompted.

4. After all questions have been answered, the app will display your final score.

# Adding More Questions
You can extend the quiz game by adding more questions to the question_data list in the data.py file. Each question should be represented as a dictionary with the keys "text" for the question text and "answer" for the correct answer ("True" or "False").

# Acknowledgments
This quiz game app was created as a simple project to demonstrate the use of Python classes and logic flow. It can be expanded upon and customized according to your preferences.

For additional questions or support, feel free to reach out to the author at cschinner7@gmail.com.
