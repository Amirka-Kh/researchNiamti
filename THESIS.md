# Amazing Relation of Developer and Project Estimations

## Abstract

Accurate project estimation and developer contribution analysis are critical to the success of software development projects. This research explores the challenges of linking developer productivity metrics to project estimation, with the goal of improving project planning and team efficiency. By analyzing a wide range of productivity and estimation models, the study identifies metrics most closely linked to project outcomes. A prototype tool was tested in a real-world setting, highlighting potential insights into productivity trends and estimation accuracy. Preliminary findings demonstrate the potential of combining data-driven metrics with qualitative insights, providing a foundation for future research and tool development.

Our tool was tested in a real-world setting by a software development company. The results were encouraging: the tool identified a developer who claimed to be overworked but whose contributions were average compared to the rest of the team. The situation led to the developer's voluntary departure, which, according to the company, had a positive impact on team morale and overall productivity. These findings demonstrate the potential of our tool to improve both project estimation and team dynamics, ultimately contributing to more efficient project management.It should be noted that we do not claim that our tool is a silver bullet for assessing the feasibility of any project. We are only saying that we have had a successful experience in test trials, which gives room for further research. In our case, the tool has been successful, but a full-fledged study is necessary for consistent conclusions.

## Introduction

In the fast-paced world of software development, the ability to accurately estimate project parameters and evaluate developer contributions is critical to a project’s success. Proper estimation helps set clear, achievable expectations for developers, which enhances their productivity and aligns their efforts with the project’s goals [1]. When developers see that their contributions are correctly recognized and rewarded, their motivation increases, leading to better work engagement. The relationship between work satisfaction and productivity is well-documented: when individuals satisfied with job and work environment and feel valued for the job they perform, they are more inclined to improve and grow, fostering a positive cycle of motivation and productivity [2].

The practice of estimating project timelines and budgets, as well as measuring developer productivity, has evolved significantly over time. Traditionally, project estimation involved basic metrics like the number of lines of code (LOC), budget allocation, and deadline setting [3]. While these methods provided a foundation, they often fell short of capturing the full complexity of modern software development environments. Similarly, developer contribution was historically measured by lines of code produced, hours and the number of bugs found\fixed, failing to account for the qualitative aspects of a developer’s work, such as innovation, collaboration, or code quality [2, 3, 5].

With the growing complexity of software projects, there has been a gradual shift toward more nuanced methods of collecting and analyzing productivity metrics [4, 5]. Agile methodologies have allowed organizations to directly link developer effort with the amount of tasks completed and the time spent on each. Techniques such as velocity tracking and continuous integration have introduced additional metrics for assessing both team and individual performance [1]. However, despite these advancements, many organizations still struggle to accurately predict project outcomes and fairly evaluate developer contributions [1].

Two main problems in project estimation are corrupted data and incorrect calculations [7]. Decisions based on corrupted data can provide a misleading picture of the development team, potentially leading to their underestimation or overestimation; neither scenario benefits the project [9]. Additionally, each project is unique, and statistical data from one project does not guarantee accuracy for another [10]. Furthermore, without appropriate techniques, management may fail to consider the dynamic nature of development teams and their productivity history. For instance, factors such as team cohesion, individual skill levels, and past project performance are often overlooked when estimating project complexity or setting deadlines [11]. As a result, projects are frequently either over- or under-estimated, which can lead to missed deadlines, budget overruns, and a general decline in team morale [12].

Moreover, having valid data is challenging, as collecting metrics can be difficult. Some managers tend to rely on only one or two metrics to base their decisions [1,4]. While this approach is better than having no metrics at all, it must be used correctly. For instance, if a manager tracks the number of tasks accomplished by developers, all tasks should have similar scope in terms of time and complexity, which can be achieved by breaking down larger tasks into smaller ones. So, manager should also set right development process and make right calculations.

