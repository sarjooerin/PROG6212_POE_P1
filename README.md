Documentation: Project Planning and Prototype Development 

 

1. Design Decisions and Justifications  

To solve the difficulties Independent Contractor (IC) lecturers encountered in filing and monitoring monthly claims, the Contract Monthly Claim System (CMCS) was created. Accuracy, responsibility, and usability are given top priority in the design. The design team determined that three primary layers were required after analyzing the requirements: 

1. Database Layer: to guarantee safe, standardized data storage.  

2. Application Layer: to process and implement business logic (e.g., role-based access, claim approval).  

3. User Interface Layer (GUI): to give managers, coordinators, and lecturers an easy-to-use, clear experience. 

This tiered strategy adheres to best practices for system development, especially for.NET Core MVC applications, where separating concerns improves scalability and maintainability.  

Among the main factors influencing these design decisions were: 

Data Integrity: Clear primary and foreign keys must be used to connect claims, lecturers, and approvals. 

Security: Sensitive data is protected by user authentication (password and username with hashed storage).  

User Experience: Managers can access a review dashboard, and lecturers can submit claims with the help of clear GUI wireframes.  

Scalability: Future features like automated alerts and sophisticated reporting are anticipated by the system. 

 

2. Structure of Databases  

UML Class Diagrams were used in the database's design to represent entities, attributes, and relationships. Six essential entities are included in the final structure: 

1. Lecturer: contains the lecturer's information (ID, name, email, department, and contact).  

2. Claim: denotes every monthly claim, associated with a claim status and a lecturer. Month, Year, Hours Worked, Rate, Amount, and Date Submitted are all included.  

3. Document: ensures transparency in claims by supporting file uploads (proof of hours, supporting documents).  

4. Approval: Documents the actions taken by Coordinators or Managers during claim reviews, including comments and approval dates.  

5. Claim Status: For workflow clarity, status codes (such as Pending, Approved, and Rejected) are defined.  

6. The user authenticates the system using their roles (Manager, Coordinator, Lecturer). 

Relationships were well-defined: 

A lecturer makes a lot of claims.  

There may be more than one supporting document for a claim.  

Although a claim may go through several approval records, it only has one claim status. 

If a user is a coordinator or manager, they can approve a lot of claims.  

This supports accurate reporting and secure workflows while ensuring normalization (at least 3NF) and removing redundancy. 

 

3. Layout of the Graphical User Interface (GUI) 

 Role-based access and simplicity are key components of the GUI design. To illustrate the intended layouts, wireframes were created: 

 1. Lecturer Login Page: a secure form that needs a password and username. Two-factor authentication and password recovery are possible future additions. 

 2. Submit Monthly Claim Page: Instructors enter their hourly rate, hours worked, and any supporting documentation. The claim is saved and linked to the lecturer via a submission button. 

 3. The Lecturer Dashboard (My Claims) shows the date, amount, rate, hours worked, and status of claims. This aids instructors in keeping track of their submissions. 

 4. The Coordinator & Manager Dashboard shows all of the unresolved claims. Along with action buttons (Approve/Reject), each entry shows the lecturer's information, the date of submission, and the calculated amount. 

The layout adheres to usability heuristics, which include consistent styling, minimal data entry, and clear labeling. Without training, this design methodology guarantees that novice users can comprehend system workflows with ease. 

 

4. Premises and Limitations  

When designing the system, a number of assumptions were made: 

An administrator has created valid system credentials for each lecturer.  

Unless administrators update them, hourly rates are preset and constant across claims. 

Web-based claims can be supported by stable institutional infrastructure and internet access.  

At least one supporting document (evidence of work) must always be included with claims.  

Among the constraints taken into account are:  

Time: Only the submission and approval of core claims are the focus of the prototype phase. Other modules (like email notifications and analytics dashboards) are outside the current purview.  

Technical: Restricted to the SQL database tools and.NET Core MVC as specified in the module.  

Security: Although advanced encryption (such as TLS/SSL and multi-factor authentication) is not yet fully implemented at the prototype stage, passwords will be hashed. 

 

5. Justification for Design Choices  

Industry best practices are reflected in the selected architecture: 

Normalization minimizes redundancy and guarantees efficiency.  

Referential integrity between entities is ensured by foreign key relationships.  

By concealing unnecessary functionality, role-based GUI layouts enhance the user experience.  

Agile prototyping is in line with wireframes, which give stakeholders early visibility prior to complete implementation.  

Because of its modular design, the system can be improved in the future without affecting its essential features. This iterative process is similar to real-world software projects in that early prototypes develop over several sprints into fully functional systems. 

 

6. Final thoughts  

Requirements analysis, UML-driven database design, and GUI prototyping are all integrated in the Contract Monthly Claim System (CMCS) documentation and prototype planning. The design guarantees a strong basis for subsequent implementation by precisely defining entities, relationships, and workflows. While the modular database structure offers accuracy and scalability, the use of role-specific dashboards improves usability. 

In the end, this prototype bridges the gap between theoretical knowledge and real-world application by reflecting both industry relevance and academic requirements. The system has the potential to become a production-ready application that can greatly enhance Independent Contractor lecturers' claim management procedures with additional development. 

