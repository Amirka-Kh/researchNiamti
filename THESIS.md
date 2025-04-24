# Amazing Relation of Developer and Project Estimations

## Abstract

Accurate project estimation and developer contribution analysis are critical to the success of software development projects. This research explores the challenges of linking developer productivity metrics to project estimation, with the goal of improving project planning and team efficiency. By analyzing a wide range of productivity and estimation models, the study identifies metrics most closely linked to project outcomes. A prototype tool was tested in a real-world setting, highlighting potential insights into productivity trends and estimation accuracy. Preliminary findings demonstrate the potential of combining data-driven metrics with qualitative insights, providing a foundation for future research and tool development.

Our tool was tested in a real-world setting by a software development company. The results were encouraging: the tool identified a developer who claimed to be overworked but whose contributions were average compared to the rest of the team. The situation led to the developer's voluntary departure, which, according to the company, had a positive impact on team morale and overall productivity. These findings demonstrate the potential of our tool to improve both project estimation and team dynamics, ultimately contributing to more efficient project management.It should be noted that we do not claim that our tool is a silver bullet for assessing the feasibility of any project. We are only saying that we have had a successful experience in test trials, which gives room for further research. In our case, the tool has been successful, but a full-fledged study is necessary for consistent conclusions.

## Introduction

In the fast-paced world of software development, accurately estimating project parameters and evaluating developer contributions is crucial to a project’s success. Estimation goes beyond financial forecasting—it shapes team dynamics and morale. Realistic deadlines and budgets enhance productivity while reducing stress, ensuring developers stay aligned with project goals [1]. When contributions are properly recognized and rewarded, motivation increases, leading to greater engagement. The relationship between work satisfaction and productivity is well-documented: when individuals feel valued and supported in their work environment, they are more likely to improve their skills and contribute meaningfully, reinforcing a cycle of motivation and efficiency [2].

Given the importance of accurate estimation, it is essential to examine how estimation methodologies have evolved over time. Traditionally, project estimation relied on basic metrics such as lines of code (LOC), budget allocation, and deadline setting [3]. While these methods provided a foundation, they often failed to reflect the complexities of modern software development. For instance, a developer who refactors existing code may contribute fewer lines than one writing new features, yet their impact on maintainability and performance can be substantial. Activity-based metrics capture these contributions more effectively. Historically, developer productivity was measured by lines of code, hours worked, and bugs resolved, overlooking qualitative factors like innovation, collaboration, and code quality [2, 3, 5].

As software projects grow in complexity, organizations have gradually shifted toward more nuanced approaches to measuring productivity [4, 5]. Agile methodologies now allow teams to track effort based on completed tasks and time spent on each. Techniques like velocity tracking and continuous integration provide additional insights into both individual and team performance [1]. However, despite these advancements, many organizations still struggle with accurate project estimation and fair assessment of developer contributions [1].

One of the biggest challenges in estimation is the quality of underlying data. Corrupted or incomplete data can distort the assessment of a development team’s performance, leading to either overestimation or underestimation—both of which can be harmful to a project [7, 9]. Additionally, project uniqueness poses another hurdle; data from one project does not necessarily translate to another with accuracy [10]. Many estimation models also fail to account for dynamic factors such as team cohesion, individual skill levels, and past performance. Overlooking these elements can result in inaccurate complexity assessments, unrealistic deadlines, and resource misallocation, ultimately leading to missed milestones, budget overruns, and declining team morale [11, 12].

Beyond estimation errors, the reliability of collected data significantly impacts project outcomes. Even the most sophisticated estimation models are ineffective without valid, comprehensive data. However, gathering accurate metrics is inherently difficult. Some managers rely on just one or two indicators to guide decisions [1,4]. While having any metric is better than none, improper use can lead to misleading conclusions. For example, if a manager evaluates productivity based solely on completed tasks, all tasks must be of comparable scope in terms of time and complexity. This requires breaking down large assignments into smaller, well-defined units. Thus, managers must implement structured development processes and apply estimation techniques correctly to ensure reliable calculation.

Estimating project outcomes and tracking developer productivity is inherently challenging. To mitigate these difficulties, various methodologies have been developed, including COCOMO II, Earned Value Management (EVM), burn-down charts, and risk analysis. These techniques aim to improve project forecasts and resource planning [12-15, A1]. However, even with these tools, many organizations still struggle to predict when a project might become unprofitable or how team dynamics will influence future outcomes [16].

Exceptional results are achieved when management effectively leverages estimation tools and metrics to set realistic expectations for both themselves and their teams. High-performing teams use these insights to maintain productivity, meet deadlines, and stay within budget [17]. However, as projects grow in complexity, traditional estimation methods often fail to provide accurate predictions for cost, effort, and timelines. Managing productivity across larger teams becomes increasingly difficult, sometimes leading to diminishing returns [19]. To address these challenges, integrating activity-based metrics with the Constructive Cost Model II (COCOMO II) offers a promising approach to real-time budget control and team performance optimization.

