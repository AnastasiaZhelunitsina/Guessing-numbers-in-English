from random import randint
print('Hi! This is the "Guessing numbers" game. Try to guess an integer number from 1 to 100. Are you ready?')
answer = input('Please enter your answer. If you wanna continue enter "Yes". If you wanna quit this game enter "Q".').lower()
if answer == 'yes' or answer == ' yep' or answer == 'of course' or answer == 'y':
    print('Okay, Let\'s start!')
elif answer == 'q' or answer == 'no':
    print('Oh, it\'s so sad! See you later)')
    exit()

name = input('Enter your name please: ')
number = randint(1, 100)
number_of_attempts = 1
while True:
    user_number = int(input(f'{name} please enter your number from 1 to 100: '))
    if 101 > user_number > number > 0:
        if user_number - number < 10:
            print('This is a little more than necessary. You\'re close)')
            number_of_attempts += 1
        else:
            print('Too much, try again')
            number_of_attempts += 1
    elif 0 < user_number < number < 101:
        if number - user_number < 10:
            print('This is a little less than necessary.You\'re close)')
            number_of_attempts += 1
        else:
            print('Too little, try again')
            number_of_attempts += 1
    elif user_number == number:
        if number_of_attempts < 5:
            print(f'You\'re absolutely right! Number of your attempts: {number_of_attempts}! It\'s amazing! Сongratulations!')
            question = input('To exit the game, enter "Q"').lower()
            if question == 'q' or question == 'y' or question == 'yes':
                print('Oh, it\'s so sad! See you later)')
                break
            else:
                number = randint(1, 100)
                number_of_attempts = 1
                continue
        elif number_of_attempts < 10:
            print(f'You\'re absolutely right! Number of your attempts: {number_of_attempts}! It\'s a good job! Congratulations!')
            question = input('To exit the game, enter "Q"').lower()
            if question == 'q' or question == 'y' or question == 'yes':
                print('Oh, it\'s so sad! See you later)')
                break
            else:
                number = randint(1, 100)
                number_of_attempts = 1
                continue
        else:
            print(f'You\'re absolutely right! Number of your attempts: {number_of_attempts}! Congratulations!')
            question = input('To exit the game, enter "Q"').lower()
            if question == 'q' or question == 'y' or question == 'yes':
                print('Oh, it\'s so sad! See you later)')
                break
            else:
                number = randint(1, 100)
                number_of_attempts = 1
                continue
    elif user_number > 100:
        print('The entered number is greater than 100. Please try again.')
        number_of_attempts += 1
    elif 0 > user_number:
        print('The number entered is less than 1. Please try again.')
        number_of_attempts += 1