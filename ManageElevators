import java.util.ArrayList;
import java.util.List;

public class ManageElevators {
    private List<Elevator> elevators;
    private int maxFloor;

    public ManageElevators(int cntElevators, int cntFloors, int currentFloor) {
        this.maxFloor = cntFloors;
        elevators = new ArrayList<>();
        for (int i = 0; i < cntElevators; i++) {
            elevators.add(new Elevator(currentFloor, maxFloor));
        }
    }

    public void callingElevator(int floor) {
        if (floor < 0 || floor > maxFloor) {
            System.out.println("Такого этажа не существует!");
            return;
        }
        Elevator rightElevator = findRightElevator(floor);
        rightElevator.addCalls(floor);
    }

    private Elevator findRightElevator(int floor) {
        Elevator rightElevator = null;
        int minDistance = 1000;
        for (Elevator elevator : elevators) {
            if (elevator.passingCall(floor)) {
                int distance = Math.abs(elevator.getCurrentFloor() - floor);
                if (distance < minDistance) {
                    minDistance = distance;
                    rightElevator = elevator;
                }
            }
        }
        if (rightElevator == null) {
            for (Elevator elevator : elevators) {
                int distance = Math.abs(elevator.getCurrentFloor() - floor);
                if (distance < minDistance) {
                    minDistance = distance;
                    rightElevator = elevator;
                }
            }
        }
        return rightElevator;
    }

    public void stage() {
        for (Elevator elevator : elevators) {
            elevator.move();
        }
    }

    public void printVizual() {
        for (int i = maxFloor; i >= 0; i--) {
            for (int j = 0; j < elevators.size(); j++) {
                if (elevators.get(j).getCurrentFloor() == i) {
                    System.out.print("П | ");
                } else {
                    System.out.print(". | ");
                }
            }
            System.out.println(i);
        }
        System.out.println();
    }
}
