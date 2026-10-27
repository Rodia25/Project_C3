# Project_C3
import java.util.Scanner;
public class C3
{

     static void main()
    {
        Student student = new Student();
        Login login = new Login();
        //Messenger messenger = new Messenger();
        Scanner scnr = new Scanner(System.in);
        String response;    //Check whether account for user already exists
        String username, newUser; // for existing and new user
        String password, newPass;
        String major = "",country = "",year = " ";

        System.out.println("Do you already have a C3 account:");
        response = scnr.next();

        if(response.equalsIgnoreCase("yes"))
        {
            login.setUsername("Bill123");
            System.out.println();
            login.setPassword("12345678");
            System.out.println();
            username = login.getUsername();
            password = login.getPassword();
            System.out.print("Username: " + username + "\n");//prints out username
            System.out.print("Password: " + password + "\n");//and password

        }
        else if (response.equalsIgnoreCase("no"))
        {
            //New account setup
            //login.setNewUsername("Bill123");
            System.out.println();
            newUser = login.getNewUsername();
            //login.setNewPassword("12345678");
            System.out.println();
            newPass = login.getNewPassword();
            System.out.println("New Username: " + newUser);//prints out new username
            System.out.println("New password: " + newPass);//and password

            username = newUser;
            //Biography info
            System.out.print("Major: "); //Asks for minor
            major = scnr.next();
            student.setMajor(major);
            System.out.print("Country of origin: "); //Asks for country of origin
            country = scnr.next();
            student.setCountry(country);
            System.out.print("Academic Year: ");//Asks for Academic year (freshman, senior,etc.)
            year = scnr.next();
            student.setYear(year);
//            System.out.print("First Language: "); //Asks for native language
//            language = scnr.next();
//            student.setLanguage(language);
            student.setUsername(username);
            System.out.println();
            System.out.println(student.toString());

            //Messaging on the platform


        }
    }