COCOMO II has long been a cornerstone of software effort estimation, providing a structured, algorithmic model to predict development costs based on project attributes. However, its reliance on predefined parameters and historical data makes it less adaptable to dynamic development environments [A2]. In contrast, activity-based metrics—such as task completion rates, code churn, and real-time productivity indicators—offer a more up-to-date perspective on project progress and developer contributions. By combining these metrics with COCOMO II, organizations can refine their estimations in real time, leading to better decision-making and more efficient resource allocation [A3].

This integration of quantitative and qualitative insights enables managers to assess workload distribution more effectively and identify bottlenecks before they escalate into critical issues [10, 20-21]. Moreover, a major challenge in estimation lies in misreported or misinterpreted productivity metrics, which can result in inaccurate assessments, resource misallocation, or unjustified changes to project scope. By continuously refining cost estimations with real-time performance data, the integration of activity-based metrics with COCOMO II can help mitigate these issues.
This thesis aims to bridge the gap between static estimation models and dynamic project realities by answering key research questions:

#### Activity Metrics
- Why are traditional code and commit metrics insufficient for evaluating team productivity and project health?
- What makes churn a more effective metric for assessing software development activity, and how should it be collected and analyzed?
- How can activity metrics (e.g., churn, code velocity) be standardized to provide meaningful insights across different projects?

#### COCOMO II
- Why is COCOMO II still a relevant and effective model for software cost estimation despite its limitations?
- How does COCOMO II calculate project costs, and what factors (e.g., team organization, experience, and project complexity) influence its accuracy?
- How can activity metrics (e.g., churn, team velocity) be integrated into the COCOMO II model to improve cost estimation and project planning?
- What challenges arise when linking activity metrics to COCOMO II, and how can they be addressed in real-world software projects?

#### Budget Control and Team Performance
- How can real-time cost estimation trackers be developed to monitor project budgets dynamically?
- What parameters (e.g., team changes, deadlines, scope creep) should real-time cost estimation trackers depend on to ensure accuracy?
- How can project budget overruns be detected early, especially in cases of missed deadlines or team restructuring?

By addressing these questions, this research aims to enhance software project management by developing a framework that improves estimation accuracy and enables proactive budget monitoring. The framework will be tested through a prototype tool, allowing organizations to incorporate real-time, data-driven insights into their project management processes. Ultimately, this approach equips project managers with the tools to make informed decisions, optimize resource allocation, and ensure project success.

## Literature Review

### Introduction to Productivity in Software Development

Team productivity in software development is one of the most important aspects of IT industry projects because team productivity links technical, economic and social factors that directly affect the labor and monetary costs of an IT project [N1][T1]. This combination of many complex factors and the high cost of error makes the concept of development team productivity a very interesting and multifaceted subject for research. The topic of software development team productivity became especially relevant after the COVID-19 pandemic, when many developers were forced to work from home and the usual processes of interactions within the team needed urgent changes [N2].

Traditionally, productivity in software engineering has been defined using a simple quantitative formula: productivity = output / input, where input is measured in effort (e.g., person-hours), and output is estimated through proxies such as Lines of Code (LOC), Function Points (FP), or the number of features delivered [A1][?]. This model, borrowed from manufacturing, offers a clean and measurable view of productivity and has informed many early estimation techniques, including parametric models like COCOMO [A2].

However, this formulaic approach has been widely criticized for its oversimplification. In software development, output is difficult to quantify meaningfully, and size-based measurements often fail to reflect true business value, code quality, team collaboration, or innovation [T1]. Furthermore, the diversity of project contexts—different domains, technologies, and team structures—makes it problematic to compare productivity across projects using only size and effort [A1][T1].

As emphasized in prior research, “simple software productivity metrics based solely on software size and project effort are hardly comparable” due to these contextual discrepancies [T1]. Productivity and effort are deeply intertwined, influenced by a variety of factors such as domain complexity, technology stack, developer experience, and team cohesion [?]. As such, effective management and benchmarking of software productivity require a nuanced understanding of these influences. Effort estimation models can play a supporting role in establishing productivity baselines, but only when they consider these influencing factors explicitly and transparently.

In the framework of our thesis, we define productivity as a team’s ability to achieve outlined business objectives through developing, improving, and maintaining software [N3]. This value-oriented definition aligns more closely with modern Agile and DevOps philosophies, which emphasize outcomes over output, collaboration over countable units, and sustainable delivery over short-term throughput [?]. While this definition does not replace the need for quantitative models, it serves as a guiding principle for interpreting productivity in a broader and more meaningful way.

### Traditional Metrics and Their Limitations

As discussed in the Introduction, traditional software estimation approaches often rely on quantitative metrics such as lines of code, number of commits, or hours worked. While these indicators are easy to collect, they fall short in capturing the full scope of developer contributions, particularly in modern, agile environments where collaboration, refactoring, and non-coding activities play a significant role [?]. These limitations highlight the need for more holistic models of productivity that account for both technical and social dimensions of team performance. To address this, recent research has introduced multidimensional frameworks—most notably SPACE and DORA—that provide a richer understanding of developer productivity beyond surface-level output [?].

### Modern Productivity Frameworks

