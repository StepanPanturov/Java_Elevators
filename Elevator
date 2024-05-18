import java.util.LinkedList;


public class Elevator {
    private LinkedList<Integer> calls;
    private int currentFloor;
    private int maxFloor;
    private boolean direction;

    public Elevator(int initialFloor, int maxFloor) {
        this.calls = new LinkedList<>();
        this.currentFloor = initialFloor;
        this.maxFloor = maxFloor;
        this.direction = true;
    }

    public void move() {
        if (!calls.isEmpty()) {
            int needFloor = calls.getFirst();
            if (currentFloor > needFloor) {
                currentFloor--;
            }
            else if (currentFloor < needFloor) {
                currentFloor++;
            }
            if (currentFloor == needFloor) {
                calls.removeFirst();
                if (!calls.isEmpty()) {
                    direction = currentFloor < calls.getFirst();
                }
            }
        }
    }

    public int getCurrentFloor() {
        return currentFloor;
    }

    public void addCalls(int floor) {
        if (floor >= 0 && floor <= maxFloor && !calls.contains(floor)) {
            calls.add(floor);
            calls.sort((a, b) -> direction ? a - b : b - a);
        }
    }

    public boolean passingCall(int floor) {
        if (floor >= currentFloor && direction) {
            return true;
        }
        else {
            return floor <= currentFloor && !direction;
        }
    }
}
