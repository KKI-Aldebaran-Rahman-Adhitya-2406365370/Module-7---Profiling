# Pre-reflection Screenshots
## From "Commit 2"
![all-student-test_plan_1.png](all-student-test_plan_1.png)

![all-student-name-test_plan_2.png](all-student-name-test_plan_2.png)

![highest-gpa-test_plan_3.png](highest-gpa-test_plan_3.png)

## From "Commit 3"
![[POWERSHELL] all-student-test_plan_1.png](%5BPOWERSHELL%5D%20all-student-test_plan_1.png)

![[NOTEPAD] all-student-test_plan_1.png](%5BNOTEPAD%5D%20all-student-test_plan_1.png)

![[POWERSHELL] all-student-name-test_plan_2.png](%5BPOWERSHELL%5D%20all-student-name-test_plan_2.png)

![[NOTEPAD] all-student-name-test_plan_2.png](%5BNOTEPAD%5D%20all-student-name-test_plan_2.png)

![[POWERSHELL] highest-gpa-test_plan_3.png](%5BPOWERSHELL%5D%20highest-gpa-test_plan_3.png)

![[NOTEPAD] highest-gpa-test_plan_3.png](%5BNOTEPAD%5D%20highest-gpa-test_plan_3.png)

## After Optimization

![[POWERSHELL] all-student-test_plan_1_afterOptimization.png](%5BPOWERSHELL%5D%20all-student-test_plan_1_afterOptimization.png)

![[NOTEPAD] all-student-test_plan_1_afterOptimization.png](%5BNOTEPAD%5D%20all-student-test_plan_1_afterOptimization.png)

![[POWERSHELL] all-student-name-test_plan_2_afterOptimization.png](%5BPOWERSHELL%5D%20all-student-name-test_plan_2_afterOptimization.png)

![[NOTEPAD] all-student-name-test_plan_2_afterOptimization.png](%5BNOTEPAD%5D%20all-student-name-test_plan_2_afterOptimization.png)

![[POWERSHELL] highest-gpa-test_plan_3_afterOptimization.png](%5BPOWERSHELL%5D%20highest-gpa-test_plan_3_afterOptimization.png)

![[NOTEPAD] highest-gpa-test_plan_3_afterOptimization.png](%5BNOTEPAD%5D%20highest-gpa-test_plan_3_afterOptimization.png)

# Reflection

## 1. What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?
In the context of optimizing application performance, JMeter and IntelliJ Profiler approaches it in two different ways. JMeter acts as a tester that focuses on external metrics such as response time, throughput, and error rates. On the other hand, IntelliJ Profiler acts as a tester that looks inside the JVM to see which specific method is creating a bottleneck.
As a result, JMeter can be thought as an app that checks performance at a high-level, without focusing on the individual methods executed whereas IntelliJ Profiler can be thought as a feature that checks performance at a low-level by calculating the time allocated for each method.

## 2. How does the profiling process help you in identifying and understanding the weak points in your application?
Profiling helps me identify how my code can be improved from the perspective of performance. Even though my code may pass unit tests and functional tests, it may not perform fast enough. Tools such as flame graphs help me find methods that take the most CPU time. This helps me evaluate why a method or some methods need that much time and if it/they can be optimized.
The compare feature in IntelliJ Profiler also helps by letting me know how much better has a method performed after refactoring is done.

## 3. Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?
Yes, I think IntelliJ Profiler is effective in assisting me when I need to analyze and identify bottlenecks in my application. My main reason for this is due to the complexity of a codebase as it gets larger.
When a codebase grows bigger, it can be difficult to pinpoint where performance issues are simply by optimizing one part of the codebase. IntelliJ Profiler helps me by tracing what methods exactly are causing these performance issues. As a result, I can quickly find the bottlenecks and optimize the codebase as needed.

## 4. What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?
I think a challenge for me would be the verbosity of profiler reports. I understand that it is verbose because it needs to convey all useful information, but most of the time I only needed to check a certain part of the report to make an optimization. As a result, my best method for now is to know exactly what I am looking for when I want to improve the performance of my code.
This way, I do not get sidetracked by metrics that are not relevant to what I am trying to optimize for.

## 5. What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?
The main benefit that I gain from using IntelliJ Profiler is that its variety of features helps me pinpoint exactly what I should refactor. Features such as flame graph, call tree, and method list are all useful since it helps me specify which code is taking the most time.
Another benefit is that, after running IntelliJ Profiler, I get to see the number of milliseconds a line of code has after I stop the profiling process. This helps me a lot because I don't have to look at too many reports to know what exactly to optimize. The red labels on the number of milliseconds also help a lot because that tells me that this should be prioritized for optimization.

## 6. How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?
In situations where IntelliJ Profiler and JMeter differ, I usually suspect that there is or there are some external factors that are influencing the profiling process. Checking external factors such as network latency, database indexing, or connection pool limits can be sources where these two profiling tools differ.
Another possibility is to check if the JMeter load is too high for the current JVM heap size which may cause "stop-the-world" garbage collection where JMeter and IntelliJ Profiler may also differ. An easily overlooked possibility would be that the two profiling tools are testing two different environments which is a source of difference in results. 

## 7. What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?
Based on my experience in this module, my strategy was to optimize various database queries which is more efficient than processing large lists in Java's memory. Another solution I used was using optimized built-in functions such as String.join() to reduce memory allocation. To anticipate a situation where "optimized" methods do not work, I made a new branch called "optimize" to do all work related to optimization there and only merge to main when needed. 
Finally, I checked if the optimized methods gave the same output as the unoptimized methods. This ensures that performance improved without changing how the website looked.