In 2021, at the ACM Queue conference, a team of researchers from Microsoft Research, GitHub, and D.R. proposed a framework called SPACE [N4]. This framework determines the performance factors of software development teams. SPACE is a multidimensional approach to evaluating developer productivity that goes beyond traditional metrics and takes into account not only the technical but also the social aspects of the team's work. It includes:

- Satisfaction: The degree to which developers are satisfied with their work has a significant impact on their motivation and overall quality of task performance. High levels of satisfaction can contribute to increased productivity. For example, code review perception metrics can determine how developers feel about this activity - whether they see value in it, such as opportunities for training, mentoring, or improving the quality of the codebase. This is especially important because an excessive number of code review tasks assigned to a single developer can cause resentment. If some team members feel that they are being given a disproportionate review burden, it may limit their time for other duties and reduce job satisfaction [N4].

- Performance: This is a traditional criterion that includes both quantitative measures (e.g., number of tasks or functions completed) and the quality of the work performed. For example, code review speed characterizes how quickly a review is completed. This metric can reflect both the reviewer's individual productivity and the constraints imposed by processes within the team. For example, a staff member may complete a review within an hour of being assigned, but a team may follow the practice of leaving review requests open for 24 hours to allow all team members to review proposed changes. Thus, this metric is applicable at both the individual developer and team-wide level. 

&ensp; &nbsp; &nbsp; &nbsp; In contrast, the DORA framework evaluates performance through four key metrics: deployment frequency, lead time for changes, mean time to recovery (MTTR), and change failure rate. These indicators focus heavily on delivery efficiency and system stability, making DORA particularly well-suited for DevOps and CI/CD environments where software delivery speed and reliability are critical [?].

&ensp; &nbsp; &nbsp; &nbsp; While SPACE provides a broader, more human-centric view that integrates developer experience and well-being into the performance equation, its flexibility can make it harder to measure consistently across teams.

- Activity: This metric evaluates the level of developer activity using metrics such as LOC, number of commits, or time spent programming. This provides a measure of team engagement. For example, the number of code reviews completed is a personal metric that reflects the number of reviews completed by a single developer over a given period and represents a contribution to the overall development outcome.

&ensp; &nbsp; &nbsp; &nbsp; Activity metrics are commonly used to evaluate developer productivity due to their ease of quantification. However, these indicators give only a limited idea of the overall performance. Developer activity is defined as the number of actions or outputs performed over time, such as coding new features, conducting code reviews, and completing project documentation [N4][N5]. Despite their value, these activity indicators cannot fully reflect the complexities and differences inherent in developer productivity across different environments and tasks. The diverse nature of the developers' activities makes it difficult to measure comprehensively. Factors such as overtime, irregular work schedules, and various support systems can significantly affect activity indicators. Therefore, when evaluating developer productivity, it is important to consider routine tasks such as meetings, problem solving, and brainstorming, in addition to coding activities [N5].

- Collaboration and Communication: Effective communication within the team is crucial for successful software development. This parameter covers the quality of communication between team members.For example, code reviews are themselves a form of collaboration between developers, realized through code. Assessing the quality and thoroughness of these reviews serves as an excellent qualitative indicator of the level of collaboration and communication within the team.


- Efficiency and Flow: This metric measures how efficiently the team utilizes its resources to achieve its goals. Flow describes the state of maximum developer concentration on tasks. For example, code reviews are important, but can create difficulties if they interrupt the workflow or cause delays that limit system performance. Waiting for code review can also slow down the developer's further activity. The optimal solution is to organize the process so that code reviews do not interfere with developer focus (which affects individual metrics), but do not slow down the overall flow of the system (which affects system metrics). This approach allows teams to release code efficiently (team-level metrics). Therefore, it is important to assess how the timing of code reviews affects the productivity and rhythm of individuals, teams, and the overall system. This can be done by using data collection or perception analysis tools that capture the timing of reviews and the characteristics of interruptions that occur (e.g., their frequency and when they occur) [N4].

These dimensions help evaluate both individual and team performance in a holistic way, offering a richer context than traditional metrics. For the SPACE framework to work effectively, it is recommended to take into account at least 3 dimensions of development, which provides a more comprehensive and objective view of processes [N4]. Considering this and the focus of our research, which is aimed at using the COCOMO2 methodology, which basically contains the metrics of the codebase, we will take a closer look at the factors and metrics directly related to the code.

As development teams strive for greater efficiency and accountability, organizations often turn to estimation models to predict resource needs, delivery timelines, and project outcomes. These models become essential as project complexity increases, team dynamics evolve, and business environments demand rapid yet reliable planning. While productivity frameworks like SPACE provide a deep understanding of team and individual performance, they do not inherently offer quantitative mechanisms to forecast effort, schedule, or budget. This gap is where estimation models, such as COCOMO II, play a pivotal role [?]. They offer structured methodologies to convert qualitative and activity-based insights into quantifiable forecasts that guide resource allocation and decision-making. To better understand how these estimation systems function and why they are critical to successful software project execution, we now examine effort estimation in software projects.

### Effort Estimation in Software Projects

