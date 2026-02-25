# EXPT 1: LINEAR-AND-CIRCULAR-CONVOLUTION-USING-DFT
## AIM
To perform and verify linear and circular convolution operation of two given sequences
using SCILAB.
## APPARATUS REQUIRED
PC installed with SCILAB
## PROGRAM:
### LINEAR CONVOLUTION
program:
```
clc;
clear;
x=[2 1 0 1];
h=[1 2 1];
m=length(x);
n=length(h);
a=0:1:m-1;
b=0:1:n-1;
subplot(3,1,1);
plot2d3(a,x);
xlabel('Time');
ylabel('Amplitude');
title('Graphical representation of input signal x');
subplot(3,1,2);
plot2d3(b,h);
xlabel('Time');
ylabel('Amplitude');
title('Graphical representation of impulse signal h');
for i=1:n+m-1;
    conv_sum=0;
    for j=1:i
        if(((i-j+1)<=n)&(j<=m))
            conv_sum=conv_sum+x(j)*h(i-j+1);
        end;
        y(i)=conv_sum;
     end;
end;
disp(y,'convolution sum using direct formula method=')
subplot(3,1,3);
plot2d3(y)
title('Graphical representation of output signal y');
```
### CALCULATIONS:
<img width="800" height="1000" alt="image" src="https://github.com/user-attachments/assets/4f10d651-94b0-4472-9350-ec989cafde8d" />
<img width="800" height="1000" alt="image" src="https://github.com/user-attachments/assets/dd27a6b3-51e1-4060-9bca-6208dcba945d" />
### SAMPLE OUTPUT:
<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/bf0c1b2d-7763-4a30-bb69-7fd7e45ed265" />

## CIRCULAR CONVOLUTION
program:
```
clc;
clear;
x=[1 1 1 1];
n1=0:1:length(x)-1;
subplot(3,1,1);
plot2d3(n1,x);
xlabel('time');
ylabel('amplitude');
title('input sequence');
h=[1 2 3];
n2=0:1:length(h)-1;
subplot(3,1,2);
plot2d3(n2,h);
xlabel('time');
ylabel('amplitude');
title('impulse sequence');
N1=length(x);
N2=length(h);
N=max(N1,N2);
N3=N1-N2;
if(N3>0)
    h=[h,zeros(1,N3)];
else
    x=[x,zeros(1,abs(N3))];
end
disp(x)
disp(h)
for n=1:N
  y(n)=0;
  for i=1:N
      j=n-i+1;
      if(j<=0)
          j=N+j;
      end
  y(n)=y(n)+x(i)*h(j);
  end
end
disp(y)
n=0:N-1;
subplot(3,1,3);
plot2d3(n,y);
xlabel('time');
ylabel('amplitude');
title('circular convolution');
```
### CALCULATIONS:
<img width="800" height="1000" alt="image" src="https://github.com/user-attachments/assets/be6439df-e02d-471c-879b-3bf0a0cdad25" />
### SAMPLE OUTPUT:
<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/df1747b3-e9c8-4369-8347-55576877fe07" />
## RESULT:

Thus, the linear convolution and circular convolution of the two given sequences were performed and its result was verified.
