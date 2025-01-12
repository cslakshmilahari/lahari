import time
import random

def print_slow(text, delay=0.05):
    for char in text:
        print(char, end="", flush=True)
        time.sleep(delay)
    print()

def intro():
    print_slow("You wake up in a dark forest. The trees loom high, their branches clawing at the starless sky.")
    print_slow("You don't remember how you got here, but you feel an overwhelming sense of urgency.")
    print_slow("The air is damp, and the faint sound of rustling leaves sends a shiver down your spine.")
    print_slow("A dense fog rolls in, obscuring your view, and the distant hoot of an owl echoes eerily.")
    print_slow("Ahead of you, a path splits into three directions: left, right, and straight ahead.")
    print_slow("Each path looks equally ominous, but staying here feels even more dangerous.")
    print_slow("Will you summon the courage to explore, or will the forest claim another lost soul?")

def choose_path():
    print_slow("Which path will you take?")
    print("1. Left - The path seems to wind deeper into the dense forest, where shadows dance ominously.")
    print("2. Right - The sound of rushing water can be faintly heard, suggesting a river or waterfall ahead.")
    print("3. Straight ahead - A faint light flickers in the distance, leading to what appears to be an old structure.")
    choice = input("Enter your choice (1, 2, or 3): ").strip()
    while choice not in ["1", "2", "3"]:
        choice = input("Invalid choice. Please select 1, 2, or 3: ").strip()
    return choice

def encounter_wolf():
    print_slow("As you walk down the left path, the forest grows darker, and the air feels heavy.")
    print_slow("You hear rustling in the bushes, and moments later, a massive wolf steps out.")
    print_slow("Its eyes glow eerily in the faint light, and its growls send chills down your spine.")
    print_slow("The wolf blocks your path, its sharp teeth glinting in the faint moonlight.")
    print("1. Run")
    print("2. Fight")
    print("3. Offer food")
    action = input("What will you do? (1, 2, or 3): ").strip()
    while action not in ["1", "2", "3"]:
        action = input("Invalid choice. Please select 1, 2, or 3: ").strip()

    if action == "1":
        print_slow("You turn and sprint as fast as you can, branches whipping against your face.")
        print_slow("The wolf chases after you, its snarls growing louder and more menacing.")
        print_slow("Just when you think it's over, the wolf halts abruptly, letting out a final growl before retreating.")
        print_slow("You collapse against a tree, breathless but alive.")
        return "escaped"
    elif action == "2":
        print_slow("You grab a sturdy branch from the ground and prepare to defend yourself.")
        if random.random() > 0.5:
            print_slow("After a fierce struggle, you manage to fend off the wolf, which retreats into the darkness.")
            print_slow("You're injured, but you've survived this terrifying encounter.")
            return "injured"
        else:
            print_slow("The wolf lunges at you with incredible speed. Despite your best efforts, it overpowers you.")
            print_slow("Your journey ends here in the dark forest.")
            return "dead"
    else:
        print_slow("You reach into your bag and offer the wolf some food. It sniffs cautiously before taking it.")
        print_slow("Satisfied, the wolf retreats into the woods, leaving the path clear.")
        return "safe"

def encounter_river():
    print_slow("The right path leads you to a roaring river, its waters churning with unrelenting force.")
    print_slow("The sound of the rushing water drowns out all other noise, and the cold spray chills you to the bone.")
    print_slow("You notice debris floating downstream, hinting at the river's strength.")
    print("1. Swim across")
    print("2. Build a raft")
    print("3. Look for a bridge")
    action = input("What will you do? (1, 2, or 3): ").strip()
    while action not in ["1", "2", "3"]:
        action = input("Invalid choice. Please select 1, 2, or 3: ").strip()

    if action == "1":
        print_slow("You take a deep breath and dive into the freezing water. The current pulls at you with incredible force.")
        if random.random() > 0.5:
            print_slow("After an exhausting struggle, you reach the other side, shivering and barely able to stand.")
            return "safe"
        else:
            print_slow("The current proves too strong. Despite your efforts, the river sweeps you away.")
            return "dead"
    elif action == "2":
        print_slow("You gather logs, vines, and anything else you can find to construct a makeshift raft.")
        print_slow("It takes hours, and your hands are blistered, but eventually, the raft is ready.")
        print_slow("You set off down the river, the raft creaking ominously as it carries you to safety on the other side.")
        return "safe"
    else:
        print_slow("You follow the riverbank for what feels like miles, your legs growing weary.")
        print_slow("Finally, you discover a rickety old bridge hidden behind dense undergrowth.")
        print_slow("The bridge creaks and sways as you cross, but it holds, and you make it to the other side.")
        return "safe"