Project management is a complex system of processes, methods, and tools aimed at achieving project success. In software development, success is traditionally defined as delivering a product with the required functionality and quality within budget and on schedule. However, this definition doesn't always reflect the real-world complexity of software projects, where success is influenced by many dynamic factors [T1]. This thesis concentrates on effort which encompasses both cost and time. Effort estimation is fundamental to project planning, and poor estimation of costs, timelines, or resource needs can lead to project failure. Consequently, accurate effort estimation models are vital for aligning stakeholder expectations, budgeting, and scheduling [T2].

Several commonly used project estimation techniques include Expert Judgment, Planning Poker, and Delphi Technique, which rely on collaborative inputs and consensus building, particularly effective in Agile teams. Function Point Analysis (FPA) and Use Case Points (UCP) offer more formalized approaches, translating functional requirements into effort estimates based on complexity and scope [A1]. Techniques like Story Points and Velocity Tracking are widely adopted in Agile environments for iterative and flexible planning.

Additionally, frameworks such as Earned Value Management (EVM) combine scope, schedule, and cost metrics to evaluate project performance against the baseline [?]. Tools like Jira, Microsoft Project, Rally, and Asana often include built-in capabilities for effort tracking and forecasting [?]. Machine learning models are also gaining traction, leveraging historical project data to predict timelines and cost with increasing accuracy [?].

While these approaches provide varying degrees of flexibility and granularity, they often struggle with maintaining accuracy in rapidly evolving projects or complex software ecosystems. This challenge has led to the continued relevance of structured algorithmic models like COCOMO [A1].

COCOMO is a well-established software development and cost estimation model that has evolved over the years to meet changing software development practices and methodologies [A2]. The first and original model, known as COCOMO 81, was introduced in 1981 by Dr. Barry Boehm in his textbook "Software Engineering Economics." It focused primarily on providing point estimates for software development effort, schedule, and cost based on a limited set of parameters. Initially developed in 1981, the model evolved over the years and was significantly updated in 2000 into what is now known as COCOMO II.

### COCOMO History

COCOMO 81 was the foundational version of the model, offering a structured, algorithmic approach to software cost estimation. It introduced three estimation levels—Basic, Intermediate, and Detailed—each increasing in accuracy and complexity. Estimates were derived based on the size of the codebase (in lines of code), adjusted by cost drivers that represented aspects like product complexity, personnel experience, and development tools. While revolutionary at the time, COCOMO 81 assumed a linear, waterfall-style development process, which limited its applicability in evolving project environments.

COCOMO II, introduced in 2000, addressed the limitations of its predecessor by incorporating flexibility for modern development paradigms, such as iterative development, software reuse, and component-based engineering. It features three submodels – Application Composition, Early Design, and Post-Architecture – each suited to different stages of a project’s life cycle. These models use a wider range of cost drivers and scale factors to enhance estimation accuracy. Despite its improvements, COCOMO II still relies heavily on predefined parameters and lacks real-time adaptability [10][11].

COSYSMO (Constructive Systems Engineering Cost Model) is an extension of COCOMO II designed specifically for systems engineering projects. It focuses on estimating effort related to system-level tasks such as requirements engineering, architecture design, and integration. COSYSMO incorporates its own set of cost drivers and effort multipliers suitable for large, interdisciplinary projects, making it highly relevant in aerospace, defense, and large-scale enterprise systems.

Agile COCOMO emerged as an adaptation of COCOMO II to accommodate Agile development methodologies. Since Agile projects often lack stable requirements and use story points rather than lines of code, Agile COCOMO uses analogy-based estimation methods, team velocity, and sprint-based planning to approximate cost and effort. Though not formally standardized, Agile COCOMO has seen various practical implementations and research efforts, aiming to maintain the structure of COCOMO while aligning with Agile's dynamic nature.

Fuzzy COCOMO incorporates fuzzy logic to deal with uncertainty and imprecision in parameter selection. Instead of assigning fixed levels (e.g., low, nominal, high) to cost drivers, Fuzzy COCOMO uses degrees of membership to model a range of possibilities. This allows for more nuanced effort estimation, especially in early stages of the project when precise data may be lacking. It enhances estimation flexibility while preserving the mathematical structure of COCOMO II.

AI-COCOMO or NeuroCOCOMO integrates machine learning algorithms with the COCOMO framework to improve parameter calibration. Artificial neural networks, support vector machines, and regression models are trained on historical project data to automatically learn the relationships between project characteristics and effort. These data-driven models aim to outperform traditional COCOMO in environments where rich datasets are available.

Dynamic COCOMO or Real-Time COCOMO is a recent evolution that enables dynamic recalculation of effort and cost estimates as project conditions change. It incorporates real-time metrics such as code churn, commit frequency, and task completion rates to continuously update the estimation model. Algorithms like fuzzy multi-objective optimization, reactive scheduling, and the SPRINT algorithm have been used to adapt the model in response to mid-project changes such as scope creep, team restructuring, or unexpected delays.

COCOMO III is a proposed but not yet formalized version that aims to integrate lessons learned from Agile, DevOps, and continuous delivery environments. Anticipated features include support for function points, SNAP points, and possibly even story points. COCOMO III is expected to introduce automated parameter tuning and better compatibility with modern development pipelines, but as of 2025, it remains a conceptual direction in academic and industrial discussions. Consequently, accurate effort estimation models are vital for aligning stakeholder expectations, budgeting, and scheduling.

