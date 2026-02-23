<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: NANDEESWARI A</h3>
<h3>Register Number: 212224220068 </h3>


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
<hr>
<h3>PYTHON IMPLEMENTATION:</h3>

<pre>
<code>
# Medicine Prescribing AI Agent using PEAS Description

class MedicineAgent:
    def __init__(self, location, rooms):
        self.location = location
        self.rooms = rooms
        self.performance = 0

    def sense_temperature(self):
        return self.rooms[self.location]

    def treat_patient(self):
        if self.sense_temperature() > 98.5:
            print("Patient has fever in", self.location)
            print("Prescribing Medicine...")
            self.rooms[self.location] = 98.0
            self.performance += 10
        else:
            print("Patient is Healthy in", self.location)

    def move(self):
        if self.location == "Room A":
            self.location = "Room B"
        else:
            self.location = "Room A"
        print("Moving to", self.location)
        self.performance -= 1

    def run(self, steps):
        for i in range(steps):
            print("\nStep:", i+1)
            print("Current Location:", self.location)
            print("Temperature:", self.rooms[self.location])
            self.treat_patient()
            self.move()

        print("\nFinal Room Status:", self.rooms)
        print("Performance Score:", self.performance)


rooms = {
    "Room A": 99.0,
    "Room B": 97.0
}

agent = MedicineAgent("Room A", rooms)
agent.run(5)
</code>
</pre>
<h3>OUTPUT:</h3>
<img width="706" height="712" alt="image" src="https://github.com/user-attachments/assets/c839b02e-3748-45ae-8f59-f03a77fd8577" />
<img width="706" height="305" alt="image" src="https://github.com/user-attachments/assets/f21fb4b7-62a0-4249-b780-0dc770f48b5b" />



