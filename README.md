%this part contains the codes for yakebi iteration 
n=10;
A=rand(n)+8*eye(n);%系数矩阵
b=A*ones(n,1);%右端项
x=[0;0;0;0;0;0;0;0;0;0];
er=1;k=0;
while er>0.00005
er=0;k=k+1
for i=1:n
 t=x(i);x(i)=0;s=0;
 for j=1:n
    s=s+A(i,j)*x(j);
 end 
 y(i)=[b(i)-s]/A(i,i);
 x(i)=t;
 er=max(abs（y(i)-x(i)）,er)
 end 
 x=y;x'
 end
