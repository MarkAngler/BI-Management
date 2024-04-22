# White Paper: Evolution of Data Analytics Architecture
#### Mark Angler

## Executive Summary

This document outlines the strategic evolution of a data analytics infrastructure, illustrating the transition from traditional SQL and SSIS servers to a modern, open lakehouse architecture facilitated by Databricks. It captures the thought process, reasoning, and tactical decisions made to address challenges of sustainability, supportability, and rapid development within a growing multinational corporation. Through progressive iterations and strategic pivots, this journey underscores the importance of adaptability, governance, and cost-effectiveness in data management and analytics.

## Introduction

In the quest to establish a robust, scalable, and efficient data analytics framework, our organization embarked on a transformative journey. This journey was marked by initial trials with traditional SQL databases and integration services, through experimentation with various data management solutions, to the eventual adoption of a cutting-edge, open lakehouse architecture. Each phase of this evolution was driven by a clear set of objectives: enhance analytics capabilities, ensure sustainability and supportability, reduce time to delivery, and maintain governance standards.

## Phase 1: Initial Setup with SQL Server and SSIS

The organization's first approach involved setting up a SQL Server and SSIS (SQL Server Integration Services) to kickstart our business analytics. This phase focused on leveraging existing Microsoft ecosystem tools to quickly stand up an analytics backbone. However, within six months, it became evident that this solution fell short in terms of sustainability, supportability, and efficiency—especially for complex SQL operations and the limitations of SSIS's GUI, which proved more restrictive than facilitative.

## Phase 2: Transition to Synapse and Evaluation of Alternatives

The next logical step within our Microsoft-centric environment was to migrate to Azure Synapse Analytics. Despite high expectations, Synapse presented significant challenges in terms of bugs, performance issues, and an overall lack of maturity, leading to its eventual discontinuation by Microsoft.

This pivotal moment necessitated a thorough evaluation of alternative solutions, including Snowflake and Databricks. The prohibitive cost of Snowflake and our adverse experiences with Synapse guided our decision towards Databricks—a platform that promised cost-efficiency, rapid development capabilities, strong governance, and overall technical fit for our needs.

## Phase 3: Managed Power BI Datasets and Stihlanalytics.com

With Databricks as our foundation, we introduced managed Power BI datasets, encompassing comprehensive datamarts for various business domains. This initiative streamlined data validation, eliminated duplication, and optimized in-memory storage, significantly enhancing the Power BI user experience.

The establishment of Stihlanalytics.com, complemented by a dedicated mobile app, marked a further innovation. This one-stop data visualization portal, coupled with programmable features and mobile accessibility, significantly improved data interaction for our field staff and general users alike.

## Phase 4: Empowering Users with Open Lakehouse Architecture

Recognizing the limitations of traditional data mesh approaches, we devised a unique concept allowing users to engage directly with Databricks for exploratory analysis in a governed environment. This approach minimized the need for numerous Databricks workspaces while maximizing flexibility and governance. This model, initially without a market name, has since been recognized as a pioneering form of the "open lakehouse" architecture.

## Phase 5: Integration of Natural Language Processing

The integration of large open-source language models for natural language processing brought our analytics capabilities to the next level. By allowing users to query data using natural language, we significantly lowered the barrier to data access and enhanced decision-making processes.

## Phase 6: Global Implementation and Future Directions

The most recent strategic initiative involves a global rollout of our data analytics framework across multiple regions, leveraging Databricks Unity Catalog for federated connections. This strategy aims to maintain compliance with local regulations while fostering global collaboration and knowledge sharing.

## Conclusion

Our journey from traditional SQL databases to an innovative open lakehouse architecture illustrates a continuous pursuit of excellence in data analytics. Through iterative learning and strategic adaptation, we have established a scalable, efficient, and governance-oriented analytics framework that serves as a cornerstone for our global operations. The evolution of our data analytics architecture is a testament to our commitment to leveraging cutting-edge technology to drive business intelligence and operational efficiency across all levels of the organization.

## Analysis of Evolutionary Phases: Successes and Setbacks

### Phase 1: Initial SQL Server and SSIS Deployment

#### What Worked:
- **Rapid Deployment:** Quick setup allowed for an immediate start on business analytics efforts, demonstrating the agility of our IT infrastructure.
    - Azure SQL Server
    - SSIS on Prem

- **Familiarity:** Utilizing the well-known Microsoft ecosystem facilitated initial adoption and integration with existing tools and processes.

#### What Didn't Work:
- **Scalability Issues:** As the complexity and size of our analytics needs grew, the SQL Server struggled to scale effectively.

