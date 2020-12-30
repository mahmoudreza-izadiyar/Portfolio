# School-Management-System-CS50-Final-Project




Whole concept of this application:

In this application I have design a system for doing financial stuff for schools. we can add students , staffs, classes and also terms. for each parameters i have design separate application for each object. finance have its own application. we can arrange invoice and manage the price of each class for each student. 

in staff application we can add teachers as a staff, then i connect table of teachers to class and students, then we can use information of staff when we want to define a class and even when we need to have invoice. 

students application helps us to add new students and add them to their. we can add some money to each studnets account and clear their invoice with that money. each student has many row in the their tables in backend. name , semester, ID number and parents information. 
in the interface of student tab you can see the current session and term in top of the page, and if you click on it, you will drive to the new page that lets you to edit the session and date to edit the information of that date.

actually we can handle all the information about classes(semesters and terms, and teachers for each class) , student (money , calsses, and their teachers), staff(add new teacher), and finally produce invoice and handle all invoices for students in one place. we can handel all these parameter and relations between them through tables in backend. 


This project has four applications inside of itself: 


# 1-Finance App: 
    in this application we have 3 models (tabales) to store data and make this application functional that we can see it in model.py of this application. and also we have some functions in views.py 
        in models we have:
       -INVOICE  : this table has four foreign keys student model, session of calss , academic terms and all classes of the school, to be able to make an invoice with the relations between all these tables. 
            - BALANCE: this function will take all the payment have been paid and all payments needs to be pay and find the balance. 
            - PAYABLE INVOICE: this function will show the user how many invoice is there that need to be paid. 
            - TOTAL PAYABLE INVOICE : this function can shoe us how many invoice is there. invoices form previous terms and current term, all together, has been shown in this model. 
            - RECEIPTS : with this function we will have the number of receipts that each student has been paid. 
            - INVOICE ITEM: this object has three parts, a foreign key to invoice table , a description of each invoice, and the amount of each invoice. 
             - RECEIPT: with this model we have receipt object that show us which invoice is it for, amount and the date of paid , and some comment if we need to have. 
               this is the core of this application and all the functions and tables come together here to make invoices and build receipts. this is the crossroad of this app. 
    and  views.py use "GENERIC EDIT VIEW" for each function. user can create a new invoice in invoice tab, by filling the form. but as you can see this form is a selective ( Optional ), and all options comes from the database and models. that i represent above. 
    form has two parts, let and right. in the left side we can insert the information that we already have in our database, we can chose the information that we already insert in our students, term and class. in the right side we can put information about money and fee. 
    *** Complexity *** : in this page we have all information of our school together in one place, because of complexity of models and tables. 
    ***.Humanize: i install this app in django project to convert numbers in a better way, and then i've use it in my template to show me better numbers.
    ***.CreateView, UpdateView, DeleteView: with these function i can create views in functions. 

# 2- Result App:
    this application helps us to create a result for each students, edit result and also have all results in one page, we have only one model for this app that contains four foreign key to use another models, and three function. 
    -Create result : 
       to creating results , we have function to helps us to select each student and choose each class that we need to see students score of, and after that it will add to result summery. we can update the result by the tap in the menu and also we can see all the results in one page. 
    -Update result :
        in the field of Update results, we can edit the results before save. after that, when we are confident about our information, we can save the information and then we can see all result of each student in a separate field in the last field.
    -View Results:
        This part of application will show us all the results that we accepted before.
        in this page, we have grade too. this grade has been generated automaticaly in A , B , C and D.

# 3-Student App:  
    MODEL:
    this application, has only one model, that handel our students information inside of itself, each student has active and inactive status, and students are separated bye gender. all the personal information comes into this model, also this model can accept the csv file for each student and stor data in this way for students. 
    PAGINATION:
    in the UI of student in the app, i use pagination for my web application. you can choose the number of student that you like to shown in each page in the top of the page. 
    SEARCH:
    you can search students by each column that you like to reach each person. 
    DOWNLOAD CSV:
    you can download the csv file by going to url "downloadcsv/". it will gives you the csv file of the students. 

# 4-Staff App:
    staff application contain to models to handle the information for each staff as a teacher and also to receive the csv files form the local computer. 
    model helps us to store the information of each staff by status, gender, and personal information such as name, date of birth and address and ... . 
    views.py of this application contain 5 functions. i mixed SuccessMessageMixin, CreateView, UpdateView,DeleteView, together to reach a better interface and create some view       that can work with pre-build application in django. 
    at fist you can see the list of staff, you go to address ""staffs/staff_detail.html"" to see the details of each staff there in a single page. 
    in each field, you can edit pre-saved information by clicking on a pen icon, then you can update the information. 
    and you can delete each staff that you like, by clicking on cross sign in the top and right of the card for each staff. 
    this app lets you to create new staff and edit that staff and even delete that person. in the future you can use that name to create a class and terms.

To Login plz use :
Username: admin
password: admin123





