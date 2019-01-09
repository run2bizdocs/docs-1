title: Business rules  
Description: Business rules define how your business works, and can cover a variety of issues such as your policies, interests, objectives, ethical and social commitments, contractual obligations, strategic decisions, laws and regulations, among others  

#Business rules

Business rules define how your business works, and can cover a variety of issues such as your policies, interests, objectives, ethical and social commitments, contractual obligations, strategic decisions, laws and regulations, among others.  
In Neuro, business rules can be built through the Drools language, by drawing a flow, or through a Script.    

##HOW TO ACCESS  
1.	Access the functionality through navigation in the main menu Neuro → Management → Business Rule.    

##PRECONDITIONS
1.	No applicable.  

##FILTERS
1.	The following filter enables the user to restrict the participation of items in the standard feature listing, making it easier to find the desired items:  
-    Keyword or enter.  

![Screenshot](images/business-rule-filter.png)  
Figure 1 - Business rules search screen  

##ITEMS LIST  
The following cadastral fields are available to the user to facilitate the identification of the desired items in the standard feature listing: Name, Description, Application, Version and Block date.  

![Screenshot](images/business-rule-item.png)  
Figure 2 - Business rules listing screen

##FILLING IN THE REGISTRATION FIELDS  
1. To edit a created item, select the item you want, click Edit, make changes, and click Save.  
2. To create a new business rule, click the New button;  
3. To remove a created item, select the item you want, click  on the Edit → Remove and confirm the deletion.  
4. The business rules you enter by default are created locked. This means that the rule will not be used unless you unlock it. To unlock the rule, select the desired item, and click the Unlock option on the top menu. A Business Rule can be used in a form, within a business object, in a business process or in a flow;  
5. Further information regarding the use of a business rule can be found in the Developing Applicantions.  

--------------------  

##CREATING BUSINESS RULES USING DROOLS TYPE  
1. Drools is a set of tools that allow us to separate and reason about the logic and data found within business processes. The two important keywords we have to realize are Logic and Data. Go to https://www.drools.org/ for more information;  
2. To create a business rule using Drools, you must first create the DSL and DSLR through the Neuro → Configuration→ Domain;  
3. After these registrations have been made, access the menu Neuro → Management  → Business rule, Click on the New button. Fill in the fields by entering the  Name, Description, Type (fill in with Drools), and the respective Application that has been registered (Neuro ® Management ®  Application), finally inform Drools DSLR that was registered in the previous step;  
4. In addition, variables that complement business rules may be inserted.  

![Screenshot](images/business-rule-drools.png)  
Figure 3 - Drools business rule registration / editing screen - Basic data tab
