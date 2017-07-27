---
layout: page
title: Multiple Choice Quiz
permalink: /quiz/
---
This is a quiz for Udacity's Intro to Programming Nanodegree built with Python that utilizes a list of dictionaries. It is designed to be run in the terminal. 
{% highlight python %}

easy_questions = [
    {
        'question': 'A 6 stringed instrument prominently used in rock and roll is a ',
        'answer': 'guitar'
    },
    
    {	'question': 'The president of the US is ',
    	'answer': 'Donald Trump'

    },
    { 	'question': 'We are on planet ',
    	'answer' : 'Earth'
    },
    {
        'question': 'October 31st is also known as ',
        'answer': 'Halloween'
    }
]

medium_questions = [
    {
        'question': 'A device that amplifies an electrical signal ',
        'answer': 'Amplifier'
    },
    {
    	'question': 'CPU stands for ',
    	'answer': 'central processing unit'
    },
    {
        'question': 'A kind of programming language that utilitizes objects ',
        'answer': 'object-oriented'
    },
    {	
    	'question': 'A block of reuseable code ',
    	'answer': 'function'
    	
    }
]

hard_questions = [
    {
        'question': 'A program produces output and takes in ',
        'answer': 'input'
    },
    {
        'question': 'The command for listing the files in a directory is ',
        'answer': 'ls'
    },
    { 
    	'question': 'To make a new directory in the terminal enter ',
    	'answer': 'mkdir'

    },
    {	
    	'question': 'The linux command allowing administrative privledges is ',
    	'answer': 'sudo'
    }

]


def grab_questions(difficulty):
    '''Grab list of questions based on difficulty'''
    result = easy_questions  # Defaults to easy_questions
    if difficulty == 'medium':
        result = medium_questions
    elif difficulty == 'hard':
        result = hard_questions
    return result


def generate_quiz(questions):
    '''Loops through list of questions until complete'''
    for question in questions:
        user_answer = raw_input(question['question'] + '\n')

        while user_answer.lower() != question['answer'].lower():
            user_answer = raw_input('Incorrect. Try again:\n')
    	if user_answer.lower() == question['answer'].lower():
    		print('Correct!\n ' + question['question'] + question['answer'] + '.')
    		print('')
    	

    print('You have answered all the questions. Thank you!')


print('\nThis is a fill-in-the-blank quiz. It has 3 difficulty levels.\n')

user_input = raw_input("Choose a difficulty: Type Easy, Medium, or Hard: ")
user_input = user_input.lower()  

valid_options = ["easy", "medium", "hard"]

while user_input not in valid_options:
	user_input = raw_input("Type Easy, Medium, or Hard: ")

user_questions = grab_questions(user_input)

generate_quiz(user_questions)

{% endhighlight %}