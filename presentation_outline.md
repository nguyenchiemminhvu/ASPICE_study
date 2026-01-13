# ASPICE 3.0: A Developer's Guide
## Presentation Outline (30 minutes)

---

## Overview

This presentation is designed for developers working in automotive software development. It explains ASPICE 3.0 from a practical, developer-focused perspective rather than an auditor's or manager's viewpoint.

**Presentation Flow:**
1. What ASPICE Really Is (and Isn't) - Slides 1-4
2. Understanding Process Assessment - Slide 5
3. The V-Model and Process Reference Model - Slides 6-8
4. System Engineering (SYS) Processes - Slides 9-13
5. Software Engineering (SWE) Processes - Slides 14-19
6. Process Assessment Model & Traceability - Slides 20-27
7. Wrap-up - Slides 28-29

**Total**: ~30 minutes, 29 slides

---

# SECTION 1: What ASPICE Really Is (and Isn't) - Slides 1-4

---

## Slide 1: Title Slide

**Slide Content:**
- ASPICE 3.0: A Developer's Guide
- Understanding What We Really Need to Do
- Nguyen Chiem Minh Vu
- nguyenchiemminhvu@gmail.com
- February 14, 2026

**Speaking Notes:**

Hey everyone! Today we're diving into ASPICE 3.0, but we're not looking at it from the management or auditor angle. We're approaching this from the developer's perspective - what does ASPICE actually mean for those of us writing code and building systems every day?

I know ASPICE can feel overwhelming at first. There's this mountain of documentation, countless process groups, and it feels like you need a PhD just to understand the terminology. But here's the thing - when you strip away the formal language and focus on what really matters to developers, it's actually pretty straightforward.

Today, I want to help you understand ASPICE in a way that makes sense for your daily work. We'll cover what it really is, why it exists, how the processes map to what you're already doing, and most importantly, how to work with it rather than against it. Let's get started.

---

## Slide 2: Agenda

**Slide Content:**
- 1. What ASPICE Really Is (and Isn't)
- 2. Understanding Process Assessment
- 3. The V-Model and Process Reference Model
- 4. System Engineering (SYS) Processes
- 5. Software Engineering (SWE) Processes
- 6. Process Assessment Model & Traceability

**Speaking Notes:**

Here's our roadmap for today. We'll start by clearing up common misunderstandings about ASPICE - what it is and what it definitely isn't. Then we'll look at where ASPICE comes from and why automotive needs it. After that, we'll explore the V-Model concept that's baked into ASPICE processes.

The bulk of our time will be spent walking through the actual processes - first the System Engineering processes, then Software Engineering. These are the bread and butter of what you'll work with as developers. Finally, we'll cover how your work gets assessed through capability levels, and we'll dig into traceability and consistency - two concepts that auditors always check.

Sound good? Let's dive in.

---

## Slide 3: Common Misunderstandings About ASPICE

**Slide Content:**
- ASPICE is NOT:
  - A coding standard (that's MISRA-C, AUTOSAR)
  - A document template or design method (No required UML or template)
  - A specific tool requirement (Tools are your choice)
  - A testing framework (It does not mandate unit test tools)
  - A quality guarantee by itself (Process does not equal zero defects)
  - A certification for bug-free software (It is a process assessment)
  - A one-time audit preparation activity (It is continuous, every sprint and release)

**Speaking Notes:**

Let's start by busting some myths about ASPICE. This is important because a lot of confusion comes from people thinking ASPICE is something it's not.

First off - ASPICE is NOT a coding standard. It doesn't care whether you use tabs or spaces, what naming conventions you follow, or which language features you use. That's what MISRA-C or AUTOSAR guidelines are for. ASPICE works at a higher level.

It's not a document template either. You won't find ASPICE saying "your requirements must be in this specific Word format" or "you must use UML for architecture." Use whatever format works for your team - Word docs, Markdown, wikis, whatever. ASPICE just cares that you HAVE the information and it's traceable.

ASPICE doesn't mandate specific tools. Want to use DOORS for requirements? Great. Prefer Jira? Fine. Even Excel can work if you maintain it properly. The tool doesn't matter - the content and traceability do.

It's not a testing framework. ASPICE won't tell you to use Google Test, Catch2, or any specific unit test framework. It just wants evidence that you're testing systematically.

Here's a crucial one - ASPICE Level 3 doesn't mean zero bugs. What it means is you have a controlled, repeatable process. You'll still have bugs, but you'll catch them more systematically and learn from them.

And finally - ASPICE isn't something you dust off when auditors are coming. If you only "do ASPICE" before audits, auditors will smell it a mile away. It should be how you naturally work, sprint after sprint, release after release.

So what IS ASPICE then? Let's find out.

---

## Slide 4: What ASPICE Really Is

**Slide Content:**
- ASPICE = Process assessment framework
- Judges HOW you build, not WHAT you build
- Key questions ASPICE asks:
  - Can your team build software predictably?
  - Do results happen consistently?
  - Can the process be repeated and improved?
  - Is success based on process, not heroics?
- ASPICE = PRM + PAM
  - PRM: What to do (processes)
  - PAM: How well you do it (capability levels)

**Speaking Notes:**

So here's what ASPICE actually is - it's a process assessment framework. Think about the difference here. When you test software, you're asking "does this product meet its requirements?" When you assess a process, you're asking "can this team reliably build good products?"

ASPICE doesn't judge your final software and say "this is good code" or "this is bad code." Instead, it looks at HOW you work and asks fundamental questions: Can your team build software predictably? If you start a new project tomorrow, will you get similar quality results? Do good outcomes happen consistently, or was your last success because someone pulled three all-nighters to save the project?

The key insight is this - ASPICE wants to see that your success comes from your process, not from heroic individual efforts. In a mature process, even when your star developer is on vacation, the team can still deliver quality work. That's what processcapability means.

Now, ASPICE has two main components, and you'll hear these acronyms a lot: PRM and PAM. The PRM - Process Reference Model - defines WHAT processes you should have. Things like requirements analysis, architectural design, testing, configuration management. The PAM - Process Assessment Model - defines HOW to measure whether you're doing those processes well. That's where the capability levels come from - Level 0 through 5.

Think of PRM as the "what" and PAM as the "how well." We'll explore both throughout this presentation.

---

# SECTION 2: Understanding Process Assessment - Slide 5

---

## Slide 5: Process Assessment and SPICE

**Slide Content:**
- SPICE = Software Process Improvement and Capability Determination
- Origin: ISO/IEC 15504 → ISO/IEC 330xx series
- Automotive SPICE (2005):
  - Specialized for automotive industry
  - Safety-critical software
  - Complex supply chains (OEM → Tier-1 → Tier-2)
- Assessment focuses on:
  - Process capability
  - Evidence of systematic approach
  - Predictability and repeatability

**Speaking Notes:**

Let's talk about where ASPICE comes from, because understanding the context helps explain why it's designed the way it is.

SPICE stands for Software Process Improvement and Capability Determination. Notice the keywords - "improvement" and "capability," not "compliance" or "certification." This originated from ISO standards for assessing software processes, and then the automotive industry said "we need our own flavor of this."

Why? Because automotive is special. We're not building web apps or mobile games. We're building safety-critical systems where bugs can literally kill people. Cars have a 15-20 year lifecycle, way longer than typical software products. And we have these incredibly complex supply chains - an OEM like Mercedes or BMW works with Tier-1 suppliers like Bosch or Continental, who work with Tier-2 and Tier-3 suppliers. Everyone needs to speak the same language about process quality.

That's why Automotive SPICE was created in 2005. It's tailored for our specific needs - functional safety, ASIL levels, long-term maintenance, multi-tier supply chains.

When auditors assess you, they're not just checking boxes - "do you have a requirements document?" They're looking for evidence of systematic approaches. They want to see that your process is repeatable and predictable. The evidence matters more than the format. You could have beautiful PowerPoint slides, but if you can't show that you actually follow the process consistently, that's a problem.

---

# SECTION 3: The V-Model and Process Reference Model - Slides 6-8

---

## Slide 6: The V-Model Mindset

**Slide Content:**
- From Waterfall to V-Model
- Left side: Development activities
  - Requirements → Design → Implementation
- Right side: Verification activities
  - Unit Test ← Integration Test ← System Test
- Key concept: Traceability
  - Each requirement → design → code → test

**Speaking Notes:**

Now let's talk about the V-Model, because this is absolutely central to understanding how ASPICE processes work.

The V-Model evolved from the old waterfall model. Remember waterfall? Requirements, then design, then implementation, then testing at the end. The problem was that by the time you got to testing, it was way too late and incredibly expensive to fix fundamental issues.

The V-Model fixes this by pairing every development step on the left side with a verification step on the right side. When you write system requirements, you're simultaneously planning system tests. When you design the architecture, you're planning integration tests. When you do detailed design, you're planning unit tests.

This changes everything. You're thinking about verification from day one, not as an afterthought. You're asking "how will I prove this works?" before you even start building it.

And here's the magic concept that ties it all together - traceability. Every requirement traces to a design element, which traces to code, which traces to a test. This isn't busywork. This gives you superpowers.

Someone asks "where is requirement REQ-456 implemented?" You follow the trace links. A test fails? Trace back to find the exact code and requirement involved. Requirements change? And they always do - traceability tells you exactly what downstream impacts you have to deal with. Which design elements are affected? Which code modules need updates? Which tests need to be modified?

Without traceability, you're flying blind. With it, you have x-ray vision into your project.

---

## Slide 7: ASPICE Process Reference Model

**Slide Content:**
- 3 Process Categories:
  - Primary Life Cycle (ACQ, SPL, SYS, SWE)
  - Organizational Life Cycle (MAN, PIM, REU)
  - Supporting Life Cycle (SUP)
- Heart of ASPICE: SYS + SWE groups
- Each process has:
  - ID and Name
  - Purpose
  - Activities (Base Practices - BP)
  - Outcomes (Work Products - WP)

**Speaking Notes:**

Let's look at how the Process Reference Model is structured. ASPICE organizes processes into three big categories.

Primary Life Cycle processes are the ones that directly create value - acquiring supplies, defining systems, developing software. Organizational processes are about running the company side of things - project management, process improvement, reuse management. Supporting processes help everything else happen - quality assurance, configuration management, problem resolution.

For us as developers, the heart of ASPICE is really the SYS and SWE process groups. That's where we'll spend most of our time today. And here's what's cool - the V-Model we just talked about? It's embedded right into these process groups. SYS and SWE processes implement the V-Model step by step. Left side development activities, right side verification activities.

Now, every single process in ASPICE follows the same template, which actually makes it easier to learn. Each process has an ID like SWE.1 or SYS.3, a descriptive name, a purpose statement explaining why this process exists, then Base Practices - the activities you should be doing - and finally Outcomes or Work Products - the artifacts you should produce as evidence.

When auditors come, they're checking two things: Are you doing the Base Practices? And do you have the Work Products to prove it? That's the assessment in a nutshell.

---

## Slide 8: What is a "System" in Automotive?

**Slide Content:**
- System ≠ just software
- System includes:
  - Software running on processors
  - Hardware (chips, boards, sensors)
  - ECUs (Electronic Control Units)
  - Mechanical parts (housing, connectors)
  - Communication networks (CAN, Ethernet, LIN)
  - Power supply and actuators
- SYS processes: System-level (HW + SW)
- SWE processes: Software-only

**Speaking Notes:**

Before we dive into the actual processes, we need to be crystal clear about terminology. When ASPICE talks about a "system," it does NOT mean just software. This is super important.

Let me give you an example. Imagine an ADAS camera system. The "system" includes the software that does image processing and object detection, sure. But it also includes the camera hardware itself, the image sensor, the ECU that runs the software, the physical housing and mounting bracket, all the wiring and connectors, the CAN or Ethernet interface for communication, the power supply circuitry, maybe some actuators for adjusting the camera angle.

ALL of that together is the "system." It's the complete product - hardware, software, electronics, mechanical, everything working together.

So SYS processes deal with requirements, design, and testing at this complete system level. You're thinking about the whole integrated product. SWE processes focus specifically on the software portion inside that system.

This is why SWE comes after SYS in the V-Model flow. First, you figure out what the complete system needs to do and how it's structured. Then you drill down into just the software requirements and software design. Make sense?

This distinction will be really clear as we go through the processes.

---

# SECTION 4: System Engineering (SYS) Processes - Slides 9-13

---

## Slide 9: SYS.1 - Requirements Elicitation

**Slide Content:**
- Purpose: Gather stakeholder needs and establish baseline
- Key activities:
  - Obtain requirements from stakeholders
  - Ensure mutual understanding
  - Get explicit agreement
  - Establish formal baseline
  - Manage changes with impact assessment
  - Set up status tracking mechanism
- Outcome: Agreed stakeholder requirements with change control

**Speaking Notes:**

Alright, let's start going down the left side of the V-Model with the System Engineering processes. First up is SYS.1 - Requirements Elicitation.

This is where everything begins. You're gathering what the stakeholders actually want. And by stakeholders, I mean everyone - customers, end users, product managers, safety engineers, regulatory compliance folks, anybody who has a say in what the system should do.

The key word here is "elicitation." You're not just collecting a shopping list of features. You're actively working to ensure everyone has mutual understanding. Because here's what happens in real projects - the customer says "real-time response" and they mean 5 milliseconds, but you heard "real-time" and thought 50 milliseconds was fine. Six months later, you've got a massive problem.

So you get explicit agreement. Not just "yeah, sounds good," but actual sign-off - "yes, this statement exactly captures what we want." Then you establish a formal baseline. This is your source of truth.

Now, requirements WILL change. That's not failure, that's reality. But you manage those changes. You don't just quietly update the document. You assess the impact, evaluate risks, and track what changed and why. You set up mechanisms so stakeholders can see the status of their requests.

This prevents those awkward conversations six months later where someone asks "what happened to that feature I requested?" and nobody remembers.

The outcome of SYS.1 is a clear, agreed-upon, baselined set of stakeholder requirements that everyone can reference throughout the project.

---

## Slide 10: SYS.2 - System Requirements Analysis

**Slide Content:**
- Purpose: Transform stakeholder needs into detailed system requirements
- Key activities:
  - Specify system requirements (functions and capabilities)
  - Structure and prioritize them
  - Analyze for correctness, feasibility, verifiability
  - Analyze impact on environment and interfaces
  - Develop verification criteria
  - Establish bidirectional traceability (stakeholder requirements)
  - Ensure consistency
- Outcome: Detailed, traceable, testable system requirements

**Speaking Notes:**

Next is SYS.2 - System Requirements Analysis. This is where you take those high-level stakeholder needs and transform them into detailed technical system requirements.

Here's an example. Stakeholder requirement says "the car should warn the driver when too close to another vehicle." Okay, but what does "too close" mean? 2 meters? 5 meters? Does it depend on speed? At what speed ranges does this apply? What kind of warning - audible beep, dashboard icon, haptic feedback in the steering wheel? How loud? At what frequency?

This is what you flesh out in SYS.2. You specify the functions and capabilities in engineering detail. You structure them - maybe by subsystem, maybe by safety level, maybe by release priority. You analyze them - is this requirement technically correct? Can we actually build this? Is it physically feasible? Most importantly -can we verify it with a test?

You also analyze environmental impacts - what interfaces are affected? What other systems need to interface with this? You develop verification criteria for EACH requirement. This is crucial - you're defining HOW you will test it before you even start building.

And here's where traceability becomes real. Every system requirement must trace back to a stakeholder requirement. This proves you're not just making stuff up. You also check consistency - make sure your detailed requirements don't contradict the higher-level stakeholder requirements.

The outcome is a complete set of clear, detailed, testable system requirements with full traceability back to stakeholder needs.

---

## Slide 11: SYS.3 - System Architectural Design

**Slide Content:**
- Purpose: Define system architecture and allocate requirements
- Key activities:
  - Develop system architectural design (HW + SW elements)
  - Allocate system requirements to elements
  - Define interfaces between elements
  - Evaluate dynamic behavior and interactions
  - Evaluate alternative architectures
  - Establish bidirectional traceability (system requirements)
  - Ensure consistency
- Outcome: System architecture with allocated requirements and defined interfaces

**Speaking Notes:**

SYS.3 - System Architectural Design. This is where you decide HOW to structure the system to meet all those requirements.

You're designing the overall architecture - breaking the system down into elements. These could be ECUs, sensors, actuators, software modules, communication buses, power supplies, whatever makes sense for your system.

Then you allocate requirements to these elements. So maybe "detect objects within 200 meters" gets allocated to the radar hardware element plus the signal processing software element. "Process data within 50ms" gets allocated to the main ECU and constrains the communication architecture.

You define all the interfaces between elements. What data flows between them? What protocols and message formats? What are the timing constraints? This is critical - most integration problems come from poorly defined interfaces.

You also evaluate dynamic behavior. How do these elements interact over time? What happens during system startup? During normal operation? During shutdown? What happens when faults occur?

You should evaluate alternative architectures too. Maybe you considered a centralized architecture versus distributed, and chose distributed for redundancy. Document that decision. Auditors want to see that you made conscious choices, not just picked the first idea that popped up.

Traceability and consistency check - every architectural element must trace to system requirements, and the architecture cannot contradict those requirements.

The outcome is a complete system architecture that both the hardware team and software team can use to implement their respective parts.

---

## Slide 12: SYS.4 - System Integration and Integration Test

**Slide Content:**
- Purpose: Integrate system items and verify architectural design
- Key activities:
  - Develop integration strategy (sequence of integration)
  - Develop integration test strategy (including regression)
  - Create test cases proving compliance with architecture
  - Integrate items step by step
  - Select and execute test cases
  - Establish bidirectional traceability: architecture ↔ test cases ↔ results
  - Ensure consistency
- Outcome: Integrated system verified against architectural design

**Speaking Notes:**

Now we're moving to the right side of the V-Model - verification. SYS.4 is System Integration and Integration Test.

This is where you bring all the system pieces together. But you don't just connect everything at once and hope for the best. You have an integration strategy - a planned sequence.

Maybe you start with the power supply and communication backbone, get those working first. Then add the main ECU. Then add sensors one by one. Then actuators. Step by step, incremental integration.

Why? Because if something breaks, you know exactly what you just changed. If you integrate everything at once and it doesn't work, good luck figuring out where the problem is.

You also have a test strategy. What are you testing at each integration step? What's your regression approach when something changes? The test cases here focus on verifying the architectural design - are the interfaces working correctly? Is data flowing as designed? Are timing constraints being met? Do elements interact the way the architecture specified?

You execute tests and record everything. Full traceability - from architecture elements to test cases to test results. This is critical because when an integration test fails - and they will - you can trace back to see exactly which architectural design element has the problem.

The outcome is a fully integrated system that you've proven works according to the architecture. Not just "we plugged everything in and it powered on," but "we have evidence that all the architectural design decisions are correctly implemented."

---

## Slide 13: SYS.5 - System Qualification Test

**Slide Content:**
- Purpose: Verify complete system against system requirements
- Key activities:
  - Develop qualification test strategy (including regression)
  - Create test cases proving compliance with system requirements
  - Select and execute test cases
  - Record test results and logs
  - Establish bidirectional traceability: requirements ↔ test cases ↔ results
  - Ensure consistency
- Outcome: System ready for delivery, verified against all requirements

**Speaking Notes:**

Finally, SYS.5 - System Qualification Test. This is the big one for system level.

You've integrated everything, now you test the COMPLETE system against the original system requirements to prove it does what the customer asked for.

What's the difference from SYS.4? SYS.4 verified the architecture - "did we build the system the way we designed it?" SYS.5 verifies the requirements - "does the system actually do what it's supposed to do?"

You develop test cases based on the verification criteria you defined way back in SYS.2. Remember when you wrote "shall detect obstacles within 200m with 95% accuracy"? Your test case better verify exactly that - 200 meters, 95% accuracy, with real measurements and statistics.

You select test cases based on strategy and release plan. Maybe you have thousands of potential tests, but you intelligently select which ones to run for this release based on risk, priority, and what changed.

Execute them, record absolutely everything - results, logs, timestamps, test environment configuration, equipment used, everything. If a customer asks two years from now "did you really test this?" you can pull up the complete record.

Traceability is absolutely critical here. Every system requirement must have at least one test case verifying it. Every test result must trace back to a requirement. If you have a requirement with no tests, that's a gap. If you have a test with no requirement, auditors will ask why you're testing things nobody asked for.

The outcome is a tested, qualified system that you can confidently deliver to customers, with full documentary evidence that it meets all requirements.

That wraps up the SYS process group - the complete left-to-right journey through the V-Model at system level.

---

# SECTION 5: Software Engineering (SWE) Processes - Slides 14-19

---

## Slide 14: SWE.1 - Software Requirements Analysis

**Slide Content:**
- Purpose: Transform system requirements into software requirements
- Key activities:
  - Specify software requirements from system requirements
  - Structure and prioritize them
  - Analyze for correctness, feasibility, verifiability
  - Analyze impact on operating environment
  - Develop verification criteria
  - Establish bidirectional traceability (system requirements and architecture)
  - Ensure consistency
- Outcome: Detailed, traceable, testable software requirements

**Speaking Notes:**

Now let's move into the Software Engineering processes. This is probably more familiar territory for most of us as developers.

SWE.1 is Software Requirements Analysis. This is where you take the software-related portions of the system requirements and break them down into detailed software requirements.

Remember, system requirements cover the complete product - hardware, software, mechanical, everything. SWE.1 focuses specifically on the software portion.

Here's an example. System requirement might say "the ECU shall process CAN messages within 10ms." That's system level. The software requirement gets more specific: "the CAN driver software module shall read messages from the receive buffer every 5ms" or "the message parser shall decode NMEA sentences according to protocol version 4.1 specification" or "the logging module shall buffer up to 1000 events before oldest events are discarded."

You structure these software requirements, analyze them for feasibility and testability. You check the impact on the operating environment - how does this affect RTOS scheduling? Memory usage? CPU load? Stack depth?

You define verification criteria for each requirement. And traceability - every software requirement must trace back to either a system requirement or a system architecture element. This proves you're implementing what was actually requested, not random features.

The outcome is a complete set of software requirements that developers can actually implement. These are concrete, testable specifications suitable for coding.

---

## Slide 15: SWE.2 - Software Architectural Design

**Slide Content:**
- Purpose: Define software architecture and allocate requirements
- Key activities:
  - Develop software architectural design (modules, components)
  - Allocate software requirements to elements
  - Define interfaces between software elements
  - Evaluate timing and dynamic interactions
  - Document resource consumption (memory, CPU)
  - Evaluate alternative architectures
  - Establish bidirectional traceability (software requirements)
  - Ensure consistency
- Outcome: Software architecture with allocated requirements and interfaces

**Speaking Notes:**

SWE.2 - Software Architectural Design. This is where you design the internal structure of your software.

You decide how to organize the software into modules, components, layers - whatever architectural style fits your project. Maybe layered architecture - HAL at the bottom, middleware, application on top. Maybe component-based with well-defined interfaces. Maybe event-driven. Whatever works for your specific needs.

You allocate software requirements to these architectural elements. "Parse GNSS data" goes to the GNSS parser component. "Log diagnostic events" goes to the logging module. "Manage power states" goes to the power management module.

You define ALL the interfaces between components. And I mean really define them - function signatures, data structures, error handling approach, callback mechanisms, everything. Most software integration bugs come from poorly defined interfaces.

You evaluate timing and dynamic behavior. When does each component run? In what order? What's the call flow during normal operation? During error conditions? This is especially critical in embedded real-time systems.

Document resource consumption. This module needs 50KB RAM. This function uses 10% CPU at 10Hz execution rate. This call stack can go 8 levels deep. In embedded systems with limited resources, this isn't optional.

Evaluate alternatives. Why this architecture and not others? Document your reasoning. This helps future maintainers understand the design rationale.

Traceability and consistency - every architectural element traces to software requirements, architecture doesn't contradict requirements.

The outcome is a software architecture document that your team can use to implement the actual code. This is the blueprint everyone follows.

---

## Slide 16: SWE.3 - Software Detailed Design and Unit Construction

**Slide Content:**
- Purpose: Design software units and implement them
- Key activities:
  - Develop detailed design for each component (functions, classes)
  - Specify interfaces of each unit
  - Evaluate dynamic behavior and unit interactions
  - Evaluate design quality (complexity, testability, risks)
  - Establish bidirectional traceability: requirements ↔ units
  - Ensure consistency
  - Develop and document executable code
- Outcome: Detailed design plus implemented and documented units

**Speaking Notes:**

SWE.3 - Software Detailed Design and Unit Construction. This is where we get down to the actual code level.

For each component in your software architecture, you create detailed design. This means defining specific functions, classes, data structures, algorithms. The low-level building blocks.

You specify interfaces precisely - function parameters with types, return values, error codes, preconditions, postconditions. How does this unit handle errors? What are its threading constraints?

Evaluate dynamic behavior at the unit level. How do these functions interact? What's the call sequence? What are the timing constraints? This helps catch design issues before you write code.

Evaluate design quality. Is this function getting too complex? Too many branches? Too many responsibilities? Is it even testable? What are the risks? This is where code review of designs - before implementation - can save massive amounts of rework.

Traceability is super important here. Every unit must trace back to software requirements and architectural design. This ensures you're implementing exactly what was designed, nothing more, nothing less.

Then you actually write the code - develop and document the executable units according to the detailed design. The outcome is both the design documentation AND the actual implemented code - your .c files, .cpp files, whatever - with full traceability linking them together.

This is where theory meets practice. You're creating the actual software that will run in the system.

---

## Slide 17: SWE.4 - Software Unit Verification

**Slide Content:**
- Purpose: Verify units against detailed design and requirements
- Key activities:
  - Develop unit verification strategy (testing and static analysis)
  - Define verification criteria (test cases, coverage, coding standards)
  - Perform static verification (code reviews, static analysis)
  - Execute unit tests and record results
  - Establish bidirectional traceability: units ↔ design ↔ test cases ↔ results
  - Ensure consistency
- Outcome: Verified units with evidence of compliance

**Speaking Notes:**

SWE.4 - Software Unit Verification. This is basically unit testing, but ASPICE-style with proper documentation and traceability.

You develop a verification strategy that includes both dynamic testing - actually running the code - and static verification - code reviews, static analysis tools, checking against coding standards like MISRA-C.

You define criteria for each unit. What test cases do we need? What coverage goals - statement coverage, branch coverage, MC/DC for safety-critical code? What coding standard rules must we follow? What static analysis checks?

Then you perform the verification. Static verification catches issues like uninitialized variables, potential buffer overflows, MISRA rule violations, excessive complexity. This happens without running the code.

Dynamic testing actually executes your unit tests. Does the function behave correctly with valid inputs? With boundary conditions? With invalid inputs? Are error paths properly tested?

Record all results - test logs, coverage reports, static analysis reports. Everything. Traceability connects units to design to test cases to verification results. This proves you actually tested what you designed.

If you have 100 units but only 80 have tests, auditors will definitely ask about those 20. Every unit needs verification evidence.

The outcome is verified units with solid evidence that they comply with the detailed design and with non-functional requirements like performance, safety constraints, and reliability targets.

---

## Slide 18: SWE.5 - Software Integration and Integration Test

**Slide Content:**
- Purpose: Integrate units into complete software and verify architecture
- Key activities:
  - Develop integration strategy (sequence of integration)
  - Develop integration test strategy (including regression)
  - Create test cases proving compliance with software architecture
  - Integrate units step by step
  - Select and execute test cases
  - Establish bidirectional traceability: architecture ↔ test cases ↔ results
  - Ensure consistency
- Outcome: Integrated software verified against architectural design

**Speaking Notes:**

SWE.5 - Software Integration and Integration Test. Time to put all those units together to build the complete software.

Just like SYS.4, you don't integrate everything at once. You have a strategy. Maybe you start with low-level drivers, then add middleware, then application layer. Or maybe you integrate feature by feature. Whatever makes sense for your project.

You also have a test strategy including regression. When you integrate a new unit, you need to re-run some tests to ensure you didn't break existing functionality. Regression testing is critical - it catches those sneaky side effects where adding Feature B mysteriously breaks Feature A.

The test cases verify the software architecture. Are interfaces between units working correctly? Is data flowing as designed? Are function calls happening in the right sequence? Are timing constraints being met? Is error handling working across module boundaries?

Execute tests, record results. Full traceability - architecture elements to test cases to test results. When an integration test fails, you can trace back to find exactly which interface or interaction has the problem.

The outcome is fully integrated software - all your units compiled and linked together into a complete binary - that you've proven works according to the software architecture. This is your deliverable software, ready for the next level of testing.

---

## Slide 19: SWE.6 - Software Qualification Test

**Slide Content:**
- Purpose: Verify complete software against software requirements
- Key activities:
  - Develop qualification test strategy (including regression)
  - Create test cases proving compliance with software requirements
  - Select and execute test cases
  - Record test results and logs
  - Establish bidirectional traceability: requirements ↔ test cases ↔ results
  - Ensure consistency
- Outcome: Software ready for system integration, verified against all requirements

**Speaking Notes:**

Finally, SWE.6 - Software Qualification Test. This verifies the complete integrated software against all the software requirements you defined back in SWE.1.

Same concept as SYS.5 but at software level. The key difference - SWE.5 verified the architecture ("did we build the software correctly according to our design?"), while SWE.6 verifies the requirements ("does the software actually do what it's supposed to do?").

You create test cases based on verification criteria from SWE.1. If the requirement said "shall parse NMEA sentences with 99.9% success rate," your test case needs to verify that specific metric with real data and statistics.

Select test cases based on your strategy and release plan. Execute them. Record everything - results, logs, environment, everything.

Traceability is absolutely critical here. Every software requirement must have at least one test case verifying it. Every test result must trace back to a requirement. Auditors will check this very carefully.

The outcome is fully tested software that you can confidently hand over for system integration in SYS.4, with complete documentation evidence that it meets all software requirements.

That completes the SWE process group. Notice the parallel structure with SYS? That's the V-Model in action - the same pattern at different levels of abstraction.

---

# SECTION 6: Process Assessment Model & Traceability - Slides 20-27

---

## Slide 20: The Process Assessment Model (PAM)

**Slide Content:**
- PAM = How we measure process capability
- 6 Capability Levels (0 to 5):
  - Level 0: Incomplete (not implemented or fails)
  - Level 1: Performed (achieves its purpose)
  - Level 2: Managed (planned, monitored, controlled)
  - Level 3: Established (follows defined standard process)
  - Level 4: Predictable (quantitatively controlled)
  - Level 5: Innovating (continuously improved)
- Each level has Process Attributes (PA)
- Automotive projects typically target Level 2 or 3

**Speaking Notes:**

We've covered the PRM - the Process Reference Model - which defines WHAT processes you need. We went through all the SYS and SWE processes in detail. Now let's talk about the PAM - the Process Assessment Model - which measures HOW WELL you're doing those processes.

PAM is based on ISO/IEC 33020 and defines 6 capability levels from 0 to 5.

Level 0 - Incomplete. You're not doing the process at all, or it's failing to achieve its purpose. Basically dysfunctional.

Level 1 - Performed. You're doing the process and achieving its purpose, but maybe in an unplanned, chaotic way. It works when the right people are around, but it's not systematic.

Level 2 - Managed. You're doing it in a managed way - you plan the process, monitor it, adjust it when needed, and you properly manage and control your work products. This is where most automotive suppliers need to be.

Level 3 - Established. You have a standard defined process at organizational level that projects tailor and deploy consistently. This is what OEMs and Tier-1 suppliers typically require.

Level 4 - Predictable. You're operating within defined limits using quantitative measures to control the process. This is pretty rare - mostly safety-critical systems.

Level 5 - Innovating. You're continuously improving the process to meet changing business goals. Very few companies actually achieve this.

In automotive, most projects target Level 2 or 3. Level 2 is usually sufficient for Tier-2 suppliers. Level 3 is common for Tier-1 and OEM internal projects.

Each level has Process Attributes that define what you need to demonstrate. Let's look at those.

---

## Slide 21: Capability Levels (0 to 5)

**Slide Content:**
- Level 0: Incomplete process - Not implemented or fails; little or no systematic achievement
- Level 1: Performed process - Process achieves its purpose
- Level 2: Managed process - Planned, monitored, and adjusted; work products controlled
- Level 3: Established process - Defined process in use; capable of achieving outcomes
- Level 4: Predictable process - Operates within defined limits; measured and quantitatively controlled
- Level 5: Innovating process - Continuously improved to meet organizational change

**Speaking Notes:**

Let me break down what each capability level really means in practice.

Level 0 - Incomplete. You're either not doing the process, or you're attempting it but failing to achieve the outcomes. There's little or no evidence of systematic achievement. This is obviously not where you want to be.

Level 1 - Performed. The process achieves its purpose. You're getting the work done, but it might be ad hoc, unplanned, relying heavily on individual heroics. Results happen, but they're not necessarily repeatable or predictable.

Level 2 - Managed. Now you're planning the process before executing it. You're monitoring progress, adjusting when things go off track. Your work products - requirements, designs, code, tests - are properly managed, controlled, and maintained. This is a huge leap forward in maturity.

Level 3 - Established. You have a standard, defined process at organizational level. Individual projects tailor this standard process for their specific needs, but everyone's following the same basic framework. The process is well-documented and capable of consistently achieving outcomes.

Level 4 - Predictable. You're using quantitative measures to understand and control the process. You know your performance limits and operate within them. You have metrics showing your process is stable and predictable. This requires serious process maturity.

Level 5 - Innovating. You're continuously improving the process based on quantitative understanding to meet changing business needs. You're not just following the process, you're actively evolving it.

Again, most automotive work targets Level 2 or 3. That's where the practical value is for most organizations.

---

## Slide 22: Capability Levels and Process Attributes

**Slide Content:**
- Level 1: PA 1.1 (Process performance)
- Level 2: PA 2.1 (Performance management), PA 2.2 (Work product management)
- Level 3: PA 3.1 (Process definition), PA 3.2 (Process deployment)
- Level 4: PA 4.1 (Quantitative analysis), PA 4.2 (Quantitative control)
- Level 5: PA 5.1 (Process innovation), PA 5.2 (Process innovation implementation)

**Speaking Notes:**

Now let's look at the Process Attributes that define each level. These are what auditors actually assess.

Level 1 has one attribute - PA 1.1 Process Performance. Are you doing the process and achieving its intended outcomes? Pretty straightforward.

Level 2 has two attributes. PA 2.1 Performance Management means you plan the process, monitor it, take corrective action when needed. PA 2.2 Work Product Management means you properly identify, document, control, and maintain all the artifacts you produce - requirements docs, designs, code, test results, everything.

Level 3 also has two attributes. PA 3.1 Process Definition means you have a standard process defined at organizational level. PA 3.2 Process Deployment means you actually deploy that standard process consistently across projects, with appropriate tailoring.

Level 4 - PA 4.1 Quantitative Analysis means you collect and analyze quantitative data about the process. PA 4.2 Quantitative Control means you use that data to actually control and predict process performance.

Level 5 - PA 5.1 Process Innovation means you identify improvement opportunities based on quantitative understanding. PA 5.2 means you implement those innovations effectively.

For most of us working at Level 2 or 3, focus on those first six attributes. That's what your audits will primarily assess.

---

## Slide 23: Rating Scale and Achievement Range

**Slide Content:**
- Rating scale:
  - N - Not achieved: 0-15%
  - P- Partially achieved (-): >15% to ≤32.5%
  - P+ Partially achieved (+): >32.5% to ≤50%
  - L- Largely achieved (-): >50% to ≤67.5%
  - L+ Largely achieved (+): >67.5% to ≤85%
  - F - Fully achieved: >85% to 100%

**Speaking Notes:**

So how do auditors rate these Process Attributes? They use this achievement scale.

N - Not achieved. You're doing less than 15% of what you should. Essentially no evidence of systematic approach.

P - Partially achieved. You're doing between 15% and 50%. There's some evidence of an approach, but it's inconsistent and unpredictable. Lots of weaknesses.

L - Largely achieved. You're doing between 50% and 85%. There's evidence of a systematic approach with significant achievement, but some weaknesses remain.

F - Fully achieved. You're doing more than 85%. It's complete, systematic, with no significant weaknesses.

Here's the critical part for achieving capability levels - to claim a level, all the Process Attributes for that level must be at least Largely achieved. And all attributes from lower levels must be Fully achieved.

So to achieve Level 2, PA 1.1 must be F (Fully), and PA 2.1 and PA 2.2 must each be at least L (Largely). To achieve Level 3, PA 1.1, 2.1, and 2.2 must all be F, and PA 3.1 and 3.2 must be at least L.

This prevents checkbox compliance. You can't just barely do something and claim the level. You need solid, systematic evidence.

---

## Slide 24: Process Capability Level Model

**Slide Content:**
- To achieve Level 1: PA 1.1 must be L or F
- To achieve Level 2: PA 1.1 must be F; PA 2.1 and 2.2 must be L or F
- To achieve Level 3: PA 1.1-2.2 must be F; PA 3.1 and 3.2 must be L or F
- To achieve Level 4: PA 1.1-3.2 must be F; PA 4.1 and 4.2 must be L or F
- To achieve Level 5: PA 1.1-4.2 must be F; PA 5.1 and 5.2 must be L or F
- Note: Higher levels require all lower-level PAs to be Fully achieved

**Speaking Notes:**

Let me make this concrete with the rules for claiming each capability level.

To claim Level 1, Process Attribute 1.1 must be rated at least Largely achieved. That's it.

To claim Level 2, PA 1.1 must be Fully achieved, and PA 2.1 and 2.2 must each be at least Largely achieved.

To claim Level 3, PA 1.1 through 2.2 must all be Fully achieved, and PA 3.1 and 3.2 must each be at least Largely achieved.

See the pattern? You can't skip levels. You can't have great work product management (Level 2) if you're not even performing the process properly (Level 1).

This creates a solid foundation. Each level builds on the previous one. You can't claim Level 3 with a shaky Level 2 foundation.

In practice, this means you need to focus on getting the basics right first. Master Level 1 - actually perform the processes and achieve their purpose. Then add management (Level 2). Then standardize across the organization (Level 3).

Trying to jump straight to Level 3 without solid Level 2 practices is a recipe for failure in an audit.

---

## Slide 25: Traceability - What and Why

**Slide Content:**
- Traceability = links between work products
- Bidirectional traceability:
  - Downstream (forward): Requirements → Design → Code → Tests
  - Upstream (backward): Tests → Code → Design → Requirements
- Why it matters:
  - Completeness: everything is implemented and tested
  - Necessity: no undefined extra code
  - Impact analysis: know what to fix when requirements change
  - Answers: "Where is this implemented? Which test verifies it?"

**Speaking Notes:**

Let's talk about traceability, because this is one of the most important concepts in ASPICE and something auditors always check carefully.

Traceability means you have links between your work products. It's the chain connecting everything together from requirements through to test results.

Bidirectional means you can trace both directions. Downstream - going forward - means starting from a requirement and following it to the design that implements it, to the code that realizes it, to the test that verifies it. This ensures completeness - every requirement gets implemented and tested.

Upstream - going backward - means starting from a test result and tracing back to find which code it tested, which design element that code implements, and which requirement that design satisfies. This ensures necessity - everything you built was actually required, no random features.

Here's where traceability becomes incredibly practical. Requirements change - and they ALWAYS change. With traceability, you know exactly what the impact is. Requirement REQ-789 changed? Follow the links to see which design elements are affected, which code modules need updates, which tests need modification.

Without traceability, you're guessing. You might miss something. Or you might update stuff that didn't need updating. With traceability, you have a clear roadmap of all dependencies.

Traceability answers critical questions: Where is this requirement implemented? Which tests verify this feature? If this test fails, which requirement is affected? These aren't academic questions - these come up constantly in real projects.

---

## Slide 26: Consistency - More Than Just Links

**Slide Content:**
- Consistency = content and meaning match
- Traceability ≠ Consistency
  - Traceability: "A is linked to B"
  - Consistency: "A and B actually say the same thing"
- Example:
  - Requirement: "Alert on GNSS fix loss"
  - Design: "Display alert when fix lost" (consistent)
  - Design: "Alert when TTF > expected" (inconsistent!)
- Every process checks both:
  - "Establish bidirectional traceability"
  - "Ensure consistency"

**Speaking Notes:**

Now let's talk about consistency, because people often confuse it with traceability. They're related but distinctly different.

Traceability is about having the links - "this requirement is implemented by this design element." That's the connection.

Consistency is about the content - "does this design element actually match what the requirement says?" That's the semantic alignment.

Let me give you a concrete example. Say you have a requirement: "the system shall display an alert when GNSS position fix is lost." You create a trace link from this requirement to a design element. Great, you have traceability.

But what does that design element actually say? If it says "display alert when GNSS fix is lost" - perfect, that's consistent. The meaning matches.

But if it says "display alert when Time-To-First-Fix exceeds expected duration" - wait, that's different! fixlost and long time-to-fix are not the same thing. You have the link (traceability), but you don't have semantic alignment (consistency).

ASPICE wants both. That's why in every process, you see two separate Base Practices - one says "establish bidirectional traceability," another says "ensure consistency."

Traceability is relatively mechanical - you create the links in your tool. Consistency requires actual thinking and review - you need to read both work products and verify they match semantically.

This is where many teams fail audits. They have beautiful traceability matrices with all the links, but the content doesn't actually align. Auditors will spot this immediately.

---

## Slide 27: Practical Example - Traceability Matrix

**Slide Content:**
- Example: GNSS software module
- Traceability Matrix showing many-to-many relationships
- SWR-001 (pos @1Hz) verified by TC-010 and TC-013
- SWR-002 (UTC ≤1s) verified by TC-010 and TC-011
- SWR-003 (NO_FIX) verified by TC-012
- Key points:
  - One test can verify multiple requirements
  - One requirement can have multiple tests
  - Every requirement must have at least one test

**Speaking Notes:**

Let me show you a practical example of a traceability matrix, because this is a common way to manage and visualize traceability.

Imagine we're working on a GNSS software module. We have requirements like SWR-001 says "position data shall be output at 1Hz," SWR-002 says "UTC time accuracy shall be within 1 second," SWR-003 says "system shall report NO_FIX status when position fix is lost."

We have test cases: TC-010 tests nominal NMEA parsing, TC-011 tests UTC time accuracy specifically, TC-012 tests the fix-loss scenario, TC-013 tests output rate stability.

Look at the relationships. TC-010 verifies both SWR-001 and SWR-002 because it tests both position output and time accuracy in the nominalcase. That's fine - one test can verify multiple requirements.

SWR-001 is verified by both TC-010 and TC-013 because you need to test output rate in different scenarios - nominal and under various conditions. That's also fine - one requirement can have multiple tests.

This many-to-many relationship is totally acceptable in ASPICE. You don't need strict one-to-one mapping. What matters is:

Every requirement has AT LEAST one test verifying it. If you have a requirement with zero tests, that's a gap - you have unverified functionality.

Every test traces back to AT LEAST one requirement. If you have a test with zero requirements, auditors will ask why you're testing things nobody asked for.

This simple matrix makes gaps instantly visible. Missing links stand out. Auditors love these because they can quickly verify completeness.

---

# SECTION 7: Wrap-up - Slides 28-29

---

## Slide 28: Key Takeaways for Developers

**Slide Content:**
- ASPICE is about how we work, not what tools we use
- V-model ensures early test planning and traceability
- SYS processes: complete system (HW + SW)
- SWE processes: software only
- Left side of V: development (requirements → design → code)
- Right side of V: verification (tests proving compliance)
- Traceability: links between work products
- Consistency: content actually matches
- Process capability: levels show process maturity
- Most important: do it continuously, not just before audits

**Speaking Notes:**

Alright, let's wrap up with key takeaways you should remember as developers.

First - ASPICE doesn't dictate your tools or document formats. It cares about HOW you work. Do you have a systematic, repeatable process? That's what matters.

The V-Model is central to everything. It forces early test planning and gives you traceability from requirements through verification. Thisis incredibly powerful for managing change and understanding impacts.

Remember the distinction - SYS processes cover the complete system including hardware, SWE processes focus specifically on software. Different levels of abstraction, same V-Model pattern.

Left side of the V is development - gathering requirements, analyzing them, designing solutions, implementing code. Right side is verification - testing to prove everything works as specified. They mirror each other.

Traceability gives you links between all work products. It's not busywork - it's your map through the project. Consistency ensures those links actually make semantic sense, not just exist formally.

Process capability levels tell you how mature your process is. Level 1 - just getting things done. Level 2 - doing it in a managed way. Level 3 - following a defined standard. Most automotive work happens at Level 2 or 3.

Here's maybe the most important takeaway - ASPICE is NOT something you do once before audits and then forget. If you only "do ASPICE" when auditors are coming, you're doing it wrong and they'll know immediately. It should be your natural way of working, integrated into every sprint, every release, every day.

When ASPICE is done right, it doesn't slow you down. It actually makes you faster and more efficient because you catch problems early, you know exactly what needs updating when requirements change, and you don't waste time building things nobody asked for.

---

## Slide 29: Q&A / Discussion

**Slide Content:**
- Questions?
- Common questions:
  - How does Agile/Scrum fit with ASPICE?
  - What is the difference between system and software requirements?
  - How do we handle traceability in practice?
  - What tools should we use?
  - How do we prepare for assessments?

**Speaking Notes:**

That wraps up the main content. We've covered a lot of ground in 30 minutes - what ASPICE is versus common misconceptions, the V-Model and how it's embedded in the process structure, a complete walkthrough of SYS and SWE processes following the V from requirements to testing, process capability levels and how they're assessed, and the critical concepts of traceability and consistency.

The big picture to remember - ASPICE is fundamentally about reducing uncertainty. It doesn't guarantee zero bugs, but it shows customers that you have a mature, transparent, repeatable way of working. When a team truly follows ASPICE, it means you're building systems systematically, not randomly.

Now, anyone have questions? I've listed some common ones here.

People always ask about Agile and ASPICE - yes, they work together perfectly. ASPICE is the "what" - what processes and artifacts you need. Agile is the "how" - how you organize work into sprints. You can have two-week sprints and still maintain requirements traceability and architectural design.

System versus software requirements - system is the complete product including hardware, software is just the code portion. The system requirements come first and drive the software requirements.

Traceability in practice - most teams use requirements management tools like DOORS, Polarion, Jira with plugins, or even well-maintained spreadsheets. The tool matters less than the discipline.

What tools to use - ASPICE doesn't care. Use what works for your team as long as you can demonstrate the required work products and maintain traceability.

Assessment preparation - honestly, if you're following ASPICE processes every day like you should, there's not much special preparation needed. Just gather your evidence, ensure traceability is up to date, maybe do an internal audit to find any gaps. The work should already be done.

Any other questions before conclude?

Thank you all for your attention! Remember, ASPICE is here to help us build better systems more reliably. Work with it, not against it, and it becomes a valuable tool rather than a burden.

---

## End of Presentation

**Additional Resources:**
- ASPICE 3.0 Process Reference Model (PRM)
- ASPICE 3.0 Process Assessment Model (PAM)
- ISO/IEC 33020 (Process measurement framework)
- Your organization's ASPICE guidelines and templates

**Contact:**
- Nguyen Chiem Minh Vu
- nguyenchiemminhvu@gmail.com
