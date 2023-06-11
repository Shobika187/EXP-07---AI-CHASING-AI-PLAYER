# EXP-07---AI-CHASING-AI-PLAYER
## AIM:
To implement-chasing when AI see the player.

## ALGORITHM:
### STEP 1: Set up the AI character Blueprint:
```
i)Create an AI character Blueprint (if you haven't already) following the steps mentioned earlier.
ii)Add a Sphere Collision component to the AI character Blueprint.
iii)Position and scale the Sphere Collision component to represent the AI's detection range.
iv)Set the Sphere Collision component's collision settings to overlap with the player character.
```
### STEP 2: Create a new AI controller Blueprint:
```
i)In the Content Browser, right-click in the desired folder.
ii)Select Create Basic Asset > Blueprint Class.
iii)Choose the AIController as the parent class.
iv)Name the Blueprint (e.g., "AIController_Chase") and click Create.
```
### STEP 3: Open the AIController Blueprint:
```
i)In the Blueprint editor, locate the Event Begin Play event.
ii)Drag off the execution line and search for "Set Sight Radius".
iii)Set the Sight Radius value to the desired range for the AI's vision.
iv)Drag off the execution line again and search for "Set Peripheral Vision Angle".
v)Set the Peripheral Vision Angle value to the desired field of view for the AI's vision.
```
### STEP 4: Implement perception for the AI:
```
i)Drag off the execution line in the Begin Play event and search for "Create and Configure AI Perception Component".
ii)Connect the output of the AI Perception Component node to the AI Controller's AI Perception property.
iii)In the AI Perception Component node, configure the settings for sight and sight sense.
iv)Drag off the AI Perception Component node and search for "Update Perception".
v)Connect the output of the Update Perception node to the Event Tick event.
vi)In the Update Perception node, select "Sight" as the stimulus to update.
vii)Connect the output of the AI Perception Component to a "For Each Loop" node to iterate through all perceived stimuli.
```
### STEP 5: Implement the chase behavior:
```
i)Inside the For Each Loop, check if the perceived stimulus is the player character.
ii)If the stimulus is the player character, drag off the execution line and search for "Move To Actor".
iii)Set the Move To Actor node's target to the player character.
iv)Connect the output of the Move To Actor node to the AI Controller's Move To Location input.
```
### STEP 6: Create blackboard keys for the AI
```
i)Open the AIController Blueprint.
ii)In the Blueprint editor, locate the Event Begin Play event.
iii)Drag off the execution line and search for "Create Blackboard".
iv)Create a new blackboard object and assign it to the AIController's Blackboard property.
v)Drag off the execution line again and search for "Create Blackboard Key".
vi)Create a new key for the blackboard, such as "PlayerLocation".
vii)Connect the output of the Create Blackboard Key node to the AIController's Blackboard property
```
### STEP 7: Update blackboard values:
```
i)In the AIController Blueprint, find the Event Tick event.
ii)Drag off the execution line and search for "Get Player Character".
iii)Drag off the player character reference and search for "Get Actor Location".
iv)Connect the output of the Get Actor Location node to the AIController's Set Blackboard Value As Vector input.
v)Set the Blackboard Key to the "PlayerLocation" key you created earlier
```
### STEP 8: Set up the Behavior Tree:
```
i)Create a Behavior Tree asset following the steps mentioned earlier.
ii)Open the Behavior Tree asset in the Behavior Tree editor.
iii)Drag and drop a "Blackboard Key Selector" node onto the graph
iv)Configure the Blackboard Key Selector node to use the "PlayerLocation" key
```
## OUTPUT:
### Blackboard Key Creation:
![image](https://github.com/Shobika187/EXP-07---AI-CHASING-AI-PLAYER/assets/94508142/eb66c403-1143-4e5b-9efd-e7714a7e12de)
### Behaviour Tree:
![image](https://github.com/Shobika187/EXP-07---AI-CHASING-AI-PLAYER/assets/94508142/d2771aff-7a39-4b80-b026-7fc1d3ceb647)
### Setting Player Key Sequence Node:
![image](https://github.com/Shobika187/EXP-07---AI-CHASING-AI-PLAYER/assets/94508142/05d6ee18-0e19-441f-b7e3-332d2ea25d04)
### Setting Player Key to Move Node:
![image](https://github.com/Shobika187/EXP-07---AI-CHASING-AI-PLAYER/assets/94508142/6c08d755-838b-41b7-9abb-50f77b87e641)
### Setting Player Ley to BB Rotate Node:
![image](https://github.com/Shobika187/EXP-07---AI-CHASING-AI-PLAYER/assets/94508142/e9836144-6532-4d4c-8041-90f7273890cc)
### Adding AI Perception Node:
![image](https://github.com/Shobika187/EXP-07---AI-CHASING-AI-PLAYER/assets/94508142/238710b7-f2f4-4cc4-bf1c-3af275b16e29)
### AI Controller Graph:
![image](https://github.com/Shobika187/EXP-07---AI-CHASING-AI-PLAYER/assets/94508142/d8c6e89a-2498-4219-97c0-ec49ad95cbc6)
### AI Controller Class Selection:
![image](https://github.com/Shobika187/EXP-07---AI-CHASING-AI-PLAYER/assets/94508142/1cbe05d8-2ea6-485d-84ca-b34b22132914)
### AI Sense Configuration:
![image](https://github.com/Shobika187/EXP-07---AI-CHASING-AI-PLAYER/assets/94508142/5a1266c9-aa40-4654-b25b-b39894a03051) 
### Game Mode:
![image](https://github.com/Shobika187/EXP-07---AI-CHASING-AI-PLAYER/assets/94508142/39355adf-a6f2-4891-834b-74cb7550030e)
### RESULT:
Thus, the AI concept to the actor for chasing when AI sees the player.