While estimating project outcomes and tracking developer productivity is no easy task, various methodologies have been developed to mitigate these challenges. Techniques like COCOMO2, Earned Value Management (EVM), burn-down charts, and risk analysis aim to provide more accurate project forecasts [12-15]. However, even with these tools, predicting when a project will become unprofitable or how team dynamics will affect future outcomes remains a challenge for many organizations [16].

Amazing results are achieved, when management have mastered the use of tools and metrics to set realistic expectations for both themselves and their development teams. These teams leverage their understanding of metrics to maintain high productivity and consistently meet project deadlines and budget constraints [17]. However, as these teams grow in size, they encounter new challenges [18]. Scaling these processes effectively becomes more difficult, and the complexity of tracking productivity across larger teams can lead to diminishing returns [19].

Despite the current state of project estimation and developer contribution analysis, there is substantial room for improvement. Our aim is not to critique the entire industry but to build on the foundation that already exists and push it forward. While there are teams that have mastered the art of project and productivity estimation, there is still a need for frameworks to avoid making mistakes when using metrics and there is a need for tools to automate metrics to help teams maintain accurate project and productivity estimation as they scale [10, 20-21].

This thesis aims to develop a tool that will assist teams and management in tracking productivity and accurately estimating future projects—whether that be setting deadlines, predicting budget overruns, or assessing team dynamics. To achieve this goal, we will address the following key questions:

- RQ 1: Which factors influence productivity?
  - RQ 1.1: What is the productivity of a software development (SD) team?
  - RQ 1.2: Which factors influence that productivity?
  - RQ 1.3: Which metrics are applied to measure those factors?
  - RQ 1.4: Which metrics among them are reliable?
- RQ 2: How metrics can help control productivity of SD team?

  - RQ 2.1: What the productivity metrics can tell about SD team?
  - RQ 2.2: Which metrics has more weight in the team description?

- RQ 3: How to estimate effort based on project and team data?

  - RQ 3.1: What models/techniques are available and on what data is estimation based?
  - RQ 3.2: What factors influence to accuracy of effort estimation?
  - RQ 3.3: How to improve effort estimation?

By answering these questions, we hope to create a useful tool that will not only help mature teams continue to succeed as they scale but will also aid less experienced management teams in improving their estimation processes and decision-making. Ultimately, the goal is to develop a comprehensive framework that benefits all stakeholders in software development, from developers to project managers to upper management.

## Literature Review

The essence of estimating both productivity and project outcomes has long been understood—metrics and data are vital for all stakeholders, from developer leads to upper management and directors. However, despite the availability of metrics, many organizations do not succeed to estimate productivity and manage project planning. Our objective is to investigate why it is happening and propose a more effective approach to the use of metrics. We will explore which factors influence productivity as well as how they can be linked to project estimation in a meaningful way. By understanding the correct factors we will find related metrics to measure those factors. With these metrics we aim to define a clear framework for productivity and project estimation. This will also help us determine how to calculate project costs accurately. The following chapters will focus on the practical aspects of implementation and address the potential challenges in collecting and analyzing these metrics.

#### Problem with Metrics, Diverse Nature of Productivity

One of the most prevalent misconceptions in productivity estimation is the belief that a single metric can capture the entire picture. Many management teams and leads tend to rely on isolated metrics—whether it's the number of commits, lines of code, or hours worked—believing that these metrics alone provide a comprehensive view of developer productivity. However, all metrics have flaws, and when used in isolation, they can paint a misleading picture. Metrics are often subject to corruption, manipulation, or misinterpretation. For example, near project deadlines, developers may work longer hours, inflating activity metrics without necessarily reflecting real progress or quality.

Furthermore, different stakeholders require distinct sets of metrics. For example, management tends to focus on high-level metrics such as business outcomes and project timelines, while team leads might prioritize code quality and task completion. DevOps teams focus on operational efficiency, such as deployment frequency and uptime. These differing perspectives mean that no single metric can serve all needs, making it essential to gather a broad set of metrics from different dimensions.

