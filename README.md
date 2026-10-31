# Project_C3
import java.util.Scanner;
public class C3
{

     static void main()
    {
        Student student = new Student();
        Login login = new Login();
        Messenger messenger = new Messenger();
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
            System.out.println("Enter new username:");
            newUser = scnr.next();
            login.setNewUsername(newUser);
            System.out.println();
            newUser = login.getNewUsername();
            System.out.println("Enter new password:");
            newPass = scnr.next();
            login.setNewPassword(newPass);
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
            student.getUsername();
            System.out.println();
            System.out.println(student.toString());

            //Messaging on the platform
            System.out.print("Do you want a post a new comment or reply?(type 'comment' or 'reply')");
            response = scnr.next();
            if(response.equalsIgnoreCase("comment"))
            {
                System.out.print(username + ":\n");
                messenger.getPost();
                System.out.print(messenger.getPost());

            } else if (response.equalsIgnoreCase("reply"))
            {
                System.out.println(username + ":\n");
                messenger.getReply();
                System.out.print(messenger.getReply());
            }

        }
    }
}

     import java.util.Scanner;
    public class Student
{
    private String major;   //States user's Major
    private String country; //States user's country of birth
    private String year;    //States year of school
    private String username; //States username of student
   // private String language; //Language user wants to translate to if necassary
    private String input;   //Input of text message
    Scanner scnr = new Scanner(System.in);
    Login login = new Login();
    public void setMajor(String major)
    {
        this.major = major;
    }

    public String getMajor()
    {
        return major;
    }

    public void setCountry(String country)
    {
        this.country = country;

    }

    public String getCountry()
    {
        return country;
    }

    public void setYear(String year)
    {
        this.year = year;

    }

    public String getYear()
    {
        return year;
    }

    public void setUsername(String username)
    {
        this.username = username;
    }

    public String getUsername()
    {
        return username;
    }

//    public void setLanguage(String language)
//    {
//        this.language = language;
//    }
//
//    public String getLanguage()
//    {
//        return language;
//    }

    public void setInput(String input)
    {
        this.input = input;
    }

    public String getInput()
    {
        return input;
    }

    @Override
    public String toString()
    {
      String s = "Major: " + getMajor() +"\nCountry of origin: " + getCountry() + "\nAcademic Year: " + getYear() + "\nUsername: " + getUsername();
      return s;
    }
}

import java.util.Scanner;
public class Login
{
    private String username;    // username of student
    private String password;    // password of student
    private String newUsername; // new user sets up username
    private String newPassword; //New user sets up password
    Scanner scnr = new Scanner(System.in);

    public void setUsername(String user)
    {
        username = user;
    }

    public String getUsername()
    {
        return username;
    }

    public void setPassword(String pass)
    {
        password = pass;

        if (pass.length() < 8)
        {
            System.out.println("Password must be at least 8 characters long.");
        }
    }

    public String getPassword()
    {
        return password;
    }

    public void setNewUsername(String newUser)
    {
        newUsername = newUser;

        System.out.print("Enter a username ");
        newUser = scnr.next();
    }

    public String getNewUsername()
    {
        return newUsername;
    }

    public void setNewPassword(String newPass)
    {
        newPassword = newPass;

        System.out.print("Enter a password ");
        newPass = scnr.next();
    }

    public String getNewPassword()
    {
        return newPassword;
    }
}

import java.util.Scanner;
public class Messenger
{
    private String reply;  //Replay to someone's post
    private String post; //Make a new post
    Scanner scnr = new Scanner(System.in);

    public void setPost(String post)

    {
        this.post = post;
    }

    public String getPost()
    {
        post = scnr.nextLine();
        return post;
    }

    public void setReply(String reply)
    {
        this.reply = reply;
    }

    public String getReply()
    {
        reply = scnr.nextLine();
        return reply;
    }
}
