import random

def comp_choice(level):
    if level == 'easy':
        return random.randint(0, 5)
    elif level == 'medium':
        return random.randint(0, 10)
    elif level == 'hard':
        return random.randint(0, 20)

def winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "You guessed it right. Congrats!"
    else:
        return "Not quite! Try again."

def play_game():
    total_correct = 0
    while True:
        level = input("Choose a difficulty level (easy, medium, hard): ").lower()
        while True:
            computer_choice = comp_choice(level)
            if level == 'easy':
                user_choice = int(input("Guess a number between 0 and 5: "))
            elif level == 'medium':
                user_choice = int(input("Guess a number between 0 and 10: "))
            elif level == 'hard':
                user_choice = int(input("Guess a number between 0 and 20: "))
                
            print(f'Computer chose {computer_choice}')
            choose_winner = winner(user_choice, computer_choice)
            print(choose_winner)
            if choose_winner == "You guessed it right. Congrats!":
                total_correct += 1
                break
        play_again = input("Do you want to play again? (yes/no): ").lower()
        if play_again != "yes":
            break
    print(f'Thank you for playing! Your total correct score: {total_correct}')

play_game()