def encounter_castle():
    print_slow("The path straight ahead leads you to an ancient castle, its towers silhouetted against the dark clouds.")
    print_slow("The gates are slightly ajar, and a faint, flickering light emanates from within.")
    print_slow("An eerie silence surrounds the castle, broken only by the occasional distant thunder.")
    print("1. Enter the castle")
    print("2. Walk around it")
    print("3. Turn back")
    action = input("What will you do? (1, 2, or 3): ").strip()
    while action not in ["1", "2", "3"]:
        action = input("Invalid choice. Please select 1, 2, or 3: ").strip()

    if action == "1":
        print_slow("You push open the heavy doors and step into the castle. The air is thick with dust and the scent of decay.")
        print_slow("In the grand hall, you see piles of gold and jewels, but a massive dragon sleeps atop them.")
        print("1. Steal the treasure")
        print("2. Sneak away")
        action = input("What will you do? (1 or 2): ").strip()
        while action not in ["1", "2"]:
            action = input("Invalid choice. Please select 1 or 2: ").strip()
        if action == "1":
            print_slow("As you reach for the treasure, the dragon's eyes snap open. It roars, and flames engulf the room.")
            print_slow("Your greed has cost you your life.")
            return "dead"
        else:
            print_slow("You carefully back away, avoiding the dragon's gaze. Some risks aren't worth taking.")
            return "safe"
    elif action == "2":
        print_slow("You walk around the castle and discover a hidden garden filled with vibrant, glowing plants.")
        print_slow("The air is fresh, and you feel rejuvenated as you rest among the flora.")
        return "safe"
    else:
        print_slow("Deciding the castle is too dangerous, you turn back and retrace your steps into the forest.")
        return "safe"

