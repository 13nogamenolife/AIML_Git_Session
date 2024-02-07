public class MyPoint {
private int x;
 private int y;
 // Default constructor
 public MyPoint() {
 this.x = 0;
 this.y = 0;
 }
 // Overloaded constructor
 public MyPoint(int x, int y) {
 this.x = x;
 this.y = y;
 }
 // Method to set both x and y
 public void setXY(int x, int y) {
 this.x = x;
 this.y = y;
 }
 // Method to get x and y in a 2-element int array
 public int[] getXY() {
 int[] coordinates = {this.x,this.y};
 return coordinates;
 }
 // toString method
 @Override
 public String toString() {
 return "(" + this.x + "," +this.y + ")";
 }
 // Method to calculate distance to another point (x, y)
 public double distance(int x, int y) {
 int xDiff = this.x - x;
 int yDiff = this.y - y;
 return Math.sqrt(xDiff * xDiff + yDiff * yDiff);
 }
 // Overloaded method to calculate distance to another MyPoint
 public double distance(MyPoint another) {
 return distance(another.x, another.y);
 }
 // Overloaded method to calculate distance to the origin (0, 0)
 public double distance() {
 return distance(0, 0);
 }
}
class TestMyPoint {
 public static void main(String[] args) {
 // Test default constructor
 MyPoint point1 = new MyPoint();
 System.out.println("Point 1: " + point1.toString());
 // Test overloaded constructor
 MyPoint point2 = new MyPoint(3, 4);
 System.out.println("Point 2: " + point2.toString());
 // Test setXY method
 point1.setXY(1, 2);
 System.out.println("Point 1 after setXY: " + point1.toString());
 // Test getXY method
 int[] coordinates = point2.getXY();
 System.out.println("Point 2 coordinates: (" + coordinates[0] + "," + 
coordinates[1] + ")");
 // Test distance methods
 System.out.println("Distance from point1 to (5, 6): " + point1.distance(5, 
6));
 System.out.println("Distance from point2 to point1: " + 
point2.distance(point1));
 System.out.println("Distance from point2 to origin: " + point2.distance());
 }
}
