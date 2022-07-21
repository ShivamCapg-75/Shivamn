// Shivamn



1. Create and Custom Exception Called InsufficientFundsException,this exception should be raise when the user is trying
to withdraw the amount which is greater then the balance amount.


2.Create a Collection of the type ArrayList and store Vehicle object.

Vehicle object has the following attributes

vname
brand
price

show us the sorting of Vehicle by name,price and brand


***********************************************************************************


//import java.util.*;
//import java.io.*;
//import java.math.*;
//import java.util.regex.*;
//import java.text.*;

class UserDefinedException
{
    public static void main(String args[])
    {
        System.out.println("Shivam HDFC Bank Account\n" );
        Account acct = new Account();
        System.out.println("Current balance : " + acct.balance());
        System.out.println("Withdrawing Amount 200");
        acct.withdraw(200);
        System.out.println("Current balance : " + acct.balance());
        acct.withdraw(1000);
    }
}
class Account
{
    private int balance = 1000;
    public int balance() {
        return balance;
    }
    public void withdraw(int amount) throws NotSufficientFundException {
        if (amount > balance) {
            throw new NotSufficientFundException(String.format("Current balance %d is less than requested amount %d", balance, amount));
    }
    balance = balance - amount;
    }
    public void deposit(int amount) {
        if (amount <= 0) {
        throw new IllegalArgumentException(
                String.format("Invalid deposit amount %s", amount));
        }
    }
}
    class NotSufficientFundException extends RuntimeException {
    private String message;
    public NotSufficientFundException(String message) {
        this.message = message;
    }
    public NotSufficientFundException(Throwable cause, String message) {
        super(cause);
        this.message = message;
    }
    public String getMessage() {
        return message;
    }
}


***************************************************************************************************



****************************************************************************************************************

// Java Program to Sort an ArrayList


import java.util.*;


class Car {
    String Vname;
    String Brand;
    int Price;


    Car(String Vname, String Brand, int Price)
    {
        this.Vname = Vname;
        this.Brand = Brand;
        this.Price = Price;
    }
}


class PriceComparator implements Comparator<Car> {

    
    public int compare(Car c1, Car c2)
    {
        if (c1.Price == c2.Price)
            return 0;
        else if (c1.Price > c2.Price)
            return 1;
        else
            return -1;
    }
}

class GFG {


    public static void main(String[] args)
    {
        // Creating the ArrayList object
        ArrayList<Car> c = new ArrayList<Car>();
        c.add(new Car("Car", "Kia", 200000));
        c.add(new Car("Car", "creta", 1000000));
        c.add(new Car("Scooty", "Jupitar", 500000));
        c.add(new Car("Car", "Mercedes", 4500000));
        c.add(new Car("Scooty", "Activa" ,20000));

        
        Collections.sort(c, new PriceComparator());

        
        for (Car car : c) {

            // Print the sorted ArrayList
            System.out.println(car.Price + " " + car.Brand + " " + car.Vname);
        }
    }
}