Moreover, the reliability of metrics is a critical consideration, as they are often corrupted or inaccurate. This issue arises when project managers or leads are unable to enforce or verify adherence to established work protocols. For instance, developers may fail to track their time, assign estimation points only after tasks are completed, or move tasks between stages without valid justification. Such practices lead to data gaps or misrepresentations [31]. Misuse in the collection of metrics further exacerbates this issue. Recent research analyzing 730,000 Java methods from 47 open-source projects highlights how contradictions in prior studies often stem from differences in evaluation contexts and indicators [32]. The findings emphasize that source code metrics can provide reliable insights into maintenance effort only when applied with careful consideration of context, avoiding one-size-fits-all approaches. Ensuring data reliability requires adherence to proper guidelines and methodologies for metric usage.

However, many crucial factors are often overlooked, particularly qualitative indicators such as team morale, experience, contextual nuances, and environmental conditions. Neglecting these elements can result in incomplete or inadequate assessments of project performance. To address this challenge, it is essential to identify and focus on the minimum relevant set of metrics and indicators tailored to the specific context of the project. This approach ensures a more comprehensive evaluation of productivity and effort, ultimately leading to more informed decision-making [22].

Certainly! Here’s the revised paragraph with a smoother transition and integration of your suggestion:

The SPACE framework (Satisfaction, Performance, Activity, Collaboration, and Efficiency) is a good example of how productivity should be viewed across multiple dimensions [1]. Satisfaction, for example, is closely linked to productivity, as happier developers tend to produce higher-quality work and are less prone to burnout. Collaboration metrics reflect how well team members work together, while activity metrics track tangible outputs like commits and reviews. However, these activity metrics alone are insufficient without the context of performance and efficiency. For instance, a team may feel happy and satisfied but fail to deliver meaningful business outcomes, as seen in some game development projects like Ubisoft’s Skull and Bones [33]. This highlights why performance and efficiency are crucial for interpreting activity metrics meaningfully. A team that is performing well can often be many times more efficient than individual developers working in isolation, underscoring the importance of balancing team dynamics and individual contributions [34]. Metrics should not just track outputs but also identify potential issues, such as burnout, dissatisfaction, and unrealistic expectations.

Research in software development increasingly acknowledges the impact of Developer Experience (DevX) on Developer Productivity (DevP). The study by Razzaq et al. (2024) provides a systematic review of the various DevX factors and the practices that enhance DevX, revealing their significant role in influencing DevP. The authors identified a range of DevX factors, such as work fragmentation, developer concentration, and availability of resources, as well as a suite of practices designed to improve these factors, thereby positively impacting productivity [26].

According to the study, several essential practices have been identified as enhancing DevX in ways that positively affect productivity. These include minimizing interruptions, improving team collaboration, and ensuring a stable, supportive technical environment. For productivity evaluation, understanding the status of these DevX factors is crucial. Low indicators in DevX metrics may suggest the need to implement specific DevX practices, which can enhance team satisfaction, reduce inefficiencies, and ultimately boost overall productivity.

From Razzaq et al.'s work, we extracted and classified a list of measurable DevX metrics, organizing them by applicability and ease of collection. The table below presents these metrics and their categorization, providing a structured approach to incorporate DevX factors into our productivity measurement framework. In cases where specific DevX metrics fall below expectations, targeted DevX practices can be employed to address gaps, thereby aligning DevX with productivity goals in a data-driven way.

#### Issues in Project Estimation

Project estimation is a complex process prone to significant errors. Many organizations depend on data that may be outdated or poorly aligned with the context of the current project. For example, relying on historical data or static tools like Gantt charts can lead to inaccurate assessments, especially when the new project significantly differs from previous ones. Models that utilize methods such as story points or task count statistics offer some predictive capabilities regarding project volume and complexity. However, these approaches often fail when the underlying data is misaligned with the unique requirements of the project. Improving the estimation process demands careful adaptation to specific project contexts rather than a one-size-fits-all methodology. [22]

