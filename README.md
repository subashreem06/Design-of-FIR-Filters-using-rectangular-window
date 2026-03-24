# Design-of-FIR-Filters-using-rectangular-window
#          DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
# LPF
```
clc;
clear;
close;

N = input("Enter filter length (odd) = ");
Wc = input("Enter cutoff frequency (0 to %pi) = ");

alpha = (N-1)/2;

for n = 0:N-1
    
    if n == alpha then
        hd(n+1) = Wc/%pi;
    else
        hd(n+1) = sin(Wc*(n-alpha))/(%pi*(n-alpha));
    end
    
    w(n+1) = 1; // Rectangular window
    h(n+1) = hd(n+1)*w(n+1);
    
end

[H,w] = frmag(h,256);
subplot(2,1,1)
plot2d(w/%pi,H)
title("Magnitude Response LPF")

subplot(2,1,2)
plot2d(w/%pi,20*log10(H))
title("Magnitude in dB")
```
# HPF
```
clc;
clear;
close;

N = input("Enter filter length (odd) = ");
Wc = input("Enter cutoff frequency (0 to %pi) = ");

alpha = (N-1)/2;

for n = 0:N-1
    
    if n == alpha then
        hd(n+1) = 1 - Wc/%pi;
    else
        hd(n+1) = -sin(Wc*(n-alpha))/(%pi*(n-alpha));
    end
    
    w(n+1) = 1;
    h(n+1) = hd(n+1)*w(n+1);
    
end

[H,w] = frmag(h,256);

subplot(2,1,1)
plot2d(w/%pi,H)
title("Magnitude Response HPF")

subplot(2,1,2)
plot2d(w/%pi,20*log10(H))
title("Magnitude in dB")
```
# BPF
```
clc;
clear;
close;

N = input("Enter filter length (odd) = ");
Wc1 = input("Enter lower cutoff = ");
Wc2 = input("Enter upper cutoff = ");

alpha = (N-1)/2;

for n = 0:N-1
    
    if n == alpha then
        hd(n+1) = (Wc2-Wc1)/%pi;
    else
        hd(n+1) = (sin(Wc2*(n-alpha)) - sin(Wc1*(n-alpha)))/(%pi*(n-alpha));
    end
    
    w(n+1) = 1;
    h(n+1) = hd(n+1)*w(n+1);
    
end

[H,w] = frmag(h,256);

subplot(2,1,1)
plot2d(w/%pi,H)
title("Magnitude Response BPF")

subplot(2,1,2)
plot2d(w/%pi,20*log10(H))
title("Magnitude in dB")
```
# BSF
```
clc;
clear;
close;

N = input("Enter filter length (odd) = ");
Wc1 = input("Enter lower cutoff = ");
Wc2 = input("Enter upper cutoff = ");

alpha = (N-1)/2;

for n = 0:N-1
    
    if n == alpha then
        hd(n+1) = 1 - (Wc2-Wc1)/%pi;
    else
        hd(n+1) = (sin(Wc1*(n-alpha)) - sin(Wc2*(n-alpha)))/(%pi*(n-alpha));
    end
    
    w(n+1) = 1;
    h(n+1) = hd(n+1)*w(n+1);
    
end

[H,w] = frmag(h,256);

subplot(2,1,1)
plot2d(w/%pi,H)
title("Magnitude Response BSF")

subplot(2,1,2)
plot2d(w/%pi,20*log10(H))
title("Magnitude in dB")
```



# OUTPUT
<img width="755" height="158" alt="image" src="https://github.com/user-attachments/assets/fbd390b8-32bf-4325-8da4-fdf3282c1bf6" />
<img width="829" height="554" alt="image" src="https://github.com/user-attachments/assets/77f6778b-7ad7-4d6d-b841-db13501f6f74" 
          />
          <img width="880" height="163" alt="image" src="https://github.com/user-attachments/assets/74a8f572-2a1d-441b-843b-b75c22b905e9" />
          <img width="939" height="565" alt="image" src="https://github.com/user-attachments/assets/e489f9bd-ab6f-4a6a-a6ed-7939d60a3d1b" />
          <img width="406" height="157" alt="image" src="https://github.com/user-attachments/assets/bf089fd4-8c1c-4305-9174-8425757f72e2" />
          <img width="914" height="490" alt="image" src="https://github.com/user-attachments/assets/1dc444c2-9b67-40e4-8a42-4017487aa95d" />
          <img width="402" height="187" alt="image" src="https://github.com/user-attachments/assets/e87bdd69-29d7-4580-b0ca-fe7ed5030e6e" />
          <img width="861" height="514" alt="image" src="https://github.com/user-attachments/assets/6ccb0e0c-e751-497d-91b6-2a50bde604f6" />









# RESULT