| Model/Extension | Focus/Enhancement | Notable Features |
|---|---|---|
| COCOMO 81 | Waterfall-era projects | LOC-based, 3 estimation levels |
| COCOMO II | Modern development methods | 3 submodels, effort multipliers |
| COSYSMO | Systems engineering | Focused on architecture and integration |
| Agile COCOMO | Agile methodology | Story points, team velocity, sprint focus |
| Fuzzy COCOMO | Estimation under uncertainty | Fuzzy logic for cost driver ratings |
| AI-COCOMO | ML-enhanced estimation | ANN, regression, data-driven tuning |
| Dynamic COCOMO | Real-time project adjustments | Mid-project recalculations, live metrics |
| COCOMO III (future) | Anticipated evolution of COCOMO II | Function points, automation, DevOps-ready |

### Agile COCOMO II

Despite the wide range of enhancements built on top of COCOMO II, the core model retains a static nature that struggles to fully accommodate the dynamics of modern software development—particularly in Agile environments. Its reliance on upfront estimations, rigid cost drivers, and historical data limits its adaptability in contexts where team composition, scope, and development pace can change frequently. One of the earliest and most influential adaptations aimed at addressing these limitations was Agile COCOMO. This extension was specifically developed to better align COCOMO II with Agile principles, emphasizing flexibility, iteration, and continuous feedback.

The Agile COCOMO model adapts traditional effort estimation by incorporating analogy-based methods. Instead of depending solely on fixed size drivers like KLOC (thousands of lines of code), Agile COCOMO allows teams to estimate effort based on similar past projects – adjusting for current team structure, complexity, and process maturity [20][2]. It also gives more weight to high-impact cost drivers, such as developer experience, team cohesion, and schedule pressure – factors that play a central role in Agile teams where rapid collaboration and iterative progress are key [4][5][6].

The Agile COCOMO facilitates better decision-making and resource management in contemporary software engineering by leveraging historical data and dynamic developer metrics [9][10]. Agile COCOMO uses a blend of historical Agile project data, including:
- Sprint velocity (story points completed per sprint)
- Team size and skill levels
- Code churn (how much and how often the codebase changes)
- Lead time and cycle time
- Bug density and defect resolution time

These are mapped to cost drivers like team capability, process maturity, and product complexity, which COCOMO uses to adjust the base effort estimate. The estimation process is still parametric but now reflects Agile realities more closely.

Agile COCOMO is not designed as a real-time monitoring tool, but its strength lies in the iterative recalibration of estimates at different project stages [22][23]. For example, after each sprint or release planning session, the model can be adjusted based on newly observed performance metrics and team behavior. This allows for dynamic re-estimation based on feedback loops – a concept that resonates well with Agile’s inspect-and-adapt philosophy. That approach helps mitigate following Agile-specific challenges:
- Frequent scope changes
- Unclear initial requirements
- Non-linear team growth or restructuring
- Variation in productivity between sprints or developers

By focusing on relative estimation and adaptable effort modeling, it helps Agile teams avoid under- or overestimating project timelines and resource needs.

However, despite these advantages, Agile COCOMO still inherits some core limitations from the original COCOMO II. Notably, it often assumes that project size – measured by story points or function points – is still the main driver of cost and effort. In Agile contexts, this assumption can break down when team dynamics, communication quality, and collaboration efficiency play an even more critical role [7][8]. Furthermore, Agile COCOMO does not fully incorporate real-time tracking, nor does it automatically adjust estimations based on live project metrics without manual recalibration [22][24]. For this reason, researchers and practitioners often recommend supplementing Agile COCOMO with:
- Team feedback (e.g., retrospectives or confidence ratings) [25]
- Continuous integration metrics
- Empirical performance data from tools like Jira, Git, or SonarQube

Agile COCOMO is a valuable evolutionary step in adapting structured cost estimation to Agile practices. While it improves on static COCOMO II by adding flexibility and practical metrics, it still lacks the dynamic tracking capabilities required to provide ongoing budget control and schedule monitoring throughout the project lifecycle. These limitations highlight the need for new frameworks – like the one proposed in this thesis – that combine Agile estimation practices with real-time project data and automated recalibration logic.

### Real-Time COCOMO Concepts

Building on the identified limitations of Agile COCOMO, several research efforts have attempted to introduce real-time adaptability into cost estimation. These attempts aim to bridge the gap between static models and the dynamic nature of modern software projects. The motivation behind these efforts stems from common challenges encountered during development, such as team composition changes, frequent code modifications, and shifts in resource allocation [?][?]. In the following sections, we examine how these challenges have been addressed through various real-time enhancements and optimization strategies within the COCOMO II framework.

### Real-Time COCOMO Concepts

#### Team Composition Changes

Adjustments in team structure—such as onboarding new developers or losing key personnel—can significantly impact project cost and timeline accuracy. Traditional COCOMO II fails to account for the nuanced effects of team dynamics. To address this, researchers have proposed models like the Fuzzy Emotional COCOMO II (FECSCE), which incorporates human factors such as communication ability, mood, and personality [?]. FECSCE uses Multi-Agent Systems (MAS) to simulate interpersonal interactions and adjust estimation outputs accordingly (Kazemifard et al., 2011).

