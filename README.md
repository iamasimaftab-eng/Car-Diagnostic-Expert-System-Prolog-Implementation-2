Overview

This project implements a rule-based expert system for automobile fault diagnosis using Prolog. The system simulates the reasoning process of an automotive technician by analyzing vehicle symptoms and identifying possible faults.

The expert system uses knowledge representation and logical inference to determine the causes of vehicle problems based on observed symptoms. It applies a rule-based diagnostic model, where symptoms are linked to possible faults and those faults are categorized into vehicle subsystems such as engine, fuel system, electrical system, ignition system, cooling system, exhaust system, and starting system.

The system demonstrates how artificial intelligence techniques, particularly expert systems, can be applied to real-world problem solving in vehicle diagnostics.

Project Objectives

The primary objectives of this project are:

To design a knowledge-based expert system for diagnosing automobile faults.

To represent vehicle diagnostic knowledge using Prolog facts and rules.

To simulate mechanic-like reasoning using backward chaining inference.

To classify faults based on vehicle subsystems.

To demonstrate the use of rule-based AI systems in technical diagnostics.

Repository Structure
Automobile-Diagnosis-Expert-System
│
├── README.md
├── automobile_diagnosis.pl
├── report.pdf
└── documentation
     └── system_architecture.png
Description
File	Description
automobile_diagnosis.pl	Main Prolog knowledge base and inference rules
report.pdf	Academic report describing the expert system
README.md	Repository documentation
documentation/	Diagrams and architecture images
System Architecture

The expert system consists of the following components:

1 Knowledge Base

The knowledge base contains domain knowledge about automobile diagnostics, including:

symptoms

faults

system relationships

diagnostic rules

Example:

symptom(engine_wont_start).
fault(dead_battery).

These facts represent the core domain information used by the system.

2 Fault Classification

Each fault is mapped to a specific vehicle subsystem.

Example:

belongs_to(dead_battery, electrical_system).
belongs_to(clogged_fuel_filter, fuel_system).
belongs_to(bad_spark_plugs, ignition_system).

This allows the system to determine which vehicle subsystem is responsible for the issue.

Vehicle subsystems modeled in the system include:

Engine System

Fuel System

Ignition System

Electrical System

Cooling System

Exhaust System

Starting System

3 Symptom–Fault Relationship

Symptoms are connected to faults using the caused_by predicate.

Example:

caused_by(engine_wont_start, dead_battery).
caused_by(engine_wont_start, faulty_starter_motor).
caused_by(engine_wont_start, empty_fuel_tank).

This relationship allows the expert system to identify possible causes of a symptom.

4 Inference Engine

The system uses rule-based reasoning implemented in Prolog.

Core diagnostic rule:

diagnose(Symptom, Fault) :-
    symptom(Symptom),
    caused_by(Symptom, Fault).

This rule allows the system to infer possible faults based on a given symptom.

The inference engine uses Prolog's backward chaining mechanism to derive conclusions.

Diagnostic Capabilities

The system can diagnose a wide range of automobile problems including:

Engine Issues

engine overheating

engine knocking

engine misfires

loss of power

Fuel System Problems

clogged fuel filter

faulty fuel pump

dirty fuel injectors

Ignition Problems

bad spark plugs

faulty ignition coil

worn spark plug wires

Electrical Problems

dead battery

bad alternator

corroded battery terminals

Cooling System Issues

leaking coolant

faulty thermostat

clogged radiator

broken cooling fan

Exhaust Problems

bad oxygen sensor

faulty EGR valve

catalytic converter failure

System Rules

The expert system includes several rule categories.

Basic Diagnostic Rule
diagnose(Symptom, Fault)

Identifies faults based on symptoms.

System Detection Rule
system_fault(System, Fault)

Determines which subsystem contains a fault.

System-based Diagnostic Rule
has_fault_in_system(Symptom, System)

Identifies which system may contain the problem.

Specialized Diagnostic Rules

The system also includes advanced rules to detect specific categories of issues.

Examples include:

Battery related issues
related_to_battery(Symptom)
Spark / ignition related problems
related_to_spark(Symptom)
Fuel delivery problems
related_to_fuel_delivery(Symptom)
Overheating issues
overheating_issue(Symptom)
Smoke related engine issues
smoke_issue(Symptom)
Sensor related faults
sensor_fault(Symptom)

These rules provide more specialized diagnostic capabilities.

Example Queries

The system can be queried using Prolog commands.

Example 1 – Diagnose engine starting problem
?- diagnose(engine_wont_start, Fault).

Output:

Fault = dead_battery ;
Fault = faulty_starter_motor ;
Fault = empty_fuel_tank.
Example 2 – Identify system responsible for a fault
?- find_system(dead_battery, System).

Output:

System = electrical_system.
Example 3 – Detect cooling system problem
?- cooling_problem(engine_overheating).

Output:

true.
Example 4 – Detect sensor fault
?- sensor_fault(check_engine_light_on).

Output:

true.
Knowledge Representation

The expert system represents knowledge using predicate logic in Prolog.

The system includes:

20 symptoms

29 faults

7 vehicle subsystems

dozens of diagnostic rules

This structured representation allows the inference engine to perform logical reasoning similar to a human technician.

AI Concepts Demonstrated

This project demonstrates several Artificial Intelligence concepts, including:

Expert Systems

Knowledge Representation

Rule-Based Systems

Logical Reasoning

Inference Engines

Backward Chaining

Advantages of the System

Provides quick diagnostic suggestions

Demonstrates expert reasoning logic

Easy to extend with new rules

Helps understand AI knowledge-based systems

Limitations

The system depends on predefined rules

It cannot learn from new data automatically

Real-world diagnostics may require physical inspection

Future Improvements

The system can be extended by:

adding more vehicle symptoms and faults

integrating machine learning models

connecting with real vehicle diagnostic sensors

developing a graphical user interface

implementing probabilistic reasoning

Technologies Used
Technology	Purpose
Prolog	Knowledge representation and reasoning
Logic Programming	Rule-based inference
Expert System Architecture	AI diagnostic model
How to Run the System

Install SWI-Prolog

https://www.swi-prolog.org/

Clone the repository

git clone https://github.com/yourusername/Automobile-Diagnosis-Expert-System.git

Open Prolog

Load the file

?- consult('automobile_diagnosis.pl').

Run queries

Example:

?- diagnose(engine_overheating, Fault).
Educational Purpose

This project was developed as part of an Artificial Intelligence coursework assignment to demonstrate the design and implementation of an expert system using Prolog.

License

This project is released for educational and research purposes.
