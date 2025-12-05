# RADAR_RANGE_EQUATION

### Aim:

To calculate the maximum range of a radar system using the Radar Range equation and verify through Python Programming.

---

### Theory:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:

$$R_{max} = \left(\frac{P_t G \sigma A_e}{(4 \pi)^2 S_{min}} \right)^{\frac{1}{4}}$$

---

### Procedure:

1. Set Up the Python Enviroment:Ensure that Pytho is installed on your system. You can use Anaconda for managing Python packages and environments, or any other Python IDE of your choice.
2. Import Necessary Libraries: Import the math library in Python.
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using the Radar Range Equation.
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, transmitter gain, receiver gain, radar frequency, radar cross section and minimum detectable power.
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar.
6. Execute the program: Run the Python script to calculate and display the maximum range of the radar.

---

### Program:

```
sigma = 0.5;
Ae = 1;
Smin = 1e-10;

G = 30;
Ppeak = 4:1:10;

Rmax_values = zeros(1, length(Ppeak));

for i = 1:length(Ppeak)
    Rmax_values(i) = ((Ppeak(i) * G * sigma * Ae) / (16 * %pi^2 * Smin))^(1/4);
end

clf;
subplot(3,1,1);
plot(Ppeak, Rmax_values, 'b');
xlabel('P_t (Watts)');
ylabel('R_{max}');
title('Variation of R_{max} with P_t');


Ppeak = 3;    
G = 20:5:100;     
Rmax_values = zeros(1, length(G));

for i = 1:length(G)
    Rmax_values(i) = ((Ppeak * G(i) * sigma * Ae) / (16 * %pi^2 * Smin))^(1/4);
end

subplot(3,1,2);
plot(G, Rmax_values, 'r');
xlabel('G (linear)');
ylabel('R_{max}');
title('Variation of R_{max} with G');


G = 10;
Ppeak = 2;    

Smin_values = logspace(-12, -8, 50);

Rmax_values = zeros(1, length(Smin_values));

for i = 1:length(Smin_values)
    Rmax_values(i) = ((Ppeak * G * sigma * Ae) / (16 * %pi^2 * Smin_values(i)))^(1/4);
end

subplot(3,1,3);
plot(Smin_values, Rmax_values, 'g');
xlabel('S_{min}');
ylabel('R_{max}');
title('Variation of R_{max} with S_{min}');
give correct code with header file

```

### Output Waveform:

<img width="1640" height="988" alt="Screenshot 2025-12-05 032415" src="https://github.com/user-attachments/assets/584082e2-3930-4dc8-a723-0096d3172ce9" />


---

### Manual Calculation:

![WhatsApp Image 2025-12-04 at 15 38 36_8b6df173](https://github.com/user-attachments/assets/35123cb0-a32e-43d7-b34c-f5c1c59354fd)



---

### Result:

Thus, the value of maximum range of a radar of a radar system calculated using the Radar Equation is successfully verified using Scilab programming.
