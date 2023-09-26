# Wreck_it-_relph_tech_spotlight
Assumptions Made:
Request Rate per Month:
  Sample Request Rate per Month: 10 million API requests per month.
  Peak Load: 1 million API requests per day during peak hours.
High Availability and Redundancy:
  Assume hardware failures and network issues can occur.
            Target Recovery Time: Aim for a recovery time of under 15 minutes.
Security and Authentication:
  Role-based access control (RBAC) for queue access.
  Access control for various user roles and permissions.
Service Level Objectives (SLOs):
  Aim for a 99.99% uptime.
  Response times should be under 100 milliseconds for most requests.
Compliance and Data Privacy:
  Compliance with GDPR and other relevant data privacy regulations.
  Data anonymization and encryption in transit and at rest.
Effectiveness of Glassbox and LLMs:
  Assuming Glasbox Service is effectively able to capture user’s interaction journey
  Assuming LLMs are free from hallucinations.



  Data Collection Services (Capturing User’s navigation Journey)
GlassBox- Service

Session Recording and Interaction Analysis:
Page Views,Navigation and Form Interactions
Glassbox records how users navigate the website, including the pages they visit and the sequence of actions they perform,capture how users interact with various forms, including drop-down selections, radio buttons, or checkboxes. This data can indicate user preferences and potentially infer demographic details
Event Tracking and Conversion Funnels:
User Actions and Conversions:
Utilize Glassbox to track important user actions such as clicks on "Apply for Credit Card" or "Change Product". Analyzing conversion funnels can provide insights into the effectiveness of these features and potentially the user's intent or preferences or even dropout Journey
Behavioral Patterns and Preferences:
Mouse Movements and Hover Behavior:
Glassbox records mouse movements and hover actions. Analyzing these patterns can provide insights into the areas of interest or potential confusion, indirectly indicating user engagement and preferences.


Integrating Ml Models and LLMs with data (Recommendation Services)
Behavioral Analysis:
User Segmentation:
Utilize clustering algorithms (e.g., K-means) to segment users based on their interaction patterns captured by Glassbox. This segmentation helps in understanding different user behaviors and preferences.
Personalized Recommendations:
Collaborative Filtering:
Implement collaborative filtering algorithms to provide personalized recommendations based on user behavior, preferences, and similarities to other users.
Content-Based Filtering:
Utilize content-based filtering to recommend products or services to users based on the content they interacted with during their Glassbox sessions.


Proposed Technology Stack and framework
Glassbox: For data capturing via user’s interactions on the client’s side.
Recommendation and Segmentation Service: A django application 
LLM Chatbot: Python Application, Llama-2 as LLm and Pinecone as vectorDb
Database:
User Profile Database:
Stores user profiles, including demographic information.
Technologies: MongoDB, PostgreSQL.
Behavioral Data Database:
Stores user behavior data captured by Glassbox.
Technologies: Cassandra for scalability.
Data Lake:
Description: Centralized repository for storing structured and unstructured data, including Glassbox interactions and other data sources.
Technologies: Amazon S3, Google Cloud Storage


Non Functional Aspects
    ( Scalability, Security and Reliability)
Non Functional Assests

Scalability using Sharding and Partitioning:
   - Sharding: Shard the database horizontally to distribute data across multiple servers, ensuring horizontal scalability. For example, shard customer data by geographical location.
   - Partitioning: Apply data partitioning within each shard, e.g., partitioning user behavior logs by date or session.



Reliability Aspect:
   - Ensuring high availability through redundancy and failover mechanisms for critical components.
   - Implementing automated monitoring and alerting to detect and respond to issues promptly.

Security:
   - Implementing strict access controls, encryption in transit and at rest, and regular security audits.
   - Using OAuth or similar protocols for user authentication and authorization.
   - Monitoring for unusual activity and employ intrusion detection systems.

Key Advantages of the solution

Improved UI/UX.
Personalized recommendations.
Graphical view of analytics of user Journey.
Autofill feature for the form
Chatbot interactions 
Feedback analysis



Deployment Architecture and Security

Deployment Architecture
Implementing a load balancer at the front end to distribute incoming requests evenly across multiple instances of the API Gateway, ensuring high availability and load distribution.
Implementing auto-scaling to adjust the number of instances based on traffic and resource utilization.
Ensuring that the queue system can handle the expected message volumes and offers data replication for fault tolerance.
Considering deploying the system in multiple data centers or regions for disaster recovery and to serve customers in different geographic areas.


Security


Implementing security services such as firewalls, intrusion detection systems, and web application firewalls to protect against external threats.
Ensuring compliance with data privacy regulations (e.g., GDPR) by implementing data anonymization, access controls, and user consent management.