- **Limited Flexibility:** The rigid structure of SSIS and complexity of SQL coding for advanced analytics tasks became significant hindrances.
    - Low code / no code is more inhibiting than anything else.
    - SQL lacks programming constructs necessary for building large-scale, sustainable & supportable, projects.

### Phase 2: Transition to Azure Synapse

#### What Worked:
- **Attempt at Modernization:** The move represented a forward-thinking attempt to leverage newer, cloud-based analytics solutions.

#### What Didn't Work:
- **Performance and Bugs:** Encountered significant performance issues and bugs, affecting reliability.

### Phase 3: Adoption of Databricks

#### What Worked:
- **Flexibility and Rapid Development:** Databricks provided the necessary agility and ease of use for both developers and data scientists, significantly reducing development time.

- **Cost-Effectiveness:** Compared to other solutions, Databricks offered a more affordable option without compromising on capabilities.

- **Strong Governance:** Databricks’ governance features ensure data security and compliance, aligning with our organizational needs.

#### What Didn't Work:
- **Naming Conventions and Catalog Structure:** All of our tables were prefixed with the name of the source, and suffixed by bz, sr, or gd. Gold tables were placed in a schema dedicated to the project or application it was for, and bz & sr went in the default schema. This had room for improvement. During the migration to Unity Catalog, we prefixed the gold schemas with dm for datamart, and placed bz and silver tables in a schema named after their source. All other conventions remained the same. 

### Phase 4: Managed Power BI Datasets and Stihlanalytics.com

#### What Worked:
- **Comprehensive Data Models:** Managed Power BI datasets provided a solid foundation for reliable, easy to build dashboards.
- **User Accessibility:** Stihlanalytics.com and its mobile app significantly improved data accessibility and usability for non-technical users.

#### What Didn't Work:
- **Resource Intensiveness:** Ensuring comprehensive data coverage and maintaining performance standards required substantial resources and ongoing management.
    - **How we Addressed:** Attempted to migrate to AtScale semantic layer, which would free us up from in memory storage constraints. Without memory constraints, we would be able to provide the most granular form of data, addressing current and future analytics requirements. Riddled with bugs, we decided not to adopt AtScale and instead remain with PowerBI import datasets, but continue to pursue the strategy of zero aggregation. The trade off of not constantly having to adjust aggregations based on the same data but different requirements significantly outweighed the additional in memory storage costs that came with providing the additional data.
        - **What's Next:** Wait for PBI Fabric direct lake functionality to mature, then pilot.

### Phase 5: Empowering Users with Open Lakehouse Architecture

#### What Worked:
- **Innovative Data Architecture:** The open lakehouse architecture enabled a flexible, scalable platform for handling diverse data types and analytics workloads.
- **User Empowerment:** Providing users with tools for exploratory analysis fostered a culture of innovation and self-service analytics.

#### What Didn't Work:
- **Time:** Users were not willing to commit the time necessary to learn and analyze their data; they wanted an ‘easy button.’

### Phase 6: Integration of Natural Language Processing (The Easy Button)

#### What Worked:
- **Enhanced User Experience:** The integration of NLP technology improved data discoverability and interaction, making analytics more accessible.

- **Innovative Analytics Approach:** Leveraging open-source language models placed us at the forefront of adopting AI for analytics.

#### What Didn't Work:
- **Complex Integration:** Seamlessly integrating NLP with documents requires experimentation, adjusting, and exploration of advanced techniques.

### Conclusion

Throughout each phase of our analytics evolution, we've encountered a mix of successes and setbacks. These experiences have not only shaped our current state but have also provided valuable lessons that inform our future directions. By continually learning from both our achievements and challenges, we remain committed to driving innovation, efficiency, and growth within our data analytics capabilities.

## Philosophy and Approach to Leadership

### Principle 1: Addressing the Slowest Moving Part

In leading our data analytics evolution, a critical focus has been on identifying and addressing the slowest moving part of our processes and technology stack. This approach ensures that no component becomes a bottleneck, thus optimizing overall performance and efficiency. By prioritizing these areas, we implement targeted improvements that enhance the system's functionality and reliability, ensuring that each element contributes positively to our collective goals.

### Principle 2: Building with Sustainability, Supportability, and Adaptability

Our strategic decisions are underpinned by a commitment to sustainability, supportability, and adaptability. This philosophy guides our choice of technologies, design of systems, and deployment of resources. We build for the future, ensuring that our solutions not only meet current needs but are also capable of evolving in response to future demands. This approach minimizes the need for significant overhauls, thereby preserving our investments and ensuring continuity of operations.

