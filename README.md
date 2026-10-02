# PROJECT2
PERSONAL PROJECT
# Name: Syniamosley1
# Date: 2026-09-25
# Description: A short branching text adventure with health, endings, and invalid-choice handling

# Commit 1: Initialize branching text adventure
# Commit 2: Add health system and invalid-choice handling
# Commit 3: Implement win/lose endings and decision paths

health = 10
print("Health:", health)

first = input("Choose a path: left or right? ")

if (first == "left" or first == "right") and health > 0:
    if first == "left":
        health = health - 2
        print("Health:", health)

        second = input("A monster blocks the trail. Do you fight or run? ")

        if second == "fight":
            health = health - 3
            print("Health:", health)

            third = input("You find a treasure chest. Do you take it or leave it? ")

            if third == "take":
                print("=== YOU WIN ===")
            elif third == "leave":
                health = health - 2
                print("Health:", health)
                print("=== GAME OVER ===")
            else:
                print("Invalid choice.")
        elif second == "run":
            health = health - 4
            print("Health:", health)
            print("=== GAME OVER ===")
        else:
            print("Invalid choice.")

    elif first == "right":
        health = health - 1
        print("Health:", health)

        second = input("The path turns dark. Do you run or fight? ")

        if second == "run":
            health = health - 4
            print("Health:", health)

            third = input("You reach the ruins. Do you leave or hide? ")

            if third == "leave":
                print("=== GAME OVER ===")
            elif third == "hide":
                print("=== YOU WIN ===")
            else:
                print("Invalid choice.")
        elif second == "fight":
            health = health - 3
            print("Health:", health)
            print("=== GAME OVER ===")
        else:
            print("Invalid choice.")
else:
    print("Invalid choice.")
