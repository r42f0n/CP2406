java c
CP2406 Assessment 3 (20%)
Benchmark an N-Body Gravity Simulation in C++
Helping astrophysicists understand the universe!Overview:
Imagine you are a software developer working with a university astrophysicist. They need your help finalising an N-body simulation   that models gravitational interactions within a 2D space using the Barnes-Hut algorithm. The algorithm structures data efficiently to approximate gravitational forces between bodies, reducing the need for exhaustive pairwise calculations. They don’t want you to reimplement Barnes-Hut from scratch. Read on to find out what they want you to do!The Barnes-Hut algorithm   reduces the computational cost of gravitational force calculations by structuring data hierarchically, allowing groups of bodies to be represented as single entities for distant interactions. The existing codebase contains two “single interaction”   functions:1.   Central Body Interaction – singleInteract() in BhTree.cpp
o   Calculates gravitational interactions between a target body (e.g., a "sun") and an approximation of several other bodies or just a single other body.
o   The BhTree (Barnes-Hut Tree) is a data structure used to partition space hierarchically, allowing for efficient approximation of gravitational interactions in N-body simulations by treating clusters of distant bodies as single mass points.2.   General Body Interaction   – singleInteraction() in BarnzNhutt.cpp
o   Handles pairwise gravitational interactions between all bodies.Getting Started:You can use any C++ IDE, such as CLion, VS Code, or Visual Studio,   to work on this assessment task. We provide the existing codebase containing empty versions of each single iteration function. We suggest that you do the following:
1.   Familiarise yourself with the codebase. Review the existing code and Constants.h   file to understand the constants and values provided for simulation parameters.
2.   Try building and running BarnzNhutt.cpp; this is the simulation itself! It generates a series of images of the simulation into a subdirectory called “images”. Use ffmpeg to convert these images into a single mp4 file. You’ll need to install ffmpeg   on your computer. To generate the mp4, type this in a terminal window: ffmpeg -framerate 45 -i images/Step%05d.ppm result.mp4   
Your Tasks:1.   Complete each of the “single interaction” functions:
o   Finalise the code in BarnzNhutt.cpp   and BhTree.cpp   to ensure that each interaction function accurately computes body accelerations as necessary. See the pseudo-code below!2.   Benchmark Performance:
o   Adjust the provided files to benchmark your singleInteraction()   in BarnzNhutt.cpp function as follows:
§   Execution Time (in calculate_duration.cpp): Measure the time taken for a single call with a fixed number of bodies.
§   Memory Usage (in calculate_memory.cpp): Measure memory consumption during the function’s execution.
3.   Complexity Analysis:
o   Determine the Big-O complexity of interactBodies() in BarnzNhutt.cpp.
o   Discuss this in your 2-minute code review (see below).
Submission Guidelines:
Submit a zipped folder named CP2406-A3-FirstName-LastName   containing your project work, including:
·   The existing codebase with your two single interaction   functions.
·   The code for benchmarking your singleInteraction() function regarding execution time and memory usage.
·   A 2-minute screencast explaining:
代 写CP2406 Assessment 3C/C++
代做程序编程语言o   Show how you set up and ran the simulation yourself.
o   Show the benchmarking working for execution time and memory usage.
o   Explain what you think is the Big-O of interactBodies() in BarnzNhutt.cpp is and why.
o   Express any thoughts you have about improving this codebase.
Pseudo code for singleInteract() in BhTree.cpp:
FUNCTION singleInteract (target, other)
            Step 1. posDiff = (target - other) * TO_METERS
            Step 2. distance = magnitude of posDiff
            Step 3. IF distance == 0 THEN RETURN
            Step 4. force = TIME_STEP * (G * target.mass * other.mass) / ((distance^2 + SOFTENING^2) * distance)
            Step 5. target.accel -= force * posDiff / target.mass
Pseudo code for singleInteraction() in BarnzNhutt.cpp:
FUNCTION singleInteraction(body_a, body_b)
            Step 1. posDiff = (body_a - body_b) * TO_METERS
            Step 2. distance = magnitude of posDiff
            Step 3. force = TIME_STEP * (G * target.mass * other.mass) / ((distance^2 + SOFTENING^2) * distance)
            Step 4. target.accel -= force * posDiff / target.mass
            Step 5. other.accel += force * posDiff / other.mass
Notes:
·   In this pseudo code, the symbol ^ refers to the pow(x, y) function in C++.
·   Constants like TIME_STEP, SOFTENING, and FRICTION_FACTOR are defined in Constants.h.
·   Familiarise yourself with the body   struct   to understand how to implement the pseudo-code.
Marking scheme:
Task 1: 10 marks·   Complete the two single interaction functions so that the simulation runs successfully.
Task 2: 5 marks·   Benchmark the performance of your singleInteraction() function in terms of execution time and memory usage.
Task 3: 5 marks·   Effectively discuss your work in the code review.   ExemplaryGoodSatisfactoryLimitedVery Limited   100%75%50%25%5%
Task 1Code runs successfully without errors. Follows C++ guidelines for names and indentation and error handling. Includes clear comments for usage and parameters.    
Exhibits aspects of exemplary (left) and satisfactory (right)
Code runs successfully with some errors. Follows C++ some guidelines for names and indentation and error handling. Includes some comments for usage and parameters.
Exhibits aspects of satisfactory (left) and very limited (right)Code does not run or is completely incorrect. Code is difficult to read and does not follow guidelines. No comments provided. 
   
Task 2Execution time and memory usage of the function is accurately recorded. Includes clear comments for implementation. 
Exhibits aspects of exemplary (left) and satisfactory (right)
Execution time or memory usage of the function is missing. Includes some comments for implementation.
Exhibits aspects of satisfactory (left) and very limited (right)
Execution time and memory usage of the function is missing. Comments are not included. 
Task 3Clearly demonstrate the running of your code in a two minute screen recording. Provide the Big-O notation is correctly explained.    
Exhibits aspects of exemplary (left) and satisfactory (right)Demonstrate the running of your code, but some details are missing. Big-O notation is partially correct.
Exhibits aspects of satisfactory (left) and very limited (right)Screen recording is missing or difficult to understand. Big-O notation is not provided.
   

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