def encounter_cave():
    print_slow("A hidden path leads you to the entrance of a dark cave. Stalactites hang ominously from the ceiling.")
    print_slow("The cave mouth exhales cold air, carrying a faint metallic scent of danger.")
    print_slow("You hear faint echoes from within, and your heart races as you step inside.")
    print("1. Explore deeper")
    print("2. Collect glowing crystals")
    print("3. Turn back")
    action = input("What will you do? (1, 2, or 3): ").strip()
    while action not in ["1", "2", "3"]:
        action = input("Invalid choice. Please select 1, 2, or 3: ").strip()

    if action == "1":
        print_slow("You venture deeper into the cave, the light fading as the air grows colder.")
        if random.random() > 0.5:
            print_slow("You discover an underground lake shimmering with bioluminescent life. It's breathtakingly beautiful.")
            return "safe"
        else:
            print_slow("The ground beneath you gives way, and you fall into a hidden chasm, never to be seen again.")
            return "dead"
    elif action == "2":
        print_slow("You carefully collect some of the glowing crystals. They hum faintly in your hands.")
        print_slow("As you leave the cave, the crystals light your way, ensuring your safe return.")
        return "safe"
    else:
        print_slow("Deciding the cave is too risky, you
import random
import time

def print_slow(text, delay=0.05):
    for char in text:
        print(char, end="", flush=True)
        time.sleep(delay)
    print()

def create_character():
    print("Welcome to the RPG Adventure!")
    name = input("Enter your character's name: ").strip()
    print_slow(f"Hello, {name}. Let's set up your character.")

    print("Choose your class:")
    print("1. Warrior - Strong and resilient.")
    print("2. Mage - Master of the arcane arts.")
    print("3. Rogue - Quick and cunning.")

    while True:
        choice = input("Enter the number of your class (1, 2, or 3): ").strip()
        if choice == "1":
            character_class = "Warrior"
            hp = 150
            attack = 20
            break
        elif choice == "2":
            character_class = "Mage"
            hp = 100
            attack = 30
            break
        elif choice == "3":
            character_class = "Rogue"
            hp = 120
            attack = 25
            break
        else:
            print("Invalid choice. Please select 1, 2, or 3.")

    print_slow(f"You chose {character_class}. Your adventure begins now!")
    return {"name": name, "class": character_class, "hp": hp, "attack": attack}

def encounter_enemy():
    enemies = ["Goblin", "Orc", "Bandit", "Skeleton"]
    enemy = random.choice(enemies)
    enemy_hp = random.randint(50, 100)
    enemy_attack = random.randint(10, 20)

    print_slow(f"A wild {enemy} appears! It has {enemy_hp} HP and {enemy_attack} attack power.")
    return {"name": enemy, "hp": enemy_hp, "attack": enemy_attack}

def battle(player, enemy):
    print_slow(f"Battle starts between {player['name']} and {enemy['name']}!")

    while player["hp"] > 0 and enemy["hp"] > 0:
        print(f"Your HP: {player['hp']} | {enemy['name']} HP: {enemy['hp']}")
        print("1. Attack")
        print("2. Defend")
        print("3. Run")

        choice = input("What will you do? (1, 2, or 3): ").strip()

        if choice == "1":
            damage = random.randint(player["attack"] - 5, player["attack"] + 5)
            enemy["hp"] -= damage
            print_slow(f"You deal {damage} damage to the {enemy['name']}.")
        elif choice == "2":
            print_slow("You brace yourself for the enemy's attack.")
            continue
        elif choice == "3":
            if random.random() > 0.5:
                print_slow("You successfully escaped!")
                return "escaped"
            else:
                print_slow("You failed to escape!")
        else:
            print("Invalid choice.")
            continue

        if enemy["hp"] > 0:
            enemy_damage = random.randint(enemy["attack"] - 5, enemy["attack"] + 5)
            player["hp"] -= enemy_damage
            print_slow(f"The {enemy['name']} deals {enemy_damage} damage to you.")

    if player["hp"] <= 0:
        print_slow("You have been defeated. Your adventure ends here.")
        return "defeated"
    elif enemy["hp"] <= 0:
        print_slow(f"You defeated the {enemy['name']}! Congratulations!")
        return "victory"

def explore(player):
    print_slow("You venture into the unknown...")
    outcome = random.choice(["treasure", "enemy", "trap"])

    if outcome == "treasure":
        treasure = random.randint(10, 50)
        print_slow(f"You find a hidden treasure chest with {treasure} gold coins!")
        player["gold"] += treasure
    elif outcome == "enemy":
        enemy = encounter_enemy()
        result = battle(player, enemy)
        if result == "defeated":
            return "game_over"
    elif outcome == "trap":
        damage = random.randint(10, 30)
        player["hp"] -= damage
        print_slow(f"You trigger a trap and lose {damage} HP!")

    if player["hp"] <= 0:
        print_slow("The trap proved too much. Your journey ends here.")
        return "game_over"

    return "continue"

def main():
    player = create_character()
    player["gold"] = 0

    while True:
        print("\nWhat would you like to do?")
        print("1. Explore")
        print("2. Check Stats")
        print("3. Rest")
        print("4. Quit")

        choice = input("Enter your choice: ").strip()

        if choice == "1":
            result = explore(player)
            if result == "game_over":
                break
        elif choice == "2":
            print("\nCharacter Stats:")
            print(f"Name: {player['name']}")
            print(f"Class: {player['class']}")
            print(f"HP: {player['hp']}")
            print(f"Attack: {player['attack']}")
            print(f"Gold: {player['gold']}")
        elif choice == "3":
            print_slow("You find a safe place to rest and recover.")
            player["hp"] += random.randint(10, 30)
            print_slow(f"Your HP is now {player['hp']}.")
        elif choice == "4":
            print_slow("Thank you for playing! Goodbye!")
            break
        else:
            print("Invalid choice.")

if __name__ == "__main__":
    main()
import random
import time

# Utility function to display text slowly
def print_slow(text, delay=0.05):
    for char in text:
        print(char, end="", flush=True)
        time.sleep(delay)
    print()

# Word bank for the game
WORD_BANK = [
    "python", "adventure", "computer", "programming", "artificial", "intelligence",
    "development", "analysis", "simulation", "keyboard", "monitor", "variable",
    "function", "iteration", "recursion", "dictionary", "algorithm", "optimization"
]

# Function to choose a random word
def choose_word():
    return random.choice(WORD_BANK)

# Function to display the game state
def display_game_state(word, guessed_letters):
    display = "".join([letter if letter in guessed_letters else "_" for letter in word])
    print("Word: ", display)

# Function to handle the player's guess
def handle_guess(word, guessed_letters):
    while True:
        guess = input("Enter a letter: ").strip().lower()
        if len(guess) == 1 and guess.isalpha():
            if guess in guessed_letters:
                print("You already guessed that letter. Try again.")
            else:
                return guess
        else:
            print("Invalid input. Please enter a single letter.")

# Function to check if the game is won
def is_word_guessed(word, guessed_letters):
    return all(letter in guessed_letters for letter in word)

# Function to display the game's rules
def display_rules():
    print("Welcome to 'Guess the Word'!")
    print("The objective is to guess the hidden word one letter at a time.")
    print("You have 6 attempts to guess the word before you lose the game.")
    print("Let's begin!")

# Main game logic
def play_game():
    word = choose_word()
    guessed_letters = set()
    attempts_left = 6

    print_slow("\nA random word has been chosen. Can you guess it?")
    print("\nYou have 6 attempts. Good luck!")

    while attempts_left > 0:
        display_game_state(word, guessed_letters)
        print(f"Attempts left: {attempts_left}")
        print(f"Guessed letters: {', '.join(sorted(guessed_letters))}")

        guess = handle_guess(word, guessed_letters)
        guessed_letters.add(guess)

        if guess in word:
            print_slow(f"Good job! The letter '{guess}' is in the word.")
        else:
            print_slow(f"Sorry, the letter '{guess}' is not in the word.")
            attempts_left -= 1

        if is_word_guessed(word, guessed_letters):
            display_game_state(word, guessed_letters)
            print_slow("\nCongratulations! You've guessed the word correctly and won the game!")
            return

    print_slow("\nYou've run out of attempts. The word was:")
    print(f"{word}")
    print_slow("Better luck next time!")

# Main menu

def main():
    while True:
        print("\n=== Guess the Word ===")
        print("1. Play Game")
        print("2. Rules")
        print("3. Exit")

        choice = input("Enter your choice (1, 2, or 3): ").strip()

        if choice == "1":
            play_game()
        elif choice == "2":
            display_rules()
        elif choice == "3":
            print("Thank you for playing! Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
import json
import os

class Todo:
    def __init__(self, title, completed=False):
        self.title = title
        self.completed = completed

    def __repr__(self):
        return f"{'[x]' if self.completed else '[ ]'} {self.title}"

class TodoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, title):
        task = Todo(title)
        self.tasks.append(task)
        print(f"Added task: {task}")

    def view_tasks(self):
        if not self.tasks:
            print("No tasks available.")
            return
        for index, task in enumerate(self.tasks, start=1):
            print(f"{index}. {task}")

    def delete_task(self, index):
        if 0 <= index < len(self.tasks):
            removed_task = self.tasks.pop(index)
            print(f"Deleted task: {removed_task}")
        else:
            print("Invalid task number.")

    def complete_task(self, index):
        if 0 <= index < len(self.tasks):
            self.tasks[index].completed = True
            print(f"Completed task: {self.tasks[index]}")
        else:
            print("Invalid task number.")

    def save_to_file(self, filename):
        with open(filename, 'w') as file:
            json.dump([task.__dict__ for task in self.tasks], file)
        print(f"Tasks saved to {filename}")

    def load_from_file(self, filename):
        if os.path.exists(filename):
            with open(filename, 'r') as file:
                tasks_data = json.load(file)
                self.tasks = [Todo(**task) for task in tasks_data]
            print(f"Tasks loaded from {filename}")
        else:
            print(f"{filename} does not exist.")

def display_menu():
    print("\nTodo List Menu:")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Delete Task")
    print("4. Complete Task")
    print("5. Save Tasks")
    print("6. Load Tasks")
    print("7. Exit")

def main():
    todo_list = TodoList()
    filename = "tasks.json"

    while True:
        display_menu()
        choice = input("Choose an option (1-7): ")

        if choice == '1':
            title = input("Enter task title: ")
            todo_list.add_task(title)
        elif choice == '2':
            todo_list.view_tasks()
        elif choice == '3':
            todo_list.view_tasks()
            index = int(input("Enter task number to delete: ")) - 1
            todo_list.delete_task(index)
        elif choice == '4':
            todo_list.view_tasks()
            index = int(input("Enter task number to complete: ")) - 1
            todo_list.complete_task(index)
        elif choice == '5':
            todo_list.save_to_file(filename)
        elif choice == '6':
            todo_list.load_from_file(filename)
        elif choice == '7':
            print("Exiting the program.")
            break
        else:
            print("Invalid choice. Please try again.")


if __name__ == "__main__":
    main()
