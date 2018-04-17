# Designing a parking lot

To design a parking lot, we need to clarify many questions like 

1. type of parking --> public or private
2. How many spots are to be accomated?
3. parking structure --> Open or building?
4. is it multi level parking? if yes, how many spots for each level?
5. Do we need to use different sizes of the spots or same size for both bikes and cars? 
6. type of vehicles? --> car/bus/truck/motor cyles
7. Do we need to provide charging spots for electrical bikes/cars
8. How many handicapped and how many regular spots?

Once we get clarification on all the above questions, we have to find how many interfaces or abstact classes required for each entity.

 ### Difference between abstract and Interface :

Abstract classes can define abstract as well as concrete methods whereas Interfaces can define only declaration of classes and methods but not implementation.

In our example, if we think of vehicle, any vehicle will have numberplate and all vehicles hsould pay parking amount. So, we can declare those methods in abstract class to avoid redundancy. If we use interface for vehicle class, we have to define same code in each derived class which is a duplication of work.

### Creating Entities and interfaces/abstraction

public class parkingStructure {
    List<ParkingSpace> availableSpaces;
    Dictionary<vehicle,ParkingSpace> d= new Dictionary<vehicle,ParkingSpace>();
    TowingSystem tow;
    public void tow(ParkingSpace) throws TowingException { }
    public int calculatePayment(ParkingSpace ps){ }
    public ParkingSpace getParkingSpace();
    public ParkingSpace findMyParkigSpace(vehicle V);
}

public abstract class ParkingSpace {
    private Vehicle v;
    private ParkingSpace ps;
    public certificate park(Vehicle v) throws ParkingExceptin {}
    public unpark(Certificate c) throws ParkingException{}
    public int getParkingFees(){}
    public abstract int getHourlyRate();
    publoic void payParkingFees(int amt) throws PaymentException{}
}

public class HandicappedParkingSpace : ParkingSpace {
    public int getHourlyRate(){}
}

public class RegularParkingSpace : ParkingSpace {
    public int getHourlyRate(){}
}

public class abstract vehicle {
    public string numberPlate;
   public enum color = { blue , green , yellow , orange } ; //to differenctiate type of vehicle in the parking spot
}

For vehicle, we cant create interface since we have defined colors for vehicle type.

### Type of relationship

ParkingSpace is having 'is-a' relationship with regular and handicapped parking spots since both are inheriting the Parkingspace class.

whereas parking structure contains parkingSpace which maintains has-a relationship

