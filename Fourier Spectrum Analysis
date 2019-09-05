data=importdata('datafile');
time=data(:,1);
airgap=data(:,2);

n=length(data_input);
Fs=5; %频率
dt=1/Fs;%间隔
t=[0:n-1]*dt; 
per=16
w0=(0:n-1)/dt/n*2*pi;
f=(0:n/2-1)/dt/n*2*pi;
S0=fft(data_input);
a1=abs(S0);
a2=2*a1.^2/(2*pi*n)*dt;
m=floor(n/2/per);
if per==1
    w=f;
    S=a2(1:n/2);
else
    w=mean(reshape(f(1:per*m),per,m));
    S=mean(reshape(a2(1:per*m),per,m));
end
S=S/10
plot(w,S)
