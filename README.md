# FactoryEmployeeAssignment

using System;
class Employee // base class
{
    //variables
    private String name;
    private int empNum;

    //properties
    public string Name
    {

        get
        {
            return name;
        }
        set
        {
            name = value;
        }
    }

    public int EmpNum
    {

        get
        {
            return empNum;
        }
        set
        {
            empNum = value;
        }
    }

    //constructor
    public Employee(string name, int empNum)
    {
        this.name = name;
        this.empNum = empNum;

    }

    public string toString()
    {
        return "\nEmployee Number : " + empNum + " Name : " + name;
    }
}
class ProductionWorker : Employee // derived class
{
    private int shift;
    private double hourlyPayRate;

    //properties
    public int Shift
    {
        get
        {
            return shift;
        }
        set
        {
            shift = value;
        }
    }
    public double HourlyPayRate
    {
        get
        {
            return hourlyPayRate;
        }
        set
        {
            hourlyPayRate = value;
        }
    }

    //passing parameters to base class Employee from derived class ProductionWorker
    public ProductionWorker(String name, int empNum, int shift, double hourlyPayRate) : base(name, empNum)
    {
        this.shift = shift;
        this.hourlyPayRate = hourlyPayRate;
    }


    public string toString()
    {
        return base.toString() + "\nShift : " + shift + " Hourly Pay Rate : $" + hourlyPayRate;
    }
}


public class Test
{
    public static void Main()
    {
        Console.WriteLine("Enter the name of Employee : ");
        string name = Console.ReadLine();
        Console.WriteLine("Enter the Employee number : ");
        int empNum = Convert.ToInt32(Console.ReadLine());

        Console.WriteLine("Enter the shift : ");
        int shift = Convert.ToInt32(Console.ReadLine());
        Console.WriteLine("Enter the hourly Pay rate : ");
        double hpr = Convert.ToDouble(Console.ReadLine());

        ProductionWorker pc = new ProductionWorker(name, empNum, shift, hpr);


        Console.WriteLine("The Employee ID Number is : " + pc.EmpNum);
        Console.WriteLine("The Employee Name is : " + pc.Name);
        Console.WriteLine("The Employee Shift Number is  : " + pc.Shift);
        Console.WriteLine("The Employee Hourly Pay rate is  : $" + pc.HourlyPayRate);



    }
}


