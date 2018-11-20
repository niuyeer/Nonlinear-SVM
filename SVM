clc
clear all
x=rand(100,1);
y=rand(100,1);
d=zeros(100,1);
P=[];N=[];
%%% desired classes corresponding to the input patterns
for i=1:100
    if y(i)<1/5*sin(10*x(i))+0.3 || (y(i)-0.8)^2+
(x(i)-0.5)^2<0.15^2
        d(i)=1;
        P=[P;x(i) y(i)];
    else d(i)=-1;
          N=[N;x(i) y(i)];
end end
figure (1)
plot(P(:,1),P(:,2),'ro');
hold on
plot(N(:,1),N(:,2),'gx');
hold on
for i=1:100
    for j=1:100
        h(i,j)=d(i)*d(j)*exp(-1*((x(i)-x(j))^2+(y(i)-y(j))^2));
end end
f=-ones(100,1);
a=quadprog(h,f,[],[],d',0,zeros(100,1),[]);
for i=1:100
    if a(i)<=0.00001
        a(i)=0;
end end
%%%support vector
supportVector=[];
for i=1:100
    if a(i)~=0
        k=i;
    supportVector=[supportVector;x(k) y(k)];
end end
plot(supportVector(:,1),supportVector(:,2),'kO','Markersize',10)
hold on
theta0=0;
for i=1:100
    th(i)=a(i)*d(i)*exp(-1*((x(i)-x(k))^2+(y(i)-y(k))^2));
    theta0=theta0+th(i);
end
theta=d(k)-theta0;
c=[];c1=[];c2=[];
threshold=0.04;
for aa=0:0.001:1
    for bb=0:0.001:1
        g=0;

end end
end
for i=1:100
    w=a(i)*d(i)*exp(-1*((x(i)-aa)^2+(y(i)-bb)^2));
    g=g+w;
end
g=g+theta;
    if abs(g)<threshold
c=[c;aa bb];
    end
    if g<1+threshold && g>1-threshold
        c1=[c1;aa bb];
    end
    if g>-1-threshold && g<-1+threshold
plot(c(:,1),c(:,2),'.')
hold on
plot(c1(:,1),c1(:,2),'r.')
hold on
plot(c2(:,1),c2(:,2),'b.')
hold on