### Principle 3: Innovation and Embracing Failures

Innovation is at the heart of our strategy, driven by a belief in experimenting boldly and learning from every outcome. We cultivate an environment where failures are seen as stepping stones to success, encouraging our teams to push the boundaries of what's possible. This mindset has allowed us to pioneer solutions like the open lakehouse architecture, setting new standards in the industry. By fostering a culture that values creativity and continuous improvement, we stay ahead of technological advancements and industry trends.

### Principle 4: Alignment with Business Objectives

Every initiative and project is closely aligned with our overarching business objectives. This alignment ensures that our efforts contribute directly to the organization's growth, efficiency, and competitive edge. By maintaining a clear focus on these goals, we ensure that our technology and data strategies drive tangible business outcomes, maximizing the value of our investments and efforts.

### Principle 5: Elevating and Respecting Employees

Above all, our approach is people-centric, recognizing that our employees are the foundation of our success. We are committed to elevating and respecting every team member, fostering a culture of inclusion, empowerment, and recognition. This philosophy not only enriches our work environment but also inspires our employees to achieve their best, contributing to our collective achievements. Through professional development opportunities, open communication channels, and a supportive work culture, we ensure that our team members grow alongside the organization.

### Principle 6: Empowering Business Users: A Philosophy of Self-Service Analytics

In today’s fast-paced business environment, the ability to quickly access, interpret, and act on data is not just an advantage—it’s a necessity. At the core of our approach to data analytics is a fundamental belief: empowering business users to build their own dashboards and analytics is paramount. This philosophy is grounded in the conviction that those closest to the business processes are best positioned to derive insights from the data, provided they have the right tools and access. Our commitment to this principle is reflected in our strategies and systems, designed to provide users the right data, when they need it, and how they need it.

  - #### Democratizing Data: ####
    We envision a democratized data environment where every user has the power to query, visualize, and analyze data without depending on specialized IT resources. This empowerment accelerates decision-making, fosters innovation, and enhances responsiveness to market changes. By equipping our business users with intuitive tools and comprehensive training, we aim to break down the barriers between data and decision-makers.

  - #### Ensuring Data Availability and Integrity: ####
    At the heart of our self-service analytics approach is the commitment to provide accurate, timely, and relevant data. This involves creating a robust data governance framework that ensures data quality, security, and compliance, while also making data easily accessible. Managed data lakes and data warehouses, along with effective metadata management practices, ensure that users can trust and rely on the data they access.

  - #### Tailored Analytics Experience: ####
    Recognizing the diverse needs of our users, we prioritize the customization and flexibility of our analytics tools. Whether through drag-and-drop interfaces for building dashboards or through more advanced analytical models for deeper insights, our aim is to cater to the spectrum of analytics proficiency within our organization. This tailored approach means providing different access levels and tools that match the users’ expertise, ensuring that analytics is inclusive and productive for everyone.

  - #### Fostering a Data-Driven Culture: ####
    Empowering users goes beyond providing tools and data; it’s about cultivating a data-driven culture. This entails continuous education on the value of data-driven decision-making, sharing success stories within the organization, and encouraging a mindset of experimentation and curiosity. We believe in creating a community around data, where users feel supported in their analytics journey and are motivated to explore new ways to leverage data in their roles.

  - #### Continuous Feedback and Evolution: ####
    Our philosophy is not static; it evolves in response to user feedback, technological advancements, and changing business needs. We maintain an agile approach to our analytics platform, regularly updating our tools and practices based on user experiences and emerging trends. This commitment to continuous improvement ensures that our users are always equipped with the best possible solutions to meet their analytics needs.

  - #### Conclusion: ####
    Empowering business users to create their own dashboards and analytics is more than a strategic choice; it’s a reflection of our belief in the power of data to transform decisions, operations, and ultimately, outcomes. By providing the right data, in the right way, at the right time, we enable our users to unlock the full potential of analytics, driving innovation and efficiency across the organization. Our journey towards a more empowered and data-driven workforce is ongoing, fueled by our dedication to democratizing data access and fostering a culture that values and leverages data at every opportunity.


### Conclusion

Our leadership approach is characterized by a strategic focus on the system's efficiency, a commitment to sustainable and adaptable solutions, an innovative mindset that embraces learning opportunities, alignment with our business goals, and, most importantly, a profound respect for our employees. By adhering to these principles, we have not only navigated the challenges of evolving our data analytics capabilities but also cultivated a robust, forward-thinking organization poised for continued success in the dynamic landscape of data analytics.





