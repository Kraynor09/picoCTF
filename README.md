# picoCTF
PicoCTF

WebExploitaiton

Insp3tor 

To complete this ctf, you are required to look into the code for the site, start by opeing inspect element and examine the html page, here you should find 1 0f the string. You should aslo notice that the site uses Javascript and css. In the Javascript file you will find the 2/3 of the flag, and in the css file you should find the last part of the string.
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}

client-side

Firstly, remmber the name of this certain CTF challange, this will be usefull later on, open the inspect element and you should see that the site uses Javascript to verify the password, it does this by checking each part of the user input to see if it is what it has stored in the Javascript, if it is it gives the user a alert promting the user that they have logged in. If you examine each part of the stored text that it verifys it self with, you may strat to guess what it says.


picoCTF{no_clients_plz_b706c5}


Logon 


Where are the robots? 


Very simple CTF, firstly start of by trying to find sercert files on the webserver, this could be done by entering things that may relate to the webpage for exmaple, /robots.txt. After finding this, you should notice the "Disallow: /1bb4c.html" this shows to the user that the web developers are not wanting there clietns to go to this html page. When you open the html page you get the flag.

picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}


Web Gauntlet 
In the challange you are required to login as "admin"

part 1

First i started of by testing how the login page works, i have noticed that it takes the user input from the "username" and "password" feild and places each into a sql qeury, that sql qeury is then displayed to the user. This could be very usefull for a attack, for exmaple, we now know were each codentail is stored, the users usernames are stored in the "users" table and the passwords are stored in the same table.
lets take a look at the other url that we have been given, here we get "round1: or", or in sql is used to join  to booleans togther, to return a true or false value. This means that we can not use a or statment in our query. If you think of the standered sql query that we can input "SELECT  * FROM users WHERE username = 'admin' AND password= 'admin' " We need to make it so that the "AND password = 'admin'" is not included in out statment, we do this by entering the username 'admin' followed by a ';--' what this does is it declears that it is the end of the sql statment. So the stament would now look somthing like this "SELECT * FROM users WHERE username= 'admin';--". If we take the last part and enter that in our username box, and enter a random password, we then are placed on part2.

part2 
If we go back to the main ctf challange screen we notice the filter.php has been updated with more characters we cant use.
