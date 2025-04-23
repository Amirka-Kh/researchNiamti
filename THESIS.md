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

The essence of estimating both productivity and project outcomes has long been understood—metrics and data are vital for all stakeholders, from developer leads to upper management and directors. However, despite the availability of metrics, many organizations do not succeed to estimate productivity and manage project planning. Our objective is to investigate why it is happening and propose a more effective approach to the use of metrics. We will explore which factors influence productivity as well as how they can be linked to project estimation in a meaningful way. By understanding the correct factors we will find related metrics to measure those factors. With these metrics we aim to define a clear framework for productivity and project estimation. This will also help us determine how to calculate project costs accurately. The following chapters will focus on the practical aspects of implementation and address the potential challenges in collecting and analyzing these metrics.

#### Problem with Metrics, Diverse Nature of Productivity

One of the most prevalent misconceptions in productivity estimation is the belief that a single metric can capture the entire picture.[1] Many management teams and leads tend to rely on isolated metrics—whether it's the number of commits, lines of code, or hours worked—believing that these metrics alone provide a comprehensive view of developer productivity. However, all metrics have flaws, and when used in isolation, they can paint a misleading picture. Metrics are often subject to corruption, manipulation, or misinterpretation. For example, near project deadlines, developers may work longer hours, inflating activity metrics without necessarily reflecting real progress or quality.

Furthermore, different stakeholders require distinct sets of metrics. For example, management tends to focus on high-level metrics such as business outcomes and project timelines, while team leads might prioritize code quality and task completion. DevOps teams focus on operational efficiency, such as deployment frequency and uptime. These differing perspectives mean that no single metric can serve all needs, making it essential to gather a broad set of metrics from different dimensions.[1, 35]

Moreover, the reliability of metrics is a critical consideration, as they are often corrupted or inaccurate. This issue arises when project managers or leads are unable to enforce or verify adherence to established work protocols. For instance, developers may fail to track their time, assign estimation points only after tasks are completed, or move tasks between stages without valid justification. Such practices lead to data gaps or misrepresentations [31]. Misuse in the collection of metrics further exacerbates this issue. Recent research analyzing 730,000 Java methods from 47 open-source projects highlights how contradictions in prior studies often stem from differences in evaluation contexts and indicators [32]. The findings emphasize that source code metrics can provide reliable insights into maintenance effort only when applied with careful consideration of context, avoiding one-size-fits-all approaches. Ensuring data reliability requires adherence to proper guidelines and methodologies for metric usage.

However, many crucial factors are often overlooked, particularly qualitative indicators such as team morale, experience, contextual nuances, and environmental conditions. Neglecting these elements can result in incomplete or inadequate assessments of project performance. To address this challenge, it is essential to identify and focus on the minimum relevant set of metrics and indicators tailored to the specific context of the project. This approach ensures a more comprehensive evaluation of productivity and effort, ultimately leading to more informed decision-making [22].

The SPACE framework (Satisfaction, Performance, Activity, Collaboration, and Efficiency) is a good example of how productivity should be viewed across multiple dimensions [1]. Satisfaction, for example, is closely linked to productivity, as happier developers tend to produce higher-quality work and are less prone to burnout. Collaboration metrics reflect how well team members work together, while activity metrics track tangible outputs like commits and reviews. However, these activity metrics alone are insufficient without the context of performance and efficiency. For instance, a team may feel happy and satisfied but fail to deliver meaningful business outcomes, as seen in some game development projects like Ubisoft’s Skull and Bones [33]. This highlights why performance and efficiency are crucial for interpreting activity metrics meaningfully. A team that is performing well can often be many times more efficient than individual developers working in isolation, underscoring the importance of balancing team dynamics and individual contributions [34]. Metrics should not just track outputs but also identify potential issues, such as burnout, dissatisfaction, and unrealistic expectations.

Research in software development increasingly acknowledges the impact of Developer Experience (DevX) on Developer Productivity (DevP). The study by Razzaq et al. (2024) provides a systematic review of the various DevX factors and the practices that enhance DevX, revealing their significant role in influencing DevP. The authors identified a range of DevX factors, such as work fragmentation, developer concentration, and availability of resources, as well as a suite of practices designed to improve these factors, thereby positively impacting productivity [26].

According to the study, several essential practices have been identified as enhancing DevX in ways that positively affect productivity. These include minimizing interruptions, improving team collaboration, and ensuring a stable, supportive technical environment. For productivity evaluation, understanding the status of these DevX factors is crucial. Low indicators in DevX metrics may suggest the need to implement specific DevX practices, which can enhance team satisfaction, reduce inefficiencies, and ultimately boost overall productivity.

