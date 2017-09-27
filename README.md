# SELAB-LAB
import java.util.ArrayList;
import java.util.Scanner;

public class Patron 
{
	Scanner input = new Scanner(System.in);
	private String first; 
	private String last; 
	int bookCount = 0;	//amount books user has in pocket
	int books = 0;
	
	
	//constructor to "add new patron" by entering their name. 
	public Patron(String f, String l)
	{
		first = f; 
		last = l; 
	}
	
	public String toString()
	{
		return first + " " + last; 
	}
	
	public String getName() 
	{
		return first +  " " + last; 
	}

	public static void CheckOutBook()
	{
		System.out.println("Enter book title to be check out: ");
		Scanner input = new Scanner(System.in);
		String bookCheckOut = input.next(); 
		if(Library.BookList.contains(bookCheckOut))
		{
			Library.BookList.remove(bookCheckOut);
			System.out.println("-----" + bookCheckOut + " has been checked out!-----");
			System.out.println ("-------" + bookCheckOut + " is due in 7 days!-------");
							
		}
		else 
			System.out.println(bookCheckOut + " is not in the library. Please enter "
			+ "a different book to be checked out");
		
	}
	
	public static void CheckInBook()
	{
		System.out.println("Enter book title to be checked in: ");
		Scanner input = new Scanner(System.in);
		String bookCheckIn = input.next(); 
		if(Library.BookList.contains(bookCheckIn))
		{
			Library.BookList.add(bookCheckIn);
			System.out.println("-----" + bookCheckIn + " has been checked in!-----");	
							
		}
		else 
			System.out.println(bookCheckIn + " is not in the library. Please enter "
			+ "a different book to be checked out");
	}
	
	public boolean canBorrow()
	{
		if(bookCount <= 3)
		{
			return true; 
		} 
		else 
		{
			return false; 
		}
	}

}
 
