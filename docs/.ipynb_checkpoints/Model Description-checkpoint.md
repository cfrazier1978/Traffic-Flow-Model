# Traffic Flow Model
## Goal
The goal of this model is to create a digital twin of vehicles moving through a stretch of road.  I want to measure how long it takes a vehicle to travel from the beginning to the end of the road.  I want to measure how other factors affect the speed of movement such as:
- Driving behaviors
- Road conditions
- Number of onramps and offramps
- Accidents
- Lanes of traffic
- Number of vehicles on the road
- Types of vehicles on the road (emergency vehicles, state troopers, semis, construction vehicles)
- Lane closures
- Speed limit changes

I believe that the flow of traffic is a very complex system that if it can be modeled, then policy decisions can be made to improve traffic flow or assess necessary changes with more information.

## Model Abstract
Imagine you had the ability to hover high in the sky and observe a section of road to better understand the traffic conditions of the road.  What if you could see some repeated patterns that could be rectified, reducing the amount of traffic and the reduced speeds on the road?

This model is going to focus on a single vehicle on a road of many different road conditions.  The vehicle will begin at the starting point and the model will end when the vehicle reaches the end.  Each timestep will be one movement of the focus vehicle along with all other vehicles on the road.  The focus vehicle will have a desired speed, which will determine how far it makes it each time step, but this will be affected by the differing road conditions.

## Background
There are many times when driving that I get stuck in traffic and when you finally are able to get back to your desired speed, it isn’t always clear what caused the slowdown.  Sometimes it is obvious, there is an accident or a lane is closed for construction.  Or it could be a heavy traffic area due to ‘rush hour’.  But other times it is just slow, then it isn’t slow.  One would need to measure what is happening to rectify these recurring problems.

## Simple Use Case
The first version of this model will measure the focus vehicle with no other vehicles on the road in a single lane of traffic.  The length of the road will start short.  It can be expanded once the basic model is working.  Once the model can be built to represent a single vehicle, then a second vehicle will be added in front of the focus vehicle that is traveling at a slower speed, to make sure that I can measure the impact.

## Model Rules
- No two vehicles can be in the same space, but that may be violated in the future to create the occurrence of an accident.
- A vehicle can not travel through another vehicle, it would need to go around.
- A vehicle behind another vehicle can go no faster than the front vehicle.
- There will be a speed limit set for the road, or for sections of the road.  The driver’s personality will dictate how they react to the speed limit.
- All vehicles on the road desire to travel from their starting point to the end point unless there are extenuating circumstances.  No vehicle will treat the road as a parking lot unless an accident or breakdown of their vehicle causes this action.

## Assumptions
N/A, all the variables of this model are known.

## Random Variables
- The driver behavior will be randomly assigned.
- The type of a new vehicle will be randomly determined.

## Agents
Each vehicle will be its own agent with its own driving behavior for traveling through the road.  Some agents will have behaviors that are specific to the section of road, such as an emergency vehicle trying to clear an accident, a state trooper trying to pull over dangerous drivers or a construction vehicle trying to enter or leave a construction site on the roadway.

## Initial Conditions
- Number of Lanes: 1+ lanes for vehicles to travel on.
- Number of onramps: 0+ lanes for vehicles to enter the roadway.
- Number of offramps: 0+ lanes for vehicles to exit the roadway.
- Number of existing vehicles: How many vehicles start at a location on the road.
- Number of lanes obstructed: 0+ lanes that will be blocked.  This could be due to an accident or construction.
- Number of state troopers: 0+ police vehicles monitoring for dangerous behavior.
- Miles or Kilometers: Determine if the model will use miles or kilometers.
- Length of Road: How long is the road (in miles or kilometers).

## KPIs
- How long did it take the focus vehicle to travel the road vs how long it would have taken with no road conditions at the speed limit.
- What was the average travel speed of all vehicles compared to the speed limit.
- - Also average speed by section of roadway.  For example, was there more slowdown around an onramp compared to other sections of road?
- Track the number of specific incidents that occurred during the simulation:
- - Number of accidents
- - Number of semis
- - Number of construction vehicles
- - Number of state patrol
- - Number of drives assigned a dangerous driving behavior

## Model Coding Considerations
The biggest challenge I will face in programming this model is learning how to handle the spatial element of different agents on a plane.  Once I learn how to do this, I think the rest of the logic will be easier to program.

## Model Elements
TBD

## Model Flow Chart
TBD

## Experiments

|Experiment Number|Experiment Name|Length of Road|Number of Lanes|Number of Onramps|Number of Offramps|Num Additional Vehicles|Vehicle Types|Number of lanes obstructed|Num State Troopers|Description & Hypothesis|
|---|---|---|---|---|---|---|---|---|---|---|
|1|POC|1 Mile|1|0|0|0|N/A|0|0|Create a model that can track the location of a vehicle along an area going a set speed for a set distance.|
|2|One Other Vehicle|1 Mile|1|0|0|1|Car|0|0|Create the interaction between another vehicle traveling at a slower speed.|
|3|New Lane|1 Mile|2|0|0|1|Car|0|0|Add the ability for the focus car to determine that it wants to pass and move into the next lane.|
|4|More Vehicles|1 Mile|2|0|0|4|Car|0|0|Create multiple interactions as the focus vehicle travels down the road.|

## Adding Complexity
There are a lot of areas for adding complexity to this model.  After the simple version is done, a single new driving behavior, road condition or vehicle type will be added like you are leveling up in a video game.

Elements of complexity:
- Driving behaviors
- Road conditions
- Number of onramps and offramps
- Accidents
- Lanes of traffic
- Number of vehicles on the road
- Types of vehicles on the road (emergency vehicles, state troopers, semis, construction vehicles)
- Lane closures
- Speed limit changes

