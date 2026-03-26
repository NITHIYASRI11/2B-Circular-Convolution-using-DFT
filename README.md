# EXPT 2B:CIRCULAR-CONVOLUTION-USING-DFT
## AIM
To perform and verify circular convolution operation of two given sequences using SCILAB.
## APPARATUS REQUIRED
PC installed with SCILAB
## PROGRAM:
## CIRCULAR CONVOLUTION
```
clc;
clear;
x = [1 1 1 1];
n1 = 0:1:length(x)-1;
subplot(3,1,1);
plot2d3(n1,x);
xlabel('time');
ylabel('amplitude');
title('input sequence');
h = [1 2 3];
n2 = 0:1:length(h)-1;
subplot(3,1,2);
plot2d3(n2,h);
xlabel('time');
ylabel('amplitude');
title('impulse sequence');
N1 = length(x);
N2 = length(h);
N = max(N1,N2);
N3 = N1 - N2;
if (N3 > 0) then
    h = [h, zeros(1,N3)];
else
    x = [x, zeros(1,abs(N3))];
end
disp(x)
disp(h)
for n = 1:N
    y(n) = 0;
    for i = 1:N
        j = n - i + 1;
        if (j <= 0) then
            j = N + j;
        end
        y(n) = y(n) + x(i) * h(j);
    end
end
disp(y)
n = 0:N-1;
subplot(3,1,3);
plot2d3(n,y);
xlabel('time');
ylabel('amplitude');
title('circular convolution');
```
<br>
## CALCULATIONS:

![WhatsApp Image 2026-03-26 at 09 50 41](https://github.com/user-attachments/assets/a3f287ee-a13a-41a1-9e00-827699c2c8bc)

### SAMPLE OUTPUT:

![WhatsApp Image 2026-03-26 at 11 48 32](https://github.com/user-attachments/assets/ccf1e03a-5cd2-4aa1-a125-d6d789628d28)


## RESULT:
Thus, the circular convolution of the two given sequences were performed and its result was verified.

