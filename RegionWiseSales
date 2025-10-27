import java.util.*;
import java.io.*;

public class RegionSales {
    public static void main(String[] args) {
        String file = "E:\\Usman\\sales.txt";
        Map<String, Integer> regionTotals = new HashMap<>();
        int grandTotal = 0;
        try {
            File f1 = new File(file);
            Scanner s1 = new Scanner(f1);
            if (s1.hasNextLine()) s1.nextLine(); 
            while (s1.hasNextLine()) {
                String line = s1.nextLine();
                String[] fields = line.split("\t");
                if (fields.length >= 6) {
                    try {
                        String region = fields[1].trim();
                        int qty = Integer.parseInt(fields[4].trim());
                        int unitPrice = Integer.parseInt(fields[5].trim());
                        int lineTotal = qty * unitPrice;
                        regionTotals.put(region, regionTotals.getOrDefault(region, 0) + lineTotal);
                        grandTotal += lineTotal;
                    } catch (NumberFormatException e) {
                        System.out.println("Invalid number in line: " + line);
                    }
                } else {
                    System.out.println("Skipping line: " + line);
                }
            }
            s1.close();
            System.out.println(" Region Wise Sales");
            for (String region : regionTotals.keySet()) {
                System.out.println(region + " : " + regionTotals.get(region));
            }
            System.out.println("Grand Total is: " + grandTotal);
        } catch (IOException e) {
            System.out.println("File not found");
        }
    }
}
