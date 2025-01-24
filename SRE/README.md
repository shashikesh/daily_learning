## Adopting SRE practices

### The fundamental `SRE pillars` are:

    1. Embracing Risk  
    2. Service Level Objectives  
    3. Eliminating toil  
    4. Monitoring  
    5. Release Engineering  
    6. Automation  
    7. Simplicity  

### SRE principles vs DevOps principles
    SRE and DevOps both operate based on a set of principles. Both sets of principles drive alignment towards business goals. Some of their principles overlap. When comparing SRE vs DevOps, the biggest difference is that DevOps principles describe goals. SRE principles describe processes to achieve goals. In this sense, SRE best practices are a way for operations teams to implement DevOps principles.
    ‍
1. `embracing risk`  
    Embracing risk means weighing the costs of improving reliability and the impact it has on customer satisfaction.
    #### How to implement the principle of embracing risk
    -  Determine an acceptable level of reliability for customers. Look at use patterns and gather feedback to find these levels. This is building an SLI and SLO, which we’ll cover in the next section.
    - Determine the cost of any improvements to reliability. These improvements could include setting up redundant servers, automation efforts, or allocating engineers to reliability projects. Consider both the financial and opportunity cost.
    - Determine the risk of not implementing the improvement. Could the reliability of the service become unacceptable? How likely is it? If there is a setback, how much damage could it cause? 
    - Weigh the costs vs. the risk. Set standards for when your team embraces risk with error budgets. Make sure your team feels psychologically safe to fail and learn.

2. `service level objectives`  
    SLOs are based on Service level indicators, or SLIs. An SLI is a set of metrics that represent what’s most important to your customers. you can make SLIs that represent reliability more than any single metric.   

    SLOs can serve as a safety net to ensure that SLAs (service level agreements) aren’t breached.

    SLOs leave room for an error budget.  Whenever a failure or degradation affects the service, the error budget decreases. When the error budget is high, you can speed up development. When the error budget is on track to run out, you can hit the brakes or focus on reliability work.
3. `eliminating toil`  
    - Eliminating toil means reducing the amount of repetitive or manual work a team must do.
    - A common way of reducing toil is through automation
4.  `monitoring`  
    Monitoring means looking at the meaningful and actionable data your system produces, and making decisions based on it. 
    #### The most common metrics focused on for reliability are the four golden signals:

    - `Latency`: the time it takes for a service to respond to a request
    - `Traffic`: the amount of load a service is experiencing
    - `Error rate`: how often do requests to the service fail
    - `Saturation`: how much longer the service’s resources will last
5. `automation`
    - Automation means creating ways to complete repetitive tasks without human intervention
6. `release engineering`  
Release engineering means building and deploying software in a consistent, stable, repeatable way. It applies SRE principles to releasing software. 
7. `Simplicity`
    Simplicity means developing the least complex system that still performs as intended. The goals of simplicity and system reliability go hand-in-hand