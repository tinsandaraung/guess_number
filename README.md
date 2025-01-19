# guess_number
a number guessing game with Python

import random

def comp_choice():
  choices = list(range(6))
  return random.choice(choices)

def winner(user_choice, computer_choice):
  if user_choice == computer_choice:
    return "You guessed it right. Congrats!"
  else:
    return "Not quite! One more game."

def play_game():
  while True:
   user_choice = int(input("Guess a number between 0 and 5: "))
   computer_choice = comp_choice()
   print(f'Computer chose {computer_choice}')
   choose_winner = winner(user_choice, computer_choice)
   print(choose_winner)
   if choose_winner == "You guessed it right!":
     break

play_game()
