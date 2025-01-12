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
