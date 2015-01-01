Java-Polymorphism-and-Types-of-Music
====================================
import java.util.Scanner;
public class Menu
{
    public static void main()
    {
        int choice = 0;
        while(choice !=5)
        {
            //Menu Code
        Scanner keyboard = new Scanner (System.in);
        Rapper artist;
        System.out.println("****************MENU****************");
        System.out.println("Pick a Rapper (a number) and press enter:");
        System.out.println("1. Dirty South");
        System.out.println("2. East Coast");
        System.out.println("3. West Coast");
        System.out.println("4. Latino Reggaeton");
        System.out.println("5. in order to quit");
        
        System.out.println("****************MENU****************");
        choice = keyboard.nextInt();
        keyboard.nextLine();
        
        
     
        if (choice == 1)
            {
            System.out.println("********************************");
            System.out.println("Is your Dirty South Rapper excessive?");
            System.out.println("Enter 1 for YES, 2 for NO");
            choice = keyboard.nextInt();
            keyboard.nextLine();
            artist = new SouthRapper(0);
            if(choice == 1)
            ((SouthRapper)artist).beExcessive();
            }
        else if (choice == 2)
            artist = new EastRapper(0);
        else if (choice == 3)
            artist = new WestRapper(0);
        else if(choice == 4)
            artist = new LatinoReggaeton(0);
        else 
        break;
           
       //Your choice Printing
       System.out.println("****************YOUR CHOICE****************");
       artist.greet();
       System.out.println("****************YOUR CHOICE****************");
  
    }
    }
}
public abstract class Rapper
{
    private double cashMoney;
    
    public Rapper(double amount)
    {
        cashMoney = amount;
    }
    public void getPaid(int amount)
    {
        cashMoney += amount;
        greet();
        System.out.println("I gotz cash money");
        greet();
    }
    public abstract void greet();
    
}
public class WestRapper extends Rapper
{
    public WestRapper(double amount)
    {
        super(amount);
    }
    
    public void greet()
    {
        System.out.println("West Coast forever! Whassup Gangsta!!!");
    }
}
public class EastRapper extends Rapper
{
    public EastRapper(double amount)
    {
        super(amount);
    }
    
    public void greet()
    {
        System.out.println("East Coast represent! East coast on Fleek!!!");
    }
}
public class SouthRapper extends Rapper implements Country
{
    public SouthRapper(double amount)
    {
        super(amount);
    }
    
    public void greet()
    {
        System.out.println("From the Dirty Dirty!  Gettin' hot in herre");
    }
    
    public void beExcessive()
    {
        for (int i = 0; i < 5; i++)
            System.out.println("Y'all!");
        System.out.println("We be ");
        for (int i = 0; i < 7; i++)
            System.out.print("tippin' ");
        System.out.println(" 'dem cowz.");
    }
}
public class LatinoReggaeton extends Rapper
{
    public LatinoReggaeton(double amount)
    {
        super(amount);
    }
    
    public void greet()
    {
        System.out.println("¡Pitbul, Daddy Yankee, y Don Omar. Vamos Latinos, todos unidos, danzamos Kuduro!");
    }
}
public interface Country
{  
    public void beExcessive();   
}
public class Cowboy implements Country, Comparable
{
    private int hatSize, numCows, bootSize, laborTime;
    
    public Cowboy(int _hatSize, int _numCows, int _bootSize, int _laborTime)
    {
        hatSize = _hatSize;
        numCows = _numCows;
        bootSize = _bootSize;
        laborTime = _laborTime;
    }
    
    public int getBootSize()
    {
        return bootSize;
    }
    
    public int getLaborTime()
    {
        return laborTime;
    }
    
    public int getNumCows()
    {
        return numCows;
    }
    
    public int getHatSize()
    {
        return hatSize;
    }
    
    public void beExcessive()
    {
        System.out.println(" HOOOWWDDDDYYYYY!!!! "); //slap on the back
    }
    
    public int compareTo(Object other)
    {
        Cowboy c = (Cowboy) other;
        
        int deficient = 0;
        int otherDeficient = 0;
        
        if (hatSize == 0)
            deficient++;
        if (numCows == 0)
            deficient++;
        if (bootSize == 0)
            deficient++;  
        if (laborTime == 0)
            deficient++;
        
        if (c.getHatSize() == 0)
            otherDeficient++;
        if (c.getNumCows() == 0)
            otherDeficient++;    
        if (c.getBootSize() == 0)
            otherDeficient++;
        if (c.getLaborTime() == 0)
            otherDeficient++;
            
        if (deficient > 0 && otherDeficient > 0)
           return otherDeficient - deficient;
        else
        {
            int myValue = hatSize + numCows * 3 + bootSize + laborTime * 2;
            int otherValue = c.getHatSize() + c.getNumCows()* 3 + c.getBootSize() + c.getLaborTime()* 2;
            return myValue - otherValue;
        }
    }
}
public class Ranch
{
    public static void main()
    {
        Cowboy juan = new Cowboy(15, 10, 3, 6);
        Cowboy catie = new Cowboy(15, 0, 3, 6);
        System.out.println(juan.compareTo(catie));
        // Catie is almost the same as Juan, but since she has no cows, she is less of a cowboy. 
    }
}
public class Sandwich implements Country
{
    private int calories, taste, meatAmount;
    
    public void beExcessive()
    {
        System.out.println("You just ate 1116 calories");
    }
    
}

Creating a creative Java program in which artists from different styles of music perform!
