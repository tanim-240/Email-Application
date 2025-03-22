# Email-Application
import java.util.Scanner;

class email {
    private String firstName;
    private String lastName;
    private String department;
    private String passWord;
    private String Company = "ambani.com";
    private String EMail;
    private int MailBox=500;
    private int lengthOfPassword = 10;
    private String showInfo;

    email(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;

        System.out.println();
        this.department = setDepartment();
        System.out.println("Department:" + this.department);
        System.out.println();
        this.passWord = setPassword(10);
        System.out.println("Password: " + this.passWord);
        System.out.println();
        EMail = firstName + lastName + "@" + department + "." + Company;
        System.out.println("Your official Email: "+EMail);
        System.out.println();
       this.showInfo=ShowInfo();
        System.out.println("Employer Information :\n"+showInfo);

    }

    public String setDepartment() {

        Scanner s = new Scanner(System.in);
        System.out.println("Which department are you from :");
        System.out.println("1: for sales");
        System.out.println("2: for Development");
        System.out.println("3: for Accounting");
        System.out.print("Enter Department code:");

        int DepNum = s.nextInt();
        if (DepNum == 1) return "sales";
        if (DepNum == 2) return "Development";
        if (DepNum == 3) return "Accounting";
        else {
            return "";
        }
    }

    public String setPassword(int length) {

        String PassWord = "abcdefghijklmnopqrstuvwxyz1234567890@!#";
        char[] ch = new char[length];
        for (int i = 0; i < length; i++) {
            int rand = (int) (Math.random() * PassWord.length());
            ch[i] = PassWord.charAt(rand);
        }
        return new String(ch);
    }
    public void setMailbox(int Mailbox) {
      this.MailBox=Mailbox;
    }
    public int getMailbox(int Mailbox) {return Mailbox;
    }

    public String ShowInfo(){
        return "DisplayName"+"="+firstName+" "+lastName+"\nPassword :"+passWord+"\nEmail :"+EMail+"\nMailBox:"+MailBox+"mb";
    }

}

class EmailApp {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("How many beginner Employer ?");
        int t = sc.nextInt();
        System.out.println("Enter the Employers name :");


        while(t-->0){
            System.out.print("First Name : ");
            String EmployerFirstName= sc.next();
            System.out.print("Last  Name :");
            String EmployerLastName= sc.next();
            new email(EmployerFirstName,EmployerLastName);
        }
    }
}