Another promising direction is the development of multi-objective dynamic scheduling models that recalibrate project plans in response to team changes. These models use domain knowledge and evolutionary strategies to maintain convergence and performance when project teams evolve midstream ("Multi-Objective Dynamic Software Project Scheduling", 2023).

#### Code Modifications

Ongoing changes to the codebase – whether through rework, refactoring, or scope creep – introduce volatility that traditional estimation models cannot track. In response, dynamic optimization approaches have been proposed. Notably, a multi-objective firework algorithm was developed to adjust workload distributions and schedule planning based on project evolution (Cheng et al., 2019). This method offers a novel scheduling mechanism using simulated “explosions” to explore and refine project adjustments.
Complementary to this are disruption-driven resource rescheduling algorithms, such as those based on genetic algorithms (Xiao et al., 2010), which reassign resources in real time when unexpected changes occur. These methods are especially useful in maintaining optimal project duration and cost amid code churn.

#### Resource Allocation Shifts

Unexpected shifts in priorities or resource availability (e.g., team member reassignment or absenteeism) also affect estimation accuracy. Reactive scheduling approaches have been developed to mitigate this, using both preemptive and non-preemptive reassignment strategies (Haque, 2012). These systems evaluate resource constraints and modify timelines to maintain feasibility.

Recent work using hybrid genetic algorithms with variable neighborhood search has shown success in managing multi-project environments (Xu & Bai, 2023). These models help minimize deviation from original plans while adjusting to new constraints, proving particularly effective in high-variance Agile contexts.

### Optimization and Enhancement Techniques

Beyond direct responses to environmental changes, several techniques have been proposed to optimize COCOMO II’s accuracy under dynamic conditions. One such method is fuzzy multi-objective particle swarm optimization (MOPSO), which calibrates effort estimation using Gaussian Membership Functions (GMF) to handle uncertainty (Langsari & Sarno, 2017). MOPSO improves estimation precision by accounting for ambiguity in early project data and soft transitions in team performance.

Additionally, hybrid estimation methods combining COCOMO II with machine learning or algorithmic prioritization – such as the SPRINT algorithm – have shown potential. The SPRINT approach uses historical module data to reprioritize tasks and refine estimation accuracy, achieving impressive results in experimental evaluations (Awalliya et al., 2024).

Table 1 summarizes the key approaches discussed in the research papers and their respective citations, providing a quick reference for understanding how COCOMO II can be dynamically evaluated and adjusted in response to mid-project changes.

Table 1: Summary of Key Approaches and Their Impacts

| Aspect of Change | Approach | Citation |
|---|---|---|
| Team Composition Changes | Fuzzy Emotional COCOMO II model (FECSCE) using Multi-Agent Systems | (Kazemifard et al., 2011) |
| Code Modifications | Dynamic multi-objective optimization with firework algorithm | (Cheng et al., 2019) |
| Resource Allocation | Reactive scheduling with preemptive and non-preemptive strategies | (Haque, 2012) |
| Optimization Techniques | Fuzzy multi-objective particle swarm optimization (MOPSO) | (Langsari & Sarno, 2017) |
| Resource Disruptions | Hybrid genetic algorithm with variable neighborhood search | (Xu & Bai, 2023) |
| Effort Estimation Accuracy | Combination of COCOMO II with SPRINT algorithm | (Awalliya et al., 2024) |

### Metrics and Practices for Real-Time Estimation

Various metrics have been proposed to support real-time cost estimation, especially when integrated into Agile or CI/CD workflows. Key metrics include:
- Function Points and Lines of Code (LOC): Traditional yet still effective, often used for early-phase estimates.
- Code Churn: Measures frequency and volume of code changes—useful for identifying volatility in the development process.
- Task Completion Rate: Tracks how many tasks are completed within a given sprint or timeframe.
- Developer Productivity Metrics: Includes active coding time, bug resolution speed, and commit frequency—providing a qualitative view of team performance.

Research emphasizes that no single metric is reliable enough on its own. Instead, combinations of dynamic metrics tend to provide the most accurate forecasts, especially when mapped to cost drivers and project states

### Successes and Limitations of Current Approaches

#### Successful Integrations
Some hybrid approaches have demonstrated improved accuracy, particularly when combining real-time metrics with traditional estimation logic. For example:
- Hybrid estimation models that dynamically update COCOMO II inputs based on CI/CD metrics have improved forecasting precision in Agile environments.
- Machine Learning-augmented COCOMO has enabled adaptive tuning of cost drivers in response to live performance data.

#### Unsuccessful or Limited Attempts
Not all efforts have been successful. Studies reveal common pitfalls such as:
- Over-reliance on single metrics (e.g., only using LOC) often results in inaccurate predictions due to lack of context.
- Lack of integration with development pipelines, meaning estimates are not updated in sync with real project progress, causing them to become outdated quickly.

