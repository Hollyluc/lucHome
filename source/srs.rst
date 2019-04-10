Software Requirements Specification For Gene Expression Scatter Plot
=====================================================================
1. Introduction
----------------
We have to build a web application which can generate a gene expression scatter plot given relevant JSON files as input.  This document is intent to specify a set of requirements for our project. 

1.1. Purpose
-------------
Generate a scatter plot based on two gene expression level samples to observe the expression level of two genes in the different experimental condition. It can help biologists to analyze experimental data.

1.2. Overview
-------------
The remainder of the document is organized as follows: first, we introduce the overall description. Then we analyze the product requirements. Finally, we analyze the constrains and some change cases of the software.

1.3. Overall Description   
------------------------- 

1.3.1. User Characteristics 
****************************

 * clients: Biologists who are using web application to processing experimental data.  
                              
 * web maintainers: Computer technicians skilled in python and github.
 
1.3.2. Product Features
****************************
 
 The web application has a simple homepage with two buttons [Upload] and [Reset]. Our scientists upload two sample files of the expression levels of two genes G1 and G2 and the details of their conditions. Accepting these files, the software will return a scatter plot of gene expression correlation whose X-axis is G1 and Y-axis is G2. If an invalid file is given, the web application returns a page informing the user to provide the correct format.

1.4. Terminologies
------------------
In order to introduce the project and specify the requirements in detail, this section will explain some terminologies so that the clients and maintainers have better understanding of the content of the project.
 *JavaScript Object Notation(json)* - A lightweight data interchange format based on the JavaScript language .

 *Invalid file* - The document type is not json and the contents of the files can not represent the level of gene expression.
 
2. Functional Requirements
---------------------------

2.1. Input
------------------

A valid submitted gene expression file has the following format :
  * Users have to submit three json files.
  * For the file format, the file have to be json file.
  * The file should contain the condition of gene and gene expreession level value for each group condition. (e.g."R0001000014601":1.38128181929635). The condition names in both files must match. The details of the condition should be included in the information file.

2.2. Output(Data Analyzing)
---------------------------

The web application displays a scatter plot when given a gene expression file.

2.2.1. Plot Analyzing
---------------------

====================  ==========  ==========
      RQ1                RA1       PRIORITY
====================  ==========  ==========
 
====================  ==========  ==========

The scatter plots displays gene correlations.The X-axis is the expression level of G1 and Y-axis is the expression level of  G2.We use different colors to represent different experiments under different conditions.If the expression level of G2 increases with the increase of the expression level of G1, it means that G1 promotes the expression of G2; if it decreases, it inhibits the expression of G2.If the distribution of points of the same color is dense and the correlation coefficient is high, it means that the two genes are highly correlated; if the distribution of points of the same color is scattered, it means that their correlation is low.When our mouse touches some of these dots, we can get the  related information of the dot.

Our scatter plot model is as follows : 

.. image:: https://raw.githubusercontent.com/Hollyluc/lucHome/master/source/spot.png
      

3. Non-functional Requirements
-------------------------------
3.1. Response Time
-------------------
Since the users might have a lot of data to process,so considering the reasons for improving the user experience,this web application should be really quickly.After the discussion, we have decided the limit of response time, it should less than 5 seconds for the most using cases.

3.2. Aesthetic Aspects
----------------------
Because the scatter plot will display many spots, the interface should be as simple as possible and make the scatter plot more distinct. It will be helpful for users to analyze the data.

3.3. Confidentiality Policy
---------------------------
This project is a public web application, it is important to ensure data security. Especially for some biologist, they attach great importance to experimental data. So this application must keep experimental data confidential and the data must not be allowed to read without agreement of the owner.

4. Constraints
----------------------
 In order to make this web application more user oriented and improve its own executable capability. We also need to add some constraints to make it more durable and high-quality to use

4.1. Browser Compatibility
--------------------------
This web application will be used by many kinds of people, so it has to have a cross platform compatibility to satisfy various users. It means the application should be accessible through Firefox, Chrome, Safari and so on.

4.2. Space Complexity
----------------------
The spatial complexity of a program is the amount of memory needed to run a program. The size of the application should be about 1GB. It is necessary to limit the memory which is used for data processing so that  to make sure the system work in a proper way.

4.3. Budget
----------------------
Budget less than 10,000 USD.

4.4. System Downtime
----------------------
System downtime should be less than 30 minutes per year for a better user experience.

5. Change Cases
----------------------
(1)	In the future, other types of files can be supported as input. Such as excel files.
(2)	The application could generate an analysis result document and support download.
(3)	For some files with large amount of data, the program needs a long processing time. So it¡¯s critical for us to make the response time of browser shorter. 
(4)	More functions will be provided from the application.

6. Milestones
----------------------
1. Submit SRS for review by 2019-03-27
   
   (To be continued...)

7. Appendices
----------------------
2019-03-24 : The main page is built and the function of user input document is realized.

8. References
----------------------
Readthedocs:  https://readthedocs.org/

Group Information
----------------------
Group Name:
 Jeril&Holly

Group Member:
 Jiang Jialin(Jeril 201732120103) : 1850424414@qq.com

 Wang Hairong(Holly 201732120105) : 1012635788@qq.com 
