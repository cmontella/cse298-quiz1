# Quiz 1

CSE 298 - Foundations of Robotics

Due: Monday 7/13 at 5:00pm EST

You may use any resources you see fit (notes, lecture, book, internet), but you may not ask questions of one another.

## Description

Answer the following questions. Make at least one commit for each question.

1. Describe the method by which LIDAR measures the distance to objects.

*Most LIDAR work on a principle called "time-of-flight" to measure the distance to objects. The LIDAR emits a pulse of light toward the object, which reflects it back to the LIDAR. The time between when the pulse is emitted and recieved is measured as `t`. The distance is calculated using the equation distance = speed * time / 2 (it's divided by two because the distance traveled by the light is twice the distance to the object). We know the speed of light is ~3x10^8 m/s, so the equation can be solved to yield the distance to the object.*

2. What do accelerometers and gyroscopes measure?

*Accelerometers measure acceleration of the sensor, in m/s^2. Gyroscopes measure the angular velocity of the sensor, in units of rad/s*

3. Given the following data, find the least squares best fit for a line that passes through it. Provide values for Beta1 and Beta2.

```Matlab
data = [    
    0.8345   39.6147
    2.7439   39.7819
    2.9933   35.9441
    5.3286   33.1060
    4.7773   31.5177
    4.6543   30.9445
    7.2957   28.2147
    9.8732   26.9777
    7.5641   24.0761
    9.7092   24.7355
   12.2058   18.1678
    9.6958   17.5425
   13.7505   15.9074
   14.9036   14.0982
   15.2562   13.6018
   15.0757   10.2414
   16.9914    7.8736
   18.1118    6.0755
   20.1223    4.8266
   20.7962    1.2416];
X = [ones(20,1), data(:,1)];   
Y = [data(:,2)];
B = X\Y; %%% Answer: B = [41.7573; -1.9308]
hold on;
plot(data(:,1),data(:,2),'r.');
y = B(2)*data(:,1) + B(1);
plot(x(:,1),y),'b-');
```   