### Challenges in Real-Time COCOMO Integration
Despite the promise of real-time adaptations, several challenges still hinder practical deployment:
- Data Accuracy and Consistency: Real-time models rely on clean, continuous input. Developer reporting inconsistencies, gaps in data collection, or tool misconfigurations can compromise outputs.
- Computational Complexity: Dynamic recalculations require significant resources, particularly in large or multi-project settings.
- Organizational Resistance: Many teams still depend on static or manual estimation methods, slowing adoption of real-time tracking systems.

### Conclusion and Research Opportunity

In summary, the literature shows a growing body of work aimed at making COCOMO II more adaptable through dynamic estimation methods. These efforts address various real-world disruptions using optimization techniques, real-time metric integration, and machine learning enhancements. However, most approaches remain fragmented or computationally intensive, and few offer end-to-end support for budget and timeline control throughout the project lifecycle.
This opens a clear research opportunity: to develop a lightweight, real-time estimation framework that extends COCOMO II with dynamic metric integration, automated recalibration, and practical decision support for project managers. The following section presents such a solution – designed to be both technically feasible and aligned with Agile project realities.

## References:

[1] Nicole Forsgren, Margaret-Anne Storey, Chandra Maddila, Thomas Zimmermann, Brian Houck, and Jenna Butler. 2021. "The SPACE of Developer Productivity: There's more to it than you think". Queue 19, 1, Pages 10 (January-February 2021), 29 pages. https://doi.org/10.1145/3454122.3454124

[2] Abdul Razzaq, Jim Buckley, Qin Lai, Tingting Yu, and Goetz Botterweck. 2024. "A Systematic Literature Review on the Influence of Enhanced Developer Experience on Developers' Productivity: Factors, Practices, and Recommendations". ACM Comput. Surv. 57, 1, Article 13 (January 2025), 46 pages. https://doi.org/10.1145/3687299

[3] Oliveira, E., Fernandes, E., Steinmacher, I. et al. "Code and commit metrics of developer productivity: a study on team leaders perceptions". Empir Software Eng 25, 2519–2549 (2020). https://doi.org/10.1007/s10664-020-09820-z

[4] Hai, Vo Van, Ho Le Thi Kim Nhung, Zdenka Prokopova, Radek Silhavy, and Petr Silhavy. 2022. "A New Approach to Calibrating Functional Complexity Weight in Software Development Effort Estimation" Computers 11, no. 2: 15. https://doi.org/10.3390/computers11020015

[5] M. Fernández-Diego, E. R. Méndez, F. González-Ladrón-De-Guevara, S. Abrahão and E. Insfran, "An Update on Effort Estimation in Agile Software Development: A Systematic Literature Review," in IEEE Access, vol. 8, pp. 166768-166800, 2020, doi: 10.1109/ACCESS.2020.3021664.

[7] James Cadle and Donald Yeates. 2007. "Project Management for Information Systems (5th. ed.)". Prentice Hall Press, USA.

[10] Samya, Sumithra, Vijayalakshmi Nagarajan, Ahilan Appathurai, and Salinda Suniram. "Software Cost Effort and Time Estimation Using Dragonfly Whale Lion Optimized Deep Neural Network." Revue Roumaine des Sciences Techniques, Série Électrotechnique et Énergétique 69 (2024): 431–436. https://doi.org/10.59277/RRST-EE.2024.69.4.11

