import random
import operator

def quiz():
    print ( 'Welcome to level 2 of snakes and ladders!')
    print('Congraltions, you have reached the end of the game board.')
    print ( ' Now in order to finsh off the game, you have to complete')
    print ('a math quiz. Once when you answer ten math questions correctly,')
    print ('you will be the winner of the game')
   
   
    name = input("Please enter your name")
    print("Hello", name," Let's begin the quiz!")
    score = 0
    for i in range(10):
        correct = askQuestion()
        if correct:
            score += 1
            print('Correct!')
            print "Score",(score),"\n"
        else:
            print('Incorrect!')
            

    print ("Congraltions, you have won the game!")
    print (' A bright light now birgtens up a dark pathway.')
    print ( 'the light leads you back to your closet, which then leads')
    print (' you back to your bedroom.')
    print ('you are now back your bedroom.')


def askQuestion():
    answer = randomCalc()
    guess = float(input())
    return guess == answer

def randomCalc():
    ops = {'+':operator.add,
    '-':operator.sub,
    '*':operator.mul}
    num1 = random.randint(0,11)
    num2 = random.randint(1,11)   
    op = random.choice(list(ops.keys()))
    answer = ops.get(op)(num1,num2)
    print('What is {} {} {}?'.format(num1, op, num2))
    return answer

quiz()
#askQuestion()
#randomCalc()
