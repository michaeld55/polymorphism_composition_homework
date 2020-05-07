# Polymorphism & Composition Homework - Quiz

# Polymorphism

1. What does the ___word___ 'polymorphism' mean?

The term polymorphism means that it can have 'many forms'.

2. What does it mean when we apply polymorphism to OO design? Give a simple Java example.

  It means we can wrap our objects up in an enclosing type that defines a contract between them all.
```java
  import java.util.*;

public class Network {
    private String name;
    private ArrayList<IConnect> devices;

    public Network(String name){
        this.devices = new ArrayList<>();
        this.name = name;
    }

    public String getName(){
        return name;
    }

    public int deviceCount(){
        return devices.size();
    }

    public void connect(IConnect device){
        devices.add(device);
    }

    public void disconnectAll(){
        devices.clear();
    }
}
```

3. What can we use to implement polymorphism in Java?

  Interfaces or Abstract classes.

4. How many 'forms' can an object take when using polymorphism?

  As many as you need.

5. Give an example of when you could use polymorphism.

  To allow different types of things to be placed into the same ArrayList or HashMap.



# Composition

6. What do we mean by 'composition' in reference to object-oriented programming?

    We can think of it as a "Has a relationship" e.g. A car has a engine.

7. When would you use composition? Provide a simple example in Java.

  To allow a number of different things like devices all run the same function outputData but ensure it is different for each device.

```java

import behaviours.IOutput;

public class Computer {
    private int ram;
    private int hddSize;

    private IOutput outputDevice;  //UPDATED

    public Computer(int ram, int hddSize, IOutput outputDevice) { //UPDATED
        this.ram = ram;
        this.hddSize = hddSize;
        this.outputDevice = outputDevice;
    }

    public int getRam() {
        return this.ram;
    }

    public int getHddSize() {
        return this.hddSize;
    }

    public IOutput getOutputDevice() {
        return this.outputDevice;
    }

    public String outputData(String data) {
        return this.outputDevice.outputData(data);
    }
}
```

8. What is/are the advantage(s) of using composition?

  Composition allows a class to use behaviour from a group of other classes, and makes it possible for that behaviour to change at runtime.

9. When an object is destroyed, what happens to all the objects it is composed of?

  When an object is destroyed ___all___ of its behaviours are also destroyed.
