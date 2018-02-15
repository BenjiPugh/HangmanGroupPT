#Start Code: Wenxin on dictionary, benji user input and verification, madison on round, benji on list work

#Wenxin below \/
#The program randomly chooses a secret word from the dictionary created below.
import random

words = ["hello", "python", "program", "love", "save", "exercise", 
"funny", "trust", "respect", "start"]
def choice():
    return random.choice(words)
word1 = choice()

#Wenxin above /\

#Benji below \/
#writes out underscores in place of each letter
word_lines = ["_"] * len(word1)
print(" ".join(word_lines))


#Check user input and return it if the input is a lowercase letter.

alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']
def is_letter(user_input):
    if user_input in alphabet:
      return True
    else:
      return False

def get_guess():
    guess = input("Type in a one letter guess: ")
    while is_letter(guess) == False:
        guess = input("whoops, that wasn't a letter, please type another: " )
    else:
        print("Your guess: " + guess)
        return guess



#checks if guess is in word to tell if hangman should be created
def check_guess(guess, word):
  if guess in word:
    return True
  else:
    return False

#finds guess placement in list and returns word placement to allow word lines to be replaced with correctly guessed letters
def word_placement(word, guess):
  placement = []
  for index in range(len(word)):
    if guess == word[index]:
      placement.append(index)
  return placement
  
#changes word_lines to include correctly guessed letters
def word_reveal(word, lines, guess):
  for placement in word_placement(word, guess):
    lines[placement] = word[placement]

#Stores the rows on which the hangman will be drawn.
row1 = ['____________']
row2 = ['|       ']
row3 = ['|       ']
row4 = ['|       ']
row5 = ['|        ']
row6 = ['|       ']

#Add 5 layers of drawings, add one each time the user guesses a wrong letter.
struct = [row1, row2, row3, row4, row5, row6]
draw0 = [""]
draw1 = ['|']
draw2 = ['@']
draw3 = ["/|V"]
draw4 = ['|']
draw5 = ["/ |"]
drawing = [draw0, draw1, draw2, draw3, draw4, draw5]

def draw_hangman(round_num):
  struct[round_num].append(drawing[round_num])
  return struct
  
# Madison below  \/ 
#Just edited for bugs - Benji
#There are six rounds. In each round, the program checks user guess and reveal the correct letter.
round = 0
while round < 5:
    user_guess = get_guess().lower()
   # print(check_guess(user_guess, word1))
    word_reveal(word1, word_lines, user_guess)

#If the user guess is false, draw one layer of hangman and add one round.
    if check_guess(user_guess, word1) == False:
      round = round + 1
      print("round: " + str(round + 1))
      for row in draw_hangman(round):
        print(row)
      print(" ".join(word_lines))
    else:
        print(("You guessed a correct letter"))
        for row in struct:
            print(row)
        print("round: " + str(round + 1))
        print(" ".join(word_lines))

#User wins if all the letters are guessed correctly in 5 rounds. If not, game over.
    if word_lines == list(word1):
      print("You Win!")
      for layer in drawing:
        print(layer)
        print 
      break
else:
  print("Game Over")
  print(word1)

# Madison above /\