Another popular method, COCOMO 2, provides a more structured approach to project estimation but comes with its own set of limitations. Specifically, COCOMO 2 struggles with accurately reflecting team dynamics, work culture, and atmosphere. It also uses a broad set of parameters, some of which may be unclear or difficult to quantify. The rigid structure of models like COCOMO 2 can lead to inaccuracies, particularly in cases where human factors like satisfaction and team cohesion play significant roles in project outcomes.

Techniques for estimating efforts are divided into non-algorithmic and algorithmic, only some of each group are described above. For example, the methods using story points as an indicator are based on expert assessment and are non-algorithmic, in turn COCOMO 2 is based on a clear algorithm with mathematical equations requiring specific quantitative data and coefficients. [5, 22]

In this article, we will discuss the pros and cons of each approach, and outline a balanced strategy that will allow you to select relevant factors, indicators, an evaluation model or a hybrid of several models to achieve adequate results of estimating project efforts.

## Methodology and Design

#### A Correct Approach to Productivity and Project Estimation

To address these issues, productivity estimation should begin with accurate and comprehensive metric collection [24]. Code-related metrics, such as churn rate, number of lines of code, and changes per commit, are essential, but they should be complemented by metrics related to story points, tasks completed, and time spent [25]. These should be analyzed in relation to team satisfaction and cohesion, as both have a direct impact on long-term productivity.

When it comes to project estimation, a refined approach is necessary. We propose using an enhanced version of COCOMO 2 that incorporates better metrics and more reliable data derived from developer feedback and team estimation [28]. For example, recent studies have demonstrated a correlation between developer satisfaction and project success [1, 26]. This suggests that satisfaction metrics can help predict the efficiency of the team and the likelihood of meeting project deadlines. By collecting and analyzing satisfaction data, we can better understand how a team’s organization affects its performance, and use this information to make more accurate project estimations [29, 30].

#### Linking Productivity Metrics with Project Estimation

This research aims to explore how software development team productivity impacts project estimation accuracy. Factors like task completion rates, code churn, and team collaboration metrics are often studied separately from project estimation. However, this research investigates the potential connections between these domains. The preliminary objective is to identify productivity-related factors that influence labor costs and, consequently, the reliability of project estimations. This exploratory study will provide foundational insights without proposing new tools or frameworks, maintaining a focused scope in line with the study’s goals.

#### Defining Useful Metrics for Productivity and Project Estimation

From our analysis, we have identified several key metrics that will be useful for our project estimation framework. These include traditional code metrics like lines of code and churn, as well as more nuanced metrics like team satisfaction, task complexity, and collaboration efficiency. By focusing on a multidimensional set of metrics, we can better understand the real productivity of developers and use this data to inform project estimations. This will allow us to answer our second research question: which metrics are the most useful for productivity and project estimation?

#### Using Statistics to Estimate Project Outcomes

Once we have collected the relevant metrics, the next step is to use statistical analysis to link this data to project outcomes. By examining patterns in productivity and satisfaction over time, we can develop models that predict the likelihood of project success, cost overruns, and missed deadlines. These models will take into account both the quantitative metrics (such as churn and task completion) and qualitative factors (such as developer satisfaction and team dynamics). By answering our third research question—how can statistics be used to estimate project outcomes?—we hope to provide a robust framework for improving project estimations.

In this chapter, we have explored the common myths and mistakes associated with productivity and project estimation, and proposed a more comprehensive approach to addressing these issues. By collecting the right metrics and using a multidimensional approach, we can better understand the productivity of development teams and make more accurate project estimations. In the next chapter, we will delve into the practical details of implementing this approach, including the challenges of collecting reliable metrics and using them effectively in project planning.

References:

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