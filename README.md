# 4_way_traffic_light_controller
A traffic light controller is a system that manages the operation of traffic lights at intersections or other road junctions.
Its purpose is to regulate and optimize the flow of traffic, ensuring safety and efficient movement of vehicles and pedestrians.

Traffic light controller module that controls the operation of traffic lights at an intersection. Here is a description of the code:

Inputs:

clk: The clock signal used for synchronous operations.
rst: The reset signal used to initialize the module.
alert1, alert2: Alert signals indicating specific events like collisions or accidents.
emrg: Emergency signal indicating the presence of an emergency vehicle.
sensor_north, sensor_east, sensor_south, sensor_west: Sensors for detecting vehicles approaching from different directions.

Outputs:

NS, NW, EW, EN, SN, SE, WE, WS: Control signals for the traffic lights, representing different directions (North-South, North-West, East-West, etc.).
ambulance, police: Alert signals indicating the presence of an ambulance or police vehicle.
count: A counter variable for timing purposes.
The module also defines several parameters:

red, yellow, green: Binary values representing the different states of a traffic light.
sec30, sec10, sec5: Time durations for different signal phases.
The module contains a state machine that controls the traffic light operation. 
It defines eight states using the "s0" to "s7" parameters. 
The "ps" variable represents the present state of the state machine.

The first always block triggers on the positive edge of the clock or reset signal. 
It controls the state transitions and the count variable. 
Depending on the present state, sensor inputs, and count value, it updates the present state and count.

The second always block triggers on changes in the present state or the emergency signal.
It determines the output signal values based on the present state. 
When an emergency signal is detected, all traffic lights are set to red.

The third always block triggers on the positive edge of the clock or when alert1 or alert2 signals are asserted.
It updates the values of the ambulance and police output signals based on the occurrence of accidents or collisions.

In summary, this Verilog code implements a traffic light controller that follows a specific sequence of state transitions to
control the traffic lights at an intersection. It also incorporates emergency vehicle alerts and accident detection mechanisms.
