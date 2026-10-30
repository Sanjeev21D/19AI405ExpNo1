<h1>ExpNo 1 : Developing AI Agent with PEAS Description</h1>
<h3>Name: Sanjeev D</h3>
<h3>Register Number: 212223040185 </h3>

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
    <th>Agent Type</th>
    <th>Performance</th>
    <th>Environment</th>
    <th>Actuators</th>
    <th>Sensors</th>
  </tr>
  <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td>Treating unhealthy, agent movement</td>
    <td>Rooms, Patient</td>
    <td>Medicine, Treatment</td>
    <td>Location, Temperature of patient</td>
  </tr>
</table>
<hr>

<h3>DESIGN STEPS</h3>
<h3>STEP 1: Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2: Identifying the output:</h3>
<p>Prescribe medicine if the patient in a room has a fever / abnormal vitals.</p>
<h3>STEP 3: Developing the PEAS description:</h3>
<p>PEAS description is developed by defining the Performance, Environment, Actuators, and Sensors for the agent.</p>
<h3>STEP 4: Implementing the AI agent:</h3>
<p>Sense patient vitals (heart rate, blood pressure, temperature) and execute the appropriate clinical action based on rule thresholds.</p>
<h3>STEP 5: Measuring performance parameters:</h3>
<p>Evaluate agent response against abnormal states until condition stabilizes ("No specific action needed").</p>

<h3>PROGRAM</h3>
<hr>

```python
import random

class HealthMonitoringAgent:
    def __init__(self, patient_data):
        self.patient_data = patient_data

    def monitor_health(self):
        while True:
            current_health_state = self.sensors.get_health_state()
            action = self.choose_action(current_health_state)
            self.actuators.perform_action(action)
            if self.choose_action(current_health_state) == "No specific action needed":
                break

    def choose_action(self, current_health_state):
        # Rule-based system for decision-making
        if current_health_state['heart_rate'] > 120:
            return "Alert healthcare provider: High heart rate detected"
        elif current_health_state['blood_pressure'] > 140:
            return "Alert healthcare provider: High blood pressure detected"
        elif current_health_state['temperature'] > 38:
            return "Recommend rest and monitor temperature"
        else:
            return "No specific action needed"

class HealthSensors:
    def get_health_state(self):
        # Simulate health data retrieval
        return {
            'heart_rate': random.randint(60, 150),
            'blood_pressure': random.randint(90, 160),
            'temperature': random.uniform(36.0, 38.5)
        }

class HealthActuators:
    def perform_action(self, action):
        print(action)

if __name__ == "__main__":
    patient_data = {'patient_id': 123, 'name': 'John Doe', 'age': 35}
    
    health_sensors = HealthSensors()
    health_actuators = HealthActuators()
    
    health_monitoring_agent = HealthMonitoringAgent(patient_data)
    health_monitoring_agent.sensors = health_sensors
    health_monitoring_agent.actuators = health_actuators
    
    health_monitoring_agent.monitor_health()
```
<hr>

<h3>OUTPUT:</h3>

```text
Alert healthcare provider: High heart rate detected
Alert healthcare provider: High blood pressure detected
Alert healthcare provider: High heart rate detected
No specific action needed
```

<img width="433" height="104" alt="image" src="https://github.com/user-attachments/assets/a11871cf-04e7-4e0e-858e-28419c4df383" />

<h3>RESULT</h3>
<p>Hence, the PEAS description was formulated and the Health Monitoring AI Agent was successfully developed and implemented.</p>
