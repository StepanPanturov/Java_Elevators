import java.util.Random;

public class Main {
    public static void main(String[] args) throws InterruptedException {
        int cntElevators = 2;
        int cntFloors = 12;
        ManageElevators manageElevators = new ManageElevators(cntElevators, cntFloors, 0);
        Random random = new Random();
        for (int i = 0; i < 15; i++) {
            if (random.nextBoolean()) {
                int randomFloor = random.nextInt(cntFloors + 1);
                manageElevators.callingElevator(randomFloor);
                System.out.println("------------------------------");
                System.out.println("Вызов: " + randomFloor + " этаж");
                System.out.println("------------------------------");
            }
            manageElevators.stage();
            manageElevators.printVizual();
            Thread.sleep(500);
        }
    }
}
