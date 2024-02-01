# Rock-paper-scissor-
This is my first task from codsoft on rock paper scissor 
import random

def determine_winner(user_choice, computer_choice):
    # Define game logic to determine the winner
    if user_choice == computer_choice:
        return "It's a tie!"
    elif (user_choice == 'rock' and computer_choice == 'scissors') or \
         (user_choice == 'paper' and computer_choice == 'rock') or \
         (user_choice == 'scissors' and computer_choice == 'paper'):
        return "You win!"
    else:
        return "Computer wins!"

def main():
    user_score = 0
    computer_score = 0
    choices = ['rock', 'paper', 'scissors']
    while True:
        print("\nWelcome to Rock-Paper-Scissors!")
        print("Enter your choice: rock, paper, or scissors")
        user_choice = input("Your choice: ").lower()

        if user_choice not in choices:
            print("Please enter a valid choice!")
            continue

        computer_choice = random.choice(choices)
        print(f"Computer's choice: {computer_choice}")

        result = determine_winner(user_choice, computer_choice)
        print(f"Result: {result}")

        if result == "You win!":
            user_score += 1
        elif result == "Computer wins!":
            computer_score += 1

        print(f"Your score: {user_score} | Computer's score: {computer_score}")

        play_again = input("Do you want to play again? (Y/N): ").lower()
        if play_again != "Y":
            print("Thanks for playing!")
            break

if __name__ == "__main__":
    main()