From the work of Razzaq et al. we extracted and categorized a list of measurable DevX metrics, organizing them by applicability and ease of collection. These metrics, and their categorization, provide a structured approach to incorporating DevX factors into our performance measurement framework. In cases where specific DevX metrics do not meet expectations, targeted DevX practices can be used to address the deficiencies, thereby aligning DevX with data-driven performance goals.[26]

#### Issues in Project Estimation

Project estimation is a complex process prone to significant errors. Many organizations depend on data that may be outdated or poorly aligned with the context of the current project. For example, relying on historical data or static tools like Gantt charts can lead to inaccurate assessments, especially when the new project significantly differs from previous ones. Models that utilize methods such as story points or task count statistics offer some predictive capabilities regarding project volume and complexity. However, these approaches often fail when the underlying data is misaligned with the unique requirements of the project. Improving the estimation process demands careful adaptation to specific project contexts rather than a one-size-fits-all methodology. [22]

Another popular method, COCOMO 2, provides a more structured approach to project estimation but comes with its own set of limitations. Specifically, COCOMO 2 struggles with accurately reflecting team dynamics, work culture, and atmosphere. It also uses a broad set of parameters, some of which may be unclear or difficult to quantify. The rigid structure of models like COCOMO 2 can lead to inaccuracies, particularly in cases where human factors like satisfaction and team cohesion play significant roles in project outcomes. [36]

Techniques for estimating efforts are divided into non-algorithmic and algorithmic, only some of each group are described above. For example, the methods using story points as an indicator are based on expert assessment and are non-algorithmic, in turn COCOMO 2 is based on a clear algorithm with mathematical equations requiring specific quantitative data and coefficients. [5, 22]

In this article, we will discuss the pros and cons of each approach, and outline a balanced strategy that will allow you to select relevant factors, indicators, an evaluation model or a hybrid of several models to achieve adequate results of estimating project efforts.

## Methodology and Design

#### A Correct Approach to Productivity and Project Estimation

## Methodology (WIP)

This study employs a structured and multi-phase methodological approach to investigate the relationship between software development productivity metrics and project estimation accuracy. By combining theoretical exploration, empirical data collection, and prototype testing, the research seeks to advance understanding in this domain and provide practical tools for improving estimation practices.

### Research Approach

The research follows an exploratory and applied approach, integrating quantitative methods. The methodology is informed by the SPACE framework (Satisfaction, Performance, Activity, Collaboration, Efficiency), which emphasizes the multifaceted nature of productivity. The study is structured into three sequential phases: metric identification, data analysis, and tool development and validation.

### Phase 1: Identification and Selection of Metrics

The first phase focused on the systematic identification of relevant productivity and estimation metrics. This was achieved through:

- **Literature Review**: An extensive review of academic and industry literature was conducted to collate existing knowledge on software productivity metrics, estimation models, and their applications. Key sources included studies on developer productivity frameworks, such as SPACE, and empirical analyses of productivity indicators (e.g., churn rate, task completion rates, and satisfaction metrics). 
- **Framework Adoption**: The SPACE framework was selected as the foundational lens, ensuring that the metrics encompass diverse dimensions such as developer satisfaction, efficiency, and team dynamics.
- **Criteria for Metric Selection**: Metrics were evaluated based on their relevance, reliability, and applicability to modern software development practices. This evaluation considered both traditional metrics (e.g., lines of code, churn) and multidimensional metrics (e.g., team collaboration and task complexity).

### Phase 2: Data Collection and Analysis

The second phase involved the systematic collection and analysis of data to evaluate the relationships between productivity metrics and project outcomes. 

**Quantitative Data** Extracted from project management and version control systems (e.g., Jira, Git) to include task completion rates, churn rates, and story point estimates. Quantitative data were programmatically extracted using APIs and processed to ensure consistency.

#### Analytical Methods
Statistical techniques, including correlation and regression analysis, were employed to identify patterns and relationships between metrics and project outcomes. Predictive models were developed to assess the impact of specific productivity factors on project timelines and budgets.

### Phase 3: Tool Development and Validation

In the final phase, a prototype tool was developed to operationalize the findings and validate their practical utility.

#### Tool Design
- The tool integrates the selected productivity metrics into an interactive dashboard, enabling real-time tracking of individual and team performance.
- Predictive modules were implemented to estimate project timelines, budgets, and potential risks based on collected data.
- The tool leverages visualization techniques to highlight key insights, such as deviations in task completion rates or emerging risks of burnout.

#### Real-World Validation
- The prototype was deployed within a software development company for empirical testing.
- Validation focused on the tool’s capacity to identify productivity trends, highlight estimation inaccuracies, and support managerial decision-making.

### Ethical Considerations

Ethical rigor was maintained throughout the study. All data were not anonymized to do not care about participant confidentiality. The tool’s deployment was accompanied by transparent communication with all stakeholders.


## Results (TODO)

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