//                BMI CALCULATOR(  body mass index  )
//BMI=(WEIGHT(in pounds)/HEIGHT(in inches)^2))*703


import java.text.DecimalFormat;//for round off of double to string
import java.util.Scanner;

public class bmi_calculator {
    public double weight;
    public double feets;
    public double inches;
    public  double BMI;
    public bmi_calculator(double weight,double feets,double inches)
    {
        this.weight=weight;
        this.feets=feets;
        this.inches=inches;
    }
    public String calculate()
    {   DecimalFormat df = new DecimalFormat("0.00");
        double height=(feets*12)+inches;//HEIGHT IN INCHES
        height*=height;

        BMI=(weight/height)*703;
        String str=df.format(BMI);
        return str;

    }
    public void display()
    {
        if(BMI<=18.5)
        {
            System.out.println("YOUR BMI IS "+calculate()+" AND YOU ARE UNDERWEIGHT PERSON");
        }
        else if(BMI>18.5&&BMI<=24.9)
        {
            System.out.println("YOUR BMI IS "+calculate()+" AND YOU ARE NORMAL WEIGHTED PERSON");
        }
        else if(BMI>24.9&&BMI<=29.9)
        {
            System.out.println("YOUR BMI IS "+calculate()+" AND YOU ARE OVERWEIGHT PERSON");

        }
        else if(BMI>=30)
        {
            System.out.println("YOUR BMI IS "+calculate()+" AND YOU ARE OBESED PERSON");
        }

    }

    public static void main(String arg[]){
        System.out.println("---------------------BMI CALCULATOR---------------------- ");
        System.out.println("BMI BELOW OR EQUAL TO 18.5 IS CONSIDERED AS UNDERWEIGHT");
        System.out.println("BMI GREATER THAN 18.5 AND EQUAL TO 24.9 IS CONSIDERED AS NORMAL WEIGHT");
        System.out.println("BMI GREATER THAN 24.9 AND EQUAL TO 29.9 IS CONSIDERED AS OVER WEIGHT");
        System.out.println("BMI ABOVE 30 IS CONSIDERED AS OBESE PERSON");
        System.out.println();


        Scanner input=new Scanner(System.in);
        System.out.println("What is your weight in pounds?");
        System.out.print("Weight---->");
        double weight=input.nextDouble();
        System.out.println("What is your height in feets and inches?");
        System.out.print("Feets please---->");
        double feets=input.nextDouble();
        System.out.print("Inches please---->");
        double inches=input.nextDouble();
        System.out.println();

        bmi_calculator obj=new bmi_calculator(weight,feets,inches);
        obj.display();

    }
}
