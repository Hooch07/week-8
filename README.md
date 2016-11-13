# week-8

echo "# week-8" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/Hooch07/week-8.git
git push -u origin master
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package pblwk8v2;

/**
 *
 * @author X00129844
 */
import java.util.Scanner;

public class PBLWk8v2 {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int gender, motherF, motherI, motherH, fatherF, fatherI, fatherH, childF, childI, childH = 0;
        final int INCHES_PER_FOOT = 12;
        String repeat = "Y";

        while (repeat.equalsIgnoreCase("Y")) {
            System.out.println("Enter the gender of your future chil. (Use 1 for female, 0 for male):");
            gender = in.nextInt();

            System.out.println("Enter the hight in feet then the hight in inches of the mother: ");
            motherF = in.nextInt();
            motherI = in.nextInt();
            motherH = ((motherF * 12) + motherI);

            System.out.println("Enter the hight in feet then the hight in inches of the father: ");
            fatherF = in.nextInt();
            fatherI = in.nextInt();
            fatherH = ((fatherF * 12) + fatherI);

            switch (gender) { //femail
                case 1:
                    childH = ((fatherH * 12 / 13) + motherH) / 2;
                    break;

                case 0: // male
                    childH = ((motherH * 12 / 13) + fatherH) / 2;
                    break;
                default:
                    System.err.println("Error, wrong vlue entered!");
                    System.exit(0);
                    break;
            }
            childF = childH / INCHES_PER_FOOT;
            childI = childH % INCHES_PER_FOOT;
            System.out.println("Your future child is estimated to grow to " + childF + " feet and " + childI + " inches.\n");
            
            System.out.println("Enter 'Y' to run again, enter anything else to exit.");
            repeat = in.next();
            
        }

    }

}
