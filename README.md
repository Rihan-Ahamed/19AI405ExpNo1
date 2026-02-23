<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Rihan Ahamed.S</h3>
<h3>Register Number: 212224040276</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

CODE:
```py
import random

# Initialize performance
performance = 0

# Randomly choose starting room
current_room = random.choice(["Room A", "Room B"])

print("Medicine Prescribing Agent Started")
print("Starting in", current_room)
print("----------------------------------")

while True:
    print("\nCurrently in", current_room)
    
    # Get temperature input
    temp = float(input("Enter patient temperature in " + current_room + ": "))
    
    # Check patient condition
    if temp > 98.5:
        print("Patient is unhealthy. Prescribing medicine...")
        performance += 1
    else:
        print("Patient is healthy. No treatment needed.")
    
    # Ask user if continue
    choice = input("\nDo you want to continue? (yes/no): ").lower()
    
    if choice == "no":
        break
    
    # Move to the other room
    if current_room == "Room A":
        current_room = "Room B"
    else:
        current_room = "Room A"
    
    print("Moving to", current_room)
    performance -= 1  # movement cost

print("\n----------------------------------")
print("Final Performance Score:", performance)
print("Agent Stopped.")
```
<H3>OUTPUT:</H3>
<img width="509" height="697" alt="image" src="https://github.com/user-attachments/assets/c1eae5ba-d434-4a2e-8bb4-119030ec5bc8" />

<H3>RESULT:</H3>
<p>The Medicine Prescribing Agent successfully monitors two rooms, prescribes medicine when the patient’s temperature is greater than 98.5°F, updates performance based on treatment and movement, and continues execution until the user chooses to stop.</p>
