We can see that regardless of where the rod is - 0 degrees or 89 degrees - the voltage and hence torque provided is the same. 
But we do not need the same amount of torque to move 90 degrees as we do to move a single degree. 
With this insight in mind, we can then propose a better solution - one that will be a foundational block in control systems - The proportionality constant Kp.
Let there be a constant named Kp, which is a constant of proportionality between the difference of the desired and current angle , and the voltage output.
ie Kp is the constant of proportionality between the "error" and output torque.
Putting it into an equation, we get
V_out = Kp * (Desired Angle - Current Angle)

This error will be our lifeline. It will tell us by how much we are off. 
On this we can base our calculations.

Let us put this into the code with a sandbox function like so 
```python
def compute_motor_voltage(current_angle, time_elapsed):
    error = TARGET_ANGLE - current_angle
    Kp = 0.4
    voltage = Kp * error
    return voltage
```

Finally.. did that work?
![[Tutorial_1_Image_5.png]]
Nope it did not.
It's pretty much the same as the last graph. 
It's just doing simple harmonic motion, and in our case there's no friction to damp it either, so it just oscillates.
Well.. yeah. But let me tell you- this is the right path. 
We just need to improve it , bit by bit, and we will get what we want.