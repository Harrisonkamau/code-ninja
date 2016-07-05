---
layout: post
title: Encapsulation in Java
---
<h1>Encapsulation in Object Oriented Programming</h1>
<h3>Overview</h3>
<p>The whole idea behind encapsulation is to hide the implementation details from users. If a data member is private it means it can only be accessed within the same class. No outside class can access private data member (variable) of other class. However if we setup public getter and setter methods to update (for e.g. <strong>void setSerialNumber(int serialNumber))</strong>and read (for e.g.  <strong>int getSerialNumber())</strong> the private data fields then the outside class can access those private data fields via public methods. This way data can only be accessed by public methods thus making the private fields and their implementation hidden for outside classes. That’s why encapsulation is known as <strong>data hiding</strong>. Lets see an example to understand this concept better.</p>
~~~Java
public class EmployeeRegister{
    private int serialNumber;
    private String empName;
    private int empAge;

    //Getter and Setter methods
    public int getEmpSerialNumber(){
        return serialNumber;
    }

    public String getEmpName(){
        return empName;
    }

    public int getEmpAge(){
        return empAge;
    }

    public void setEmpAge(int newValue){
        empAge = newValue;
    }

    public void setEmpName(String newValue){
        empName = newValue;
    }

    public void setEmpSerialNumber(int newValue){
        serialNumber = newValue;
    }
}
public class EncapsTest{
    public static void main(String args[]){
         EmployeeRegister obj = new EmployeeRegister();
         obj.setEmpName("Harry");
         obj.setEmpAge(32);
         obj.setEmpSerialNumber(112233);
         System.out.println("Employee Name: " + obj.getEmpName());
         System.out.println("Employee Serial Number: " + obj.getEmpSerialNumber());
         System.out.println("Employee Age: " + obj.getEmpAge());
    }
}
~~~

<h2><strong>Output:</strong></h2>
~~~Java
Employee Name: Harry
Employee Serial Number: 112233
Employee Age: 32
~~~

<p>In above example all the three data members (or data fields) are private which cannot be accessed directly. These fields can be accessed via public methods only. Fields empName, serialNumber and empAge are made hidden data fields using encapsulation technique of OOPs.</p>






<h3>What use Getters and Setters</h3>
<p>We can create a fully encapsulated class in Java by making all the data members of the class private. Now we can use setter and getter methods to set and get the data in it.</p>