[9] [The road to results, ...](https://doe-10.1596/978-0-8213-7891-5)

[17] T. Korhonen, A. Jääskeläinen, T. Laine, and N. Saukkonen, “How performance measurement can support achieving success in project-based operations,” International Journal of Project Management, vol. 41, no. 1, p. 102 429, 2023, ISSN: 0263-7863. doi: https://doi.org/10.1016/j.ijproman.2022.11.002. [Online](https://doi.org/10.1016/j.ijproman.2022.11.002). Available: https://www.sciencedirect.com/science/article/pii/S0263786322001326.

[18] Tapasco-Alzate, Omar, Jaime A. Giraldo-García and Diógenes de Jesus Ramírez-Ramírez. “Productivity metrics in the context of knowledge work: literature vs practice.” International Journal of Productivity and Performance Management ahead-of-print (2021): n. pag.

[19] A. Coskun and R. Erturgut, “An empirical research on developing a logistics performance scale,” International Journal of Productivity and Performance Management, vol. ahead-of-print, Feb. 2021. doi: 10.1108/ijppm-10-2020-0513.

[20] Schmidt, Roy & Lyytinen, Kalle & Keil, Mark & Cule, Paul. (2001). Identifying Software Project Risks: An International Delphi Study. J. of Management Information Systems. 17. 5-36. 10.1080/07421222.2001.11045662.

[21] Boehm, B. (2004). Balancing Agility and Discipline: A Guide for the Perplexed. In: Ramamoorthy, C.V., Lee, R., Lee, K.W. (eds) Software Engineering Research and Applications. SERA 2003. Lecture Notes in Computer Science, vol 3026. Springer, Berlin, Heidelberg. https://doi.org/10.1007/978-3-540-24675-6_1

[22]Trendowicz, Adam; Jeffery, Ross . (2014). Software Project Effort Estimation || . , 10.1007/978-3-319-03629-8(), –. doi:10.1007/978-3-319-03629-8 https://link.springer.com/book/10.1007/978-3-319-03629-8

[24] Kaur, Harmandeep & Saini, Munish. (2019). Productivity Metric Estimation: Comprehensive Examine of Efficiency, Effectiveness and Value Based Metrics. International Journal of Innovative Technology and Exploring Engineering. 9. 10.35940/ijitee.A7107.129219. 

[25] Kupiainen, Eetu, Mika V. Mäntylä, and Juha Itkonen. "Using metrics in Agile and Lean Software Development – A systematic literature review of industrial studies." Information and Software Technology 62 (2015): 143-163. https://doi.org/10.1016/j.infsof.2015.02.005.

[26] Abdul Razzaq, Jim Buckley, Qin Lai, Tingting Yu, and Goetz Botterweck. (2024). A Systematic Literature Review on the Influence of Enhanced Developer Experience on Developers' Productivity: Factors, Practices, and Recommendations. ACM Comput. Surv. 57, 1, Article 13 (January 2025), 46 pages. https://doi.org/10.1145/3687299

[27] Chakravarty, K., Singh, J. (2021). A Study of Quality Metrics in Agile Software Development. In: Swain, D., Pattnaik, P.K., Athawale, T. (eds) Machine Learning and Information Processing. Advances in Intelligent Systems and Computing, vol 1311. Springer, Singapore. https://doi.org/10.1007/978-981-33-4859-2_26

[28] Yadav, Rahul Kumar, and S. Niranjan. "Project Effort Estimation using COCOMO-2 Metrics with Fuzzy Logic." Indian Journal of Science and Technology 10 (2017): 29.

[29] Ajiga, Daniel, et al. "Enhancing software development practices with AI insights in high-tech companies." (2024).

[30] Kerzner, Harold. Project management metrics, KPIs, and dashboards: a guide to measuring and monitoring project performance. John wiley & sons, 2022.

[31] Malhotra, R., Lata, K. An empirical study on predictability of software maintainability using imbalanced data. Software Qual J 28, 1581–1614 (2020). https://doi.org/10.1007/s11219-020-09525-y

[32] Chowdhury, S., Holmes, R., Zaidman, A. et al. Revisiting the debate: Are code metrics useful for measuring maintenance effort?. Empir Software Eng 27, 158 (2022). https://doi.org/10.1007/s10664-022-10193-8  

[33] Menozzi, Samuel, and Philippe Grégoire. "" Analyse fondamentale des actions-Valorisation des entreprises. Cas pratique: Ubisoft Entertainment SA."

[34] Dunnette, M.D., & Fleishman, E.A. (Eds.). (1982). Human Performance and Productivity: Volumes 1, 2, and 3 (1st ed.). Psychology Press. https://doi.org/10.4324/9781315802909

[35] Derek DeBellis, Kevin M. Storer, Amanda Lewis et al. DORA Accelerate
State of DevOps (2024) https://cloud.google.com/resources/devops/state-of-devops

[36] Samya, Sumithra, Vijayalakshmi Nagarajan, Ahilan Appathurai, and Salinda Suniram. "Software Cost Effort and Time Estimation Using Dragonfly Whale Lion Optimized Deep Neural Network." Revue Roumaine des Sciences Techniques, Série Électrotechnique et Énergétique 69 (2024): 431–436. https://doi.org/10.59277/RRST-EE.2024.69.4.11.

[N1] C. H. C. Duarte, "Software productivity in practice: A systematic mapping study," Software, vol. 1, pp. 164–214, 2022, doi: 10.3390/software1020008.

[N2] P. Ralph et al., "Pandemic programming: How COVID-19 affects software developers and how their organizations can help," Empirical Software Engineering, vol. 25, no. 6, pp. 4927–4961, 2020. [Online]. Available: https://www.researchgate.net/publication/344342621.

[N3] Zenhub, "Developer productivity management: A complete guide," 2024. [Online]. Available: https://www.zenhub.com/guides/developer-productivity.

[N4] N. Forsgren et al., "The SPACE of developer productivity: There's more to it than you think," Queue, vol. 19, no. 1, pp. 20–48, Jan.–Feb. 2021, doi: 10.1145/3454122.3454124.

[N5] Waydev, "The SPACE framework for developer productivity," 2022. [Online]. Available: https://waydev.co/wp-content/uploads/2022/12/Space-Blog-PDF-_compressed.pdf.

[N6] Codacy, "Understanding the SPACE framework for developer productivity," 2024. [Online]. Available: https://blog.codacy.com/space-framework.

[N7] GetDX, "DORA metrics: Measuring software delivery performance," 2024. [Online]. Available: https://getdx.com/blog/dora-metrics/.

[N8] B. Curtis, W. E. Hefley, and S. Miller, "People capability maturity model (P-CMM) version 2.0," Carnegie Mellon University, Tech. Rep. CMU/SEI-2009-TR-003, 2009. [Online]. Available: https://www.rose-hulman.edu/class/cs/csse372/201310/Homework/CII_modelman2000.pdf.