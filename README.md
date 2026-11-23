<h1>ExpNo 9: Solve Wumpus World Problem using Python demonstrating Inferences from Propositional Logic</h1> 
<h3>Name:                       </h3>
<h3>Register Number/Staff Id:                </h3>
<H3>Aim:</H3>
<p>
    To solve  Wumpus World Problem using Python demonstrating Inferences from Propositional Logic
</p>
<h1>Problem Description</h1>
<hr>
<h2>Wumpus World</h2>
<hr>
The Wumpus world is a simple world example to illustrate the worth of a knowledge-based agent and to represent knowledge representation.

The figure below shows a Wumpus world containing one pit and one Wumpus. There is an agent in room [1,1]. The goal of the agent is to exit the Wumpus world alive. The agent can exit the Wumpus world by reaching room [4,4]. The wumpus world contains exactly one Wumpus and one pit. There will be a breeze in the rooms adjacent to the pit, and there will be a stench in the rooms adjacent to Wumpus.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/cd6b68dc-c79f-4dcb-8126-04da90d65912)

<center>Wumpus World Representation</center>
<p>
This is a python program that uses propositional logic sentences to check which rooms are safe. 

It is assumed that there will always be a safe path that the agent can take to exit the Wumpus world. The logical agent can take four actions: Up, Down, Left and Right. These actions help the agent move from one room to an adjacent room. The agent can perceive two things: Breeze and Stench.
</p>

<hr>
<h1>Sample Input and Output:</h1>
<hr>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8696111a-a4a7-47cb-ba4b-43a4ef88573f)
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/4be5bf06-79fa-4fa0-9334-38a33f06060b)

# program:
```

wumpus = [
    ["Save", "Breeze", "PIT", "Breeze"],
    ["Smell", "Save", "Breeze", "Save"],
    ["WUMPUS", "GOLD", "PIT", "Breeze"],
    ["Smell", "Save", "Breeze", "PIT"]
]

row = 0
column = 0
arrow = True
player = True
score = 0

while player:
    print("\nPress u to move up")
    print("Press d to move down")
    print("Press l to move left")
    print("Press r to move right")

    choice = input("Enter your choice: ").lower()

    if choice == "u":
        if row > 0:
            row -= 1
        else:
            print("Move denied")

    elif choice == "d":
        if row < 3:
            row += 1
        else:
            print("Move denied")

    elif choice == "l":
        if column > 0:
            column -= 1
        else:
            print("Move denied")

    elif choice == "r":
        if column < 3:
            column += 1
        else:
            print("Move denied")

    else:
        print("Invalid choice")
        continue

    print("Current location:", wumpus[row][column])

    if wumpus[row][column] == "WUMPUS":
        score -= 1000
        print("You encountered the Wumpus!")
        print("Your score is:", score)
        break

    elif wumpus[row][column] == "PIT":
        score -= 1000
        print("You fell into the pit!")
        print("Your score is:", score)
        break

    elif wumpus[row][column] == "GOLD":
        score += 1000
        print("GOLD FOUND! You won!")
        print("Your score is:", score)
        break

    elif wumpus[row][column] == "Breeze":
        print("Warning: Breeze detected!")

    elif wumpus[row][column] == "Smell":
        print("Warning: Stench detected!")

    else:
        print("The room is safe!")
```
# output:
<img width="417" height="805" alt="image" src="https://github.com/user-attachments/assets/c872dd98-2a4a-47fe-82a4-7672ab25c989" />
