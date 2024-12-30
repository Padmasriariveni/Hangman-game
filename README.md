import random
word_list = ["apple", "beautiful", "potato", "orange", "yellow", "blue"]
lives = 6
chosen_word = random.choice(word_list)
print(f"The chosen word: {chosen_word}")
display = ["_" for _ in chosen_word]
print(display)
game_over = False
while not game_over:
    guess_letter = input("Guess a letter: ").lower()
    for pos in range(len(chosen_word)):
        letter = chosen_word[pos]
        if letter == guess_letter:
            display[pos] = guess_letter 
        print(display)
    if guess_letter not in chosen_word:
        lives -= 1
        print(f"Wrong guess! Lives left: {lives}")
        if lives == 0:
            game_over = True
            print("You Lose!")
    if "_" not in display:
        game_over = True
        print("You Win!")
