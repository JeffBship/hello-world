

### GrovePi sensors implemented using Java

This project is an example of how GrovePi libraries can be used in a Java apppication which interacts with GrovePi sensors, specifically the button and rotary used in this project.  The GrovePi.observer package has been written in a way to provide a framework where these classes can be extended to use other sensors as needed.

**ButtonRotaryDemo** provides an example of a client class interacting with the observer package.  

For each button or rotary sensor that is desired,  the developer must implement an invoker interface (either implements ButtonInvoker or implements RotaryInvoker).  Within the newly created class include the code for the action desired for any of the button/rotary events.

Invokers
 * **SamplebuttonInvoker**: Provides specific code to be executed when a single, double, or long press is invoked.  In this example it simply prints a message to the console.
 * **SampleRotaryInvoker**: Provides code to be executed when a change is detected in the position of the rotary sensor.  In this example a filter is applied such that minimum difference of SampleRotaryInvoker.tolerance is required to trigger a display.  Also, the output is formatted for single decimal place display.

Once an invoker is emplemented, the next step is to code a driver that uses the invoker.  In this example, 
**ButtonRotaryDemo.java**: Instantiates invokers, assigns invokers to sensors and pins and starts reading the sensors. 






### Package grovepi.observer

This package provides the tools used to create the invokers.  
* **InputSensorReader**: Provides a common set of control methods and class variables for subclasses.

  * **DigitalInputReader (extends InputSensorReader)**: Reads sensor data from a GrovePi digital sensor and updates an observed with this data.

  * **AnalogInputReader (extends InputSensorReader)**:  An instance of this class reads sensor data from a GrovePi analog sensor and updates an observer with this data.

* **InputSensorObserver**: Provides the interface that all concrete InputSensorObservers must implement.

  * **ButtonPressDistinguisher (implements InputSensorObserver)**: Recieves updates containing sensor events, analyzes the timing of these events and invokes the appropriate method on this instance's ButtonInvoker object.

  * **RotaryAngleDeterminer (implements InputSensorObserver)**: Determines and reports the angular position of the rotary angle sensor.  
* **Interfaces**:
  * **ButtonInvoker**: Declares the methods that are called when ButtonPressDistinguisher identifies a single, double, and long press respectively.
  * **RotaryInvoker**: Declares a method to call when RotaryAngleDenterminer is updated.


### Credits

This GrovePi sensor demonstration is extensin of coursework for CS505 Design Patterns at Central Connecticut State University,
Fall 2017, with Dr. Chad Williams.

Interested in Computer Science at CCSU?:  http://www.ccsu.edu/cs/

@author James Luczynski

@author Jeff Blankenship

## License

The MIT License (MIT)

GrovePi for the Raspberry Pi: an open source platform for connecting Grove Sensors to the Raspberry Pi.
Copyright (C) 2017  Dexter Industries

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
