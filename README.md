 
q = input('Enter q  : ');
c = input('Enter c  : ');
LALSELAM = input('Enter LALSELAM : ');


% DEMATEL step1c_12data_file

AD=load('DEMATEL step1c_12data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C12=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

 

% DEMATEL step1c_13data_file
AD=load('DEMATEL step1c_13data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C13=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]


% DEMATEL step1c_14data_file
AD=load('DEMATEL step1c_14data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C14=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]


% DEMATEL step1c_15data_file
AD=load('DEMATEL step1c_15data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C15=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]


% DEMATEL step1c_16data_file
AD=load('DEMATEL step1c_16data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C16=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]



% DEMATEL step1c_17data_file
AD=load('DEMATEL step1c_17data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C17=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]


% DEMATEL step1c_21data_file
AD=load('DEMATEL step1c_21data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C21=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]


% DEMATEL step1c_23data_file
AD=load('DEMATEL step1c_23data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C23=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]


% DEMATEL step1c_24data_file
AD=load('DEMATEL step1c_24data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C24=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 

% DEMATEL step1c_25data_file
AD=load('DEMATEL step1c_25data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C25=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_26data_file
AD=load('DEMATEL step1c_26data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C26=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_27data_file
AD=load('DEMATEL step1c_27data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C27=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_31data_file
AD=load('DEMATEL step1c_31data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C31=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
 
% DEMATEL step1c_32data_file
AD=load('DEMATEL step1c_32data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C32=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
 


% DEMATEL step1c_34data_file
AD=load('DEMATEL step1c_34data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C34=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
 % DEMATEL step1c_35data_file
AD=load('DEMATEL step1c_35data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C35=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
 

% DEMATEL step1c_36data_file
AD=load('DEMATEL step1c_36data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C36=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
 % DEMATEL step1c_37data_file
AD=load('DEMATEL step1c_37data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C37=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
% DEMATEL step1c_41data_file
AD=load('DEMATEL step1c_41data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C41=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
 
% DEMATEL step1c_42data_file
AD=load('DEMATEL step1c_42data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C42=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
  
% DEMATEL step1c_43data_file
AD=load('DEMATEL step1c_43data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C43=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
  
% DEMATEL step1c_45data_file
AD=load('DEMATEL step1c_45data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C45=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
  
% DEMATEL step1c_46data_file
AD=load('DEMATEL step1c_46data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C46=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
  
% DEMATEL step1c_47data_file
AD=load('DEMATEL step1c_47data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C47=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
 
 
 

% DEMATEL step1c_51data_file
AD=load('DEMATEL step1c_51data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C51=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
% DEMATEL step1c_52data_file
AD=load('DEMATEL step1c_52data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C52=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
 
% DEMATEL step1c_53data_file
AD=load('DEMATEL step1c_53data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C53=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]
 
 
% DEMATEL step1c_54data_file
AD=load('DEMATEL step1c_54data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C54=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]


% DEMATEL step1c_56data_file
AD=load('DEMATEL step1c_56data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C56=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_57data_file
AD=load('DEMATEL step1c_57data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C57=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_61data_file
AD=load('DEMATEL step1c_61data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C61=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_62data_file
AD=load('DEMATEL step1c_62data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C62=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_63data_file
AD=load('DEMATEL step1c_63data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C63=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_64data_file
AD=load('DEMATEL step1c_64data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C64=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]


% DEMATEL step1c_65data_file
AD=load('DEMATEL step1c_65data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C65=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

 
% DEMATEL step1c_67data_file
AD=load('DEMATEL step1c_67data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C67=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]


% DEMATEL step1c_71data_file
AD=load('DEMATEL step1c_71data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C71=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_72data_file
AD=load('DEMATEL step1c_72data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C72=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_73data_file
AD=load('DEMATEL step1c_73data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C73=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_74data_file
AD=load('DEMATEL step1c_74data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C74=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

 % DEMATEL step1c_75data_file
AD=load('DEMATEL step1c_75data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C75=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% DEMATEL step1c_76data_file
AD=load('DEMATEL step1c_76data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
ANS_C76=[ex1,ex2,EX1,EX2,e1,e2,h1,h2]

% Initialize cell array to store matrices
matrices = cell(1, 8);
I_7=eye(7);
% Display the generated matrices
for i = 1:8
    decision_matrix_i=transpose([[0 ,ANS_C21(i),ANS_C31(i),ANS_C41(i), ANS_C51(i), ANS_C61(i), ANS_C71(i)];
          [ANS_C12(i),0,ANS_C32(i),ANS_C42(i),ANS_C52(i),ANS_C62(i),ANS_C72(i)];
          [ANS_C13(i),ANS_C23(i),0,ANS_C43(i),ANS_C53(i),ANS_C63(i),ANS_C73(i)];
          [ANS_C14(i),ANS_C24(i),ANS_C34(i),0,ANS_C54(i),ANS_C64(i),ANS_C74(i)];
          [ANS_C15(i),ANS_C25(i),ANS_C35(i),ANS_C45(i),0,ANS_C65(i),ANS_C75(i)];
          [ANS_C16(i),ANS_C26(i),ANS_C36(i),ANS_C46(i),ANS_C56(i),0,ANS_C76(i)];
          [ANS_C17(i),ANS_C27(i),ANS_C37(i),ANS_C47(i),ANS_C57(i),ANS_C67(i),0]]);
    decision_matrices{i} = decision_matrix_i;
    rowSums_decision_matrices{i} = sum(decision_matrices{i}, 2);
    columnSums_decision_matrices{i} = sum(decision_matrices{i}, 1);
    maxrowSum_decision_matrices{i} = max(rowSums_decision_matrices{i});
    maxcolumnSum_decision_matrices{i} = max(columnSums_decision_matrices{i});
    LARGEST_SUM_decision_matrices{i} = max(maxrowSum_decision_matrices{i},maxcolumnSum_decision_matrices{i});
    normalized_decision_matrices{i} = decision_matrices{i} /LARGEST_SUM_decision_matrices{i}; 
    TOTAL_RELATION_matrices{i} = normalized_decision_matrices{i}*inv(I_7-normalized_decision_matrices{i}); 
    averageValue_TOTAL_RELATION_matrices{i} = mean(TOTAL_RELATION_matrices{i}(:));
    rowSums_TOTAL_RELATION_matrices{i} = sum(TOTAL_RELATION_matrices{i}, 2);
    columnSums_TOTAL_RELATION_matrices{i} = transpose(sum(TOTAL_RELATION_matrices{i}, 1));
    PU_matrices{i} = rowSums_TOTAL_RELATION_matrices{i}  - columnSums_TOTAL_RELATION_matrices{i};
    JU_matrices{i} = rowSums_TOTAL_RELATION_matrices{i}  + columnSums_TOTAL_RELATION_matrices{i};
    
end

for i = 1:8
    fprintf('decision Matrix_%d:\n', i);
    disp(decision_matrices{i});
    fprintf('rowSums_decision_matrix_%d:\n', i);
    disp(rowSums_decision_matrices{i});
    fprintf('columnSums_decision_matrix_%d:\n', i);
    disp(columnSums_decision_matrices{i});
    fprintf('maxrowSum_decision_matrix_%d:\n', i);
    disp(maxrowSum_decision_matrices{i});
    fprintf('maxcolumnSum_decision_matrix_%d:\n', i);
    disp(maxcolumnSum_decision_matrices{i});
    fprintf('LARGEST_SUM_decision_matrix_%d:\n', i);
    disp(LARGEST_SUM_decision_matrices{i});
    fprintf('normalized_decision_matrix_%d:\n', i);
    disp(normalized_decision_matrices{i});
    fprintf('TOTAL_RELATION_matrix_%d:\n', i);
    disp(TOTAL_RELATION_matrices{i});
    fprintf('averageValue_TOTAL_RELATION_matrix_%d:\n', i);
    disp(averageValue_TOTAL_RELATION_matrices{i});
    fprintf('rowSums_TOTAL_RELATION_matrix_%d:\n', i);
    disp(rowSums_TOTAL_RELATION_matrices{i});
    fprintf('columnSums_TOTAL_RELATION_matrix_%d:\n', i);
    disp(columnSums_TOTAL_RELATION_matrices{i});
    fprintf('PU_matrix_%d:\n', i);
    disp(PU_matrices{i});
    fprintf('JU_matrix_%d:\n', i);
    disp(JU_matrices{i});
    
    fprintf('\n');
end
for i=1:8
X=PU_matrices{i}(1);
Y=JU_matrices{i}(1);
end
for i=1:7
vertex_i = [PU_matrices{1}(i),JU_matrices{1}(i);PU_matrices{2}(i),JU_matrices{2}(i);PU_matrices{3}(i),JU_matrices{3}(i);PU_matrices{4}(i),JU_matrices{4}(i);PU_matrices{5}(i),JU_matrices{5}(i);PU_matrices{6}(i),JU_matrices{6}(i);PU_matrices{7}(i),JU_matrices{7}(i);PU_matrices{8}(i),JU_matrices{8}(i)];
vertices{i}= vertex_i;
end
for i=1:7
fprintf('vertex_%d:\n', i);
disp(vertices{i});
fprintf('\n');
end

% Calculate the area of the polygon
for i=1:7
area(i) = polyarea(vertices{i}(:, 1), vertices{i}(:, 2));
end
% Display the figures
for i=1:7
figure;
plot([vertices{i}(:, 1); vertices{i}(1, 1)], [vertices{i}(:, 2); vertices{i}(1, 2)], '-o');
end
title('Polygon');
xlabel('X-axis');
ylabel('Y-axis');
axis equal;
grid on;
 
area
 
 % Initialize coordinate of centroid of polygon 1 
    C1_x = 0;
    C1_y = 0;

    % Calculate the centroid using a for loop
    for i = 1:size(vertices{1}, 1)-1
        C1_x = C1_x + (vertices{1}(i, 1)+vertices{1}(i+1, 1))*(vertices{1}(i, 1) * vertices{1}(i+1, 2) - vertices{1}(i+1, 1) * vertices{1}(i, 2));
        C1_y = C1_y + (vertices{1}(i, 2)+vertices{1}(i+1, 2))*(vertices{1}(i, 1) * vertices{1}(i+1, 2) - vertices{1}(i+1, 1) * vertices{1}(i, 2));
    end

    % Add the last edge
    C1_x = C1_x + (vertices{1}(end, 1)+vertices{1}(1, 1))*(vertices{1}(end, 1) * vertices{1}(1, 2) - vertices{1}(1, 1) * vertices{1}(end, 2));
    C1_y = C1_y + (vertices{1}(end, 2)+vertices{1}(1, 2))*(vertices{1}(end, 1) * vertices{1}(1, 2) - vertices{1}(1, 1) * vertices{1}(end, 2));
        
    % Divide by 2 and take the absolute value
    C1_x = C1_x/(6* area(1))
    C1_y = C1_y/(6* area(1))
     

   % Initialize coordinate of centroid of polygon 2 
    C2_x = 0;
    C2_y = 0;
 
    % Calculate the centroid using a for loop
    for i = 1:size(vertices{2}, 1)-1
        C2_x = C2_x + (vertices{2}(i, 1)+vertices{2}(i+1, 1))*(vertices{2}(i, 1) * vertices{2}(i+1, 2) - vertices{2}(i+1, 1) * vertices{2}(i, 2));
        C2_y = C2_y + (vertices{2}(i, 2)+vertices{2}(i+1, 2))*(vertices{2}(i, 1) * vertices{2}(i+1, 2) - vertices{2}(i+1, 1) * vertices{2}(i, 2));
    end
 
    % Add the last edge
    C2_x = C2_x + (vertices{2}(end, 1)+vertices{2}(1, 1))*(vertices{2}(end, 1) * vertices{2}(1, 2) - vertices{2}(1, 1) * vertices{2}(end, 2));
    C2_y = C2_y + (vertices{2}(end, 2)+vertices{2}(1, 2))*(vertices{2}(end, 1) * vertices{2}(1, 2) - vertices{2}(1, 1) * vertices{2}(end, 2));
        
    % Divide by 2 and take the absolute value
    C2_x = C2_x/(6* area(2))
    C2_y = C2_y/(6* area(2))
     
    
    % Initialize coordinate of centroid of polygon 3 
    C3_x = 0;
    C3_y = 0;
 
    % Calculate the centroid using a for loop
    for i = 1:size(vertices{3}, 1)-1
        C3_x = C3_x + (vertices{3}(i, 1)+vertices{3}(i+1, 1))*(vertices{3}(i, 1) * vertices{3}(i+1, 2) - vertices{3}(i+1, 1) * vertices{3}(i, 2));
        C3_y = C3_y + (vertices{3}(i, 2)+vertices{3}(i+1, 2))*(vertices{3}(i, 1) * vertices{3}(i+1, 2) - vertices{3}(i+1, 1) * vertices{3}(i, 2));
    end
 
    % Add the last edge
    C3_x = C3_x + (vertices{3}(end, 1)+vertices{3}(1, 1))*(vertices{3}(end, 1) * vertices{3}(1, 2) - vertices{3}(1, 1) * vertices{3}(end, 2));
    C3_y = C3_y + (vertices{3}(end, 2)+vertices{3}(1, 2))*(vertices{3}(end, 1) * vertices{3}(1, 2) - vertices{3}(1, 1) * vertices{3}(end, 2));
        
    % Divide by 2 and take the absolute value
    C3_x = C3_x/(6* area(3))
    C3_y = C3_y/(6* area(3))
     

    % Initialize coordinate of centroid of polygon 4 
    C4_x = 0;
    C4_y = 0;
 
    % Calculate the centroid using a for loop
    for i = 1:size(vertices{4}, 1)-1
        C4_x = C4_x + (vertices{4}(i, 1)+vertices{4}(i+1, 1))*(vertices{4}(i, 1) * vertices{4}(i+1, 2) - vertices{4}(i+1, 1) * vertices{4}(i, 2));
        C4_y = C4_y + (vertices{4}(i, 2)+vertices{4}(i+1, 2))*(vertices{4}(i, 1) * vertices{4}(i+1, 2) - vertices{4}(i+1, 1) * vertices{4}(i, 2));
    end
 
    % Add the last edge
    C4_x = C4_x + (vertices{4}(end, 1)+vertices{4}(1, 1))*(vertices{4}(end, 1) * vertices{4}(1, 2) - vertices{4}(1, 1) * vertices{4}(end, 2));
    C4_y = C4_y + (vertices{4}(end, 2)+vertices{4}(1, 2))*(vertices{4}(end, 1) * vertices{4}(1, 2) - vertices{4}(1, 1) * vertices{4}(end, 2));
        
    % Divide by 2 and take the absolute value
    C4_x = C4_x/(6* area(4))
    C4_y = C4_y/(6* area(4))
     
 

    % Initialize coordinate of centroid of polygon 5 
    C5_x = 0;
    C5_y = 0;
 
    % Calculate the centroid using a for loop
    for i = 1:size(vertices{5}, 1)-1
        C5_x = C5_x + (vertices{5}(i, 1)+vertices{5}(i+1, 1))*(vertices{5}(i, 1) * vertices{5}(i+1, 2) - vertices{5}(i+1, 1) * vertices{5}(i, 2));
        C5_y = C5_y + (vertices{5}(i, 2)+vertices{5}(i+1, 2))*(vertices{5}(i, 1) * vertices{5}(i+1, 2) - vertices{5}(i+1, 1) * vertices{5}(i, 2));
    end
 
    % Add the last edge
    C5_x = C5_x + (vertices{5}(end, 1)+vertices{5}(1, 1))*(vertices{5}(end, 1) * vertices{5}(1, 2) - vertices{5}(1, 1) * vertices{5}(end, 2));
    C5_y = C5_y + (vertices{5}(end, 2)+vertices{5}(1, 2))*(vertices{5}(end, 1) * vertices{5}(1, 2) - vertices{5}(1, 1) * vertices{5}(end, 2));
        
    % Divide by 2 and take the absolute value
    C5_x = C5_x/(6* area(5))
    C5_y = C5_y/(6* area(5))
    

    % Initialize coordinate of centroid of polygon 6 
    C6_x = 0;
    C6_y = 0;
 
    % Calculate the centroid using a for loop
    for i = 1:size(vertices{6}, 1)-1
        C6_x = C6_x + (vertices{6}(i, 1)+vertices{6}(i+1, 1))*(vertices{6}(i, 1) * vertices{6}(i+1, 2) - vertices{6}(i+1, 1) * vertices{6}(i, 2));
        C6_y = C6_y + (vertices{6}(i, 2)+vertices{6}(i+1, 2))*(vertices{6}(i, 1) * vertices{6}(i+1, 2) - vertices{6}(i+1, 1) * vertices{6}(i, 2));
    end
 
    % Add the last edge
    C6_x = C6_x + (vertices{6}(end, 1)+vertices{6}(1, 1))*(vertices{6}(end, 1) * vertices{6}(1, 2) - vertices{6}(1, 1) * vertices{6}(end, 2));
    C6_y = C6_y + (vertices{6}(end, 2)+vertices{6}(1, 2))*(vertices{6}(end, 1) * vertices{6}(1, 2) - vertices{6}(1, 1) * vertices{6}(end, 2));
        
    % Divide by 2 and take the absolute value
    C6_x = C6_x/(6* area(6))
    C6_y = C6_y/(6* area(6))
     
% Initialize coordinate of centroid of polygon 7 
    C7_x = 0;
    C7_y = 0;
 
    % Calculate the centroid using a for loop
    for i = 1:size(vertices{7}, 1)-1
        C7_x = C7_x + (vertices{7}(i, 1)+vertices{7}(i+1, 1))*(vertices{7}(i, 1) * vertices{7}(i+1, 2) - vertices{7}(i+1, 1) * vertices{7}(i, 2));
        C7_y = C7_y + (vertices{7}(i, 2)+vertices{7}(i+1, 2))*(vertices{7}(i, 1) * vertices{7}(i+1, 2) - vertices{7}(i+1, 1) * vertices{7}(i, 2));
    end
 
    % Add the last edge
    C7_x = C7_x + (vertices{7}(end, 1)+vertices{7}(1, 1))*(vertices{7}(end, 1) * vertices{7}(1, 2) - vertices{7}(1, 1) * vertices{7}(end, 2));
    C7_y = C7_y + (vertices{7}(end, 2)+vertices{7}(1, 2))*(vertices{7}(end, 1) * vertices{7}(1, 2) - vertices{7}(1, 1) * vertices{7}(end, 2));
     
    % Divide by 2 and take the absolute value
    C7_x = C7_x/(6* area(7))
    C7_y = C7_y/(6* area(7))
    subjective_weight_criteria_1=sqrt(C1_x^2+C1_y^2)
    subjective_weight_criteria_2=sqrt(C2_x^2+C2_y^2)
    subjective_weight_criteria_3=sqrt(C3_x^2+C3_y^2)
    subjective_weight_criteria_4=sqrt(C4_x^2+C4_y^2)
    subjective_weight_criteria_5=sqrt(C5_x^2+C5_y^2)
    subjective_weight_criteria_6=sqrt(C6_x^2+C6_y^2)
    subjective_weight_criteria_7=sqrt(C7_x^2+C7_y^2)
    
    
%FINDING OBJECTIVE WEIGHT BY SEM
AD=load('SEM_F1C1data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R11=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
AD=load('SEM_F2C1data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R21=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F3C1data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R31=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F4C1data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R41=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F5C1data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R51=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F6C1data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R61=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F7C1data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R71=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
%GROUP q-ROFRC for C1
ANS_C1=[R11;R21;R31;R41;R51;R61;R71]
 
 
AD=load('SEM_F1C2data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R11=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F2C2data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R21=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F3C2data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R31=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F4C2data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R41=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F5C2data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R51=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F6C2data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R61=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F7C2data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R71=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
%GROUP q-ROFRC for C2
ANS_C2=[R11;R21;R31;R41;R51;R61;R71]
 
AD=load('SEM_F1C3data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R11=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F2C3data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R21=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F3C3data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R31=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F4C3data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R41=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F5C3data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R51=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F6C3data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R61=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F7C3data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R71=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
%GROUP q-ROFRC for C3
ANS_C3=[R11;R21;R31;R41;R51;R61;R71]
 
AD=load('SEM_F1C4data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R11=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F2C4data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R21=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F3C4data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R31=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F4C4data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R41=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F5C4data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R51=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F6C4data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R61=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F7C4data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R71=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
%GROUP q-ROFRC for C4
ANS_C4=[R11;R21;R31;R41;R51;R61;R71]
 
AD=load('SEM_F1C5data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R11=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F2C5data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R21=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F3C5data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R31=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F4C5data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R41=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F5C5data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R51=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F6C5data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R61=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F7C5data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R71=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
%GROUP q-ROFRC for C5
ANS_C5=[R11;R21;R31;R41;R51;R61;R71]
 
AD=load('SEM_F1C6data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R11=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];

AD=load('SEM_F2C6data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R21=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F3C6data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R31=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F4C6data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R41=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F5C6data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R51=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F6C6data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R61=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F7C6data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R71=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
%GROUP q-ROFRC for C6
ANS_C6=[R11;R21;R31;R41;R51;R61;R71]
 
 
AD=load('SEM_F1C7data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R11=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];

AD=load('SEM_F2C7data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R21=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F3C7data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R31=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F4C7data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R41=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F5C7data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R51=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F6C7data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R61=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
AD=load('SEM_F7C7data_file.txt');
r=AD(:,1);
a=AD(:,2);
b=AD(:,3);
for i=1:7
if (r(i)<5)
T(i)=(c^4 - c^(4-r(i)))/(2*(c^4)-2);
end
if (r(i)>=5)
T(i)=(c^4 + c^(r(i)-4)-2)/(2*(c^4)-2);
end
hesitancy(i)=((a(i))^q+(b(i))^q-((a(i))^q)*((b(i))^q))^(1/q);
M(i)=((1-(b(i))^(q))^(1/q) - (a(i)))/6;
wx(i)=10*T(i);
ex(i)= wx(i)-((wx(i)*hesitancy(i))/2);
Ex(i)= wx(i)+((wx(i)*hesitancy(i))/2);
En(i)= M(i)*10;
He(i)=  (En(i))*LALSELAM;
end
R0(:,1)=ex;
R0(:,2)=Ex;
R0(:,3)=En;
R0(:,4)=He;
R0;
for i=1:7
R1(i,:)=ex(i);
end
ex=R1(:,1);
for i=1:7    
        s3(i)=ex(i)+sum(R1(R1(:,1) < ex(i)));
        N3(i) = 1+numel(R1(R1(:,1) < ex(i)));
        lex(i)=s3(i)/N3(i);
end
for i=1:7
        s4(i)=ex(i)+sum(R1(R1(:,1) > ex(i)));
        N4(i) = 1+numel(R1(R1(:,1) > ex(i)));
        hex(i)=s4(i)/N4(i);
end
for i=1:7
R2(i,:)=Ex(i);
end
Ex=R2(:,1);
for i=1:7
        s5(i)=Ex(i)+sum(R2(R2(:,1) < Ex(i)));
        N5(i) = 1+numel(R2(R2(:,1) < Ex(i)));
        lEx(i)=s5(i)/N5(i);
end
for i=1:7
        s6(i)=Ex(i)+sum(R2(R2(:,1) > Ex(i)));
        N6(i) = 1+numel(R2(R2(:,1) > Ex(i)));
        hEx(i)=s6(i)/N6(i);
        
end
for i=1:7
R3(i,:)=(En(i))^2;
end
EN=R3(:,1);
for i=1:7
        s7(i)=EN(i)+sum(R3(R3(:,1) < EN(i)));
        N7(i) = 1+numel(R3(R3(:,1) < EN(i)));
        lEN(i)=sqrt(s7(i)/N7(i));
end
for i=1:7
        s8(i)=EN(i)+sum(R3(R3(:,1) > EN(i)));
        N8(i) = 1+numel(R3(R3(:,1) > EN(i)));
        hEN(i)=sqrt(s8(i)/N8(i));       
end
 
for i=1:7
R4(i,:)=(He(i))^2;
end
HE=R4(:,1);
for i=1:7
        s9(i)=HE(i)+sum(R4(R4(:,1) < HE(i)));
        N9(i) = 1+numel(R4(R4(:,1) < HE(i)));
        lHE(i)=sqrt(s9(i)/N9(i));
end
for i=1:7
        s10(i)=HE(i)+sum(R4(R4(:,1) > HE(i)));
        N10(i) = 1+numel(R4(R4(:,1) > HE(i)));
        hHE(i)=sqrt(s10(i)/N10(i));      
end
R5(:,1)=lex;
R5(:,2)=hex;
R5(:,3)=lEx;
R5(:,4)=hEx;
R5(:,5)=lEN;
R5(:,6)=hEN;
R5(:,7)=lHE;
R5(:,8)=hHE;
R5;
for i=1:7
    ex1=sum(lex)/7;
    ex2=sum(hex)/7;
    EX1=sum(lEx)/7;
    EX2=sum(hEx)/7;
    sg1(i)=(lEN(i)*lEN(i));
sg2(i)=(hEN(i)*hEN(i));
sg3(i)=(lHE(i)*lHE(i));
sg4(i)=(hHE(i)*hHE(i));
e1=sqrt(sum(sg1)/7);
e2=sqrt(sum(sg2)/7);
h1=sqrt(sum(sg3)/7);
h2=sqrt(sum(sg4)/7);
end
R71=[ex1,ex2,EX1,EX2,e1,e2,h1,h2];
 
%GROUP q-ROFRC for C7
ANS_C7=[R11;R21;R31;R41;R51;R61;R71]
 
 
 
a=ANS_C1(:,1);
A=ANS_C1(:,2);
b=ANS_C1(:,3);
B=ANS_C1(:,4);
e=ANS_C1(:,5);
E=ANS_C1(:,6);
h=ANS_C1(:,7);
H=ANS_C1(:,8);
S1=sum(B);
sprintf('%0.6f', S1);
R2= sum(power(E,2));
S2=sqrt(R2);
sprintf('%0.6f', R2);
sprintf('%0.6f', S2);
R3= sum(power(H,2));
S3=sqrt(R3);
sprintf('%0.6f', R3);
sprintf('%0.6f', S3);
S1=sum(B);
sprintf('%0.6f', S1);
S2=sqrt(sum(power(E,2)));
sprintf('%0.6f', S2);
S3=sqrt(sum(power(H,2)));
sprintf('%0.6f', S2);
for i=1:7
ex(i)=a(i)/S1;
Ex(i)=A(i)/S1;
eX(i)=b(i)/S1;
EX(i)=B(i)/S1;
en(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(e(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
En(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(E(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
he(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(h(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
He(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(H(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
m(i)=ex(i)*log(ex(i));
T1 = sum(m);
lex1 = -T1/log(7);
M(i)=Ex(i)*log(Ex(i));
T2 = sum(M);
Hex1 = -T2/log(7);
n(i)=eX(i)*log(eX(i));
T3 = sum(n);
lEX1= -T3/log(7);
N(i)=EX(i)*log(EX(i));
T4 = sum(N);
HEX1 = -T4/log(7);
p(i) = (power(en(i),2)*log(en(i)));
w1 = sum(p);
len1 = sqrt(-w1/log(7));
P(i) = (power(En(i),2)*log(En(i)));
W1 = sum(P);
HEN1 = sqrt(-W1/log(7));
q(i) = (power(he(i),2)*log(he(i)));
z1 = sum(q);
lhe1 = sqrt(-z1/log(7));
Q(i) = (power(He(i),2)*log(He(i)));
Z1 = sum(Q);
HHE1 = sqrt(-Z1/log(7));
end
 
a=ANS_C2(:,1);
A=ANS_C2(:,2);
b=ANS_C2(:,3);
B=ANS_C2(:,4);
e=ANS_C2(:,5);
E=ANS_C2(:,6);
h=ANS_C2(:,7);
H=ANS_C2(:,8);
S1=sum(B);
sprintf('%0.6f', S1);
R2= sum(power(E,2));
S2=sqrt(R2);
sprintf('%0.6f', R2);
sprintf('%0.6f', S2);
R3= sum(power(H,2));
S3=sqrt(R3);
sprintf('%0.6f', R3);
sprintf('%0.6f', S3);
S1=sum(B);
sprintf('%0.6f', S1);
S2=sqrt(sum(power(E,2)));
sprintf('%0.6f', S2);
S3=sqrt(sum(power(H,2)));
sprintf('%0.6f', S2);
for i=1:7
ex(i)=a(i)/S1;
Ex(i)=A(i)/S1;
eX(i)=b(i)/S1;
EX(i)=B(i)/S1;
en(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(e(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
En(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(E(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
he(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(h(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
He(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(H(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
m(i)=ex(i)*log(ex(i));
T1 = sum(m);
lex2 = -T1/log(7);
M(i)=Ex(i)*log(Ex(i));
T2 = sum(M);
Hex2 = -T2/log(7);
n(i)=eX(i)*log(eX(i));
T3 = sum(n);
lEX2= -T3/log(7);
N(i)=EX(i)*log(EX(i));
T4 = sum(N);
HEX2 = -T4/log(7);
p(i) = (power(en(i),2)*log(en(i)));
w1 = sum(p);
len2 = sqrt(-w1/log(7));
P(i) = (power(En(i),2)*log(En(i)));
W1 = sum(P);
HEN2 = sqrt(-W1/log(7));
q(i) = (power(he(i),2)*log(he(i)));
z1 = sum(q);
lhe2 = sqrt(-z1/log(7));
Q(i) = (power(He(i),2)*log(He(i)));
Z1 = sum(Q);
HHE2 = sqrt(-Z1/log(7));
end
 
a=ANS_C3(:,1);
A=ANS_C3(:,2);
b=ANS_C3(:,3);
B=ANS_C3(:,4);
e=ANS_C3(:,5);
E=ANS_C3(:,6);
h=ANS_C3(:,7);
H=ANS_C3(:,8);
S1=sum(B);
sprintf('%0.6f', S1);
R2= sum(power(E,2));
S2=sqrt(R2);
sprintf('%0.6f', R2);
sprintf('%0.6f', S2);
R3= sum(power(H,2));
S3=sqrt(R3);
sprintf('%0.6f', R3);
sprintf('%0.6f', S3);
S1=sum(B);
sprintf('%0.6f', S1);
S2=sqrt(sum(power(E,2)));
sprintf('%0.6f', S2);
S3=sqrt(sum(power(H,2)));
sprintf('%0.6f', S2);
for i=1:7
ex(i)=a(i)/S1;
Ex(i)=A(i)/S1;
eX(i)=b(i)/S1;
EX(i)=B(i)/S1;
en(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(e(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
En(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(E(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
he(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(h(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
He(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(H(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
m(i)=ex(i)*log(ex(i));
T1 = sum(m);
lex3 = -T1/log(7);
M(i)=Ex(i)*log(Ex(i));
T2 = sum(M);
Hex3 = -T2/log(7);
n(i)=eX(i)*log(eX(i));
T3 = sum(n);
lEX3= -T3/log(7);
N(i)=EX(i)*log(EX(i));
T4 = sum(N);
HEX3 = -T4/log(7);
p(i) = (power(en(i),2)*log(en(i)));
w1 = sum(p);
len3 = sqrt(-w1/log(7));
P(i) = (power(En(i),2)*log(En(i)));
W1 = sum(P);
HEN3 = sqrt(-W1/log(7));
q(i) = (power(he(i),2)*log(he(i)));
z1 = sum(q);
lhe3 = sqrt(-z1/log(7));
Q(i) = (power(He(i),2)*log(He(i)));
Z1 = sum(Q);
HHE3 = sqrt(-Z1/log(7));
end
 
a=ANS_C4(:,1);
A=ANS_C4(:,2);
b=ANS_C4(:,3);
B=ANS_C4(:,4);
e=ANS_C4(:,5);
E=ANS_C4(:,6);
h=ANS_C4(:,7);
H=ANS_C4(:,8);
S1=sum(B);
sprintf('%0.6f', S1);
R2= sum(power(E,2));
S2=sqrt(R2);
sprintf('%0.6f', R2);
sprintf('%0.6f', S2);
R3= sum(power(H,2));
S3=sqrt(R3);
sprintf('%0.6f', R3);
sprintf('%0.6f', S3);
S1=sum(B);
sprintf('%0.6f', S1);
S2=sqrt(sum(power(E,2)));
sprintf('%0.6f', S2);
S3=sqrt(sum(power(H,2)));
sprintf('%0.6f', S2);
for i=1:7
ex(i)=a(i)/S1;
Ex(i)=A(i)/S1;
eX(i)=b(i)/S1;
EX(i)=B(i)/S1;
en(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(e(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
En(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(E(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
he(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(h(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
He(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(H(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
m(i)=ex(i)*log(ex(i));
T1 = sum(m);
lex4 = -T1/log(7);
M(i)=Ex(i)*log(Ex(i));
T2 = sum(M);
Hex4 = -T2/log(7);
n(i)=eX(i)*log(eX(i));
T3 = sum(n);
lEX4= -T3/log(7);
N(i)=EX(i)*log(EX(i));
T4 = sum(N);
HEX4 = -T4/log(7);
p(i) = (power(en(i),2)*log(en(i)));
w1 = sum(p);
len4 = sqrt(-w1/log(7));
P(i) = (power(En(i),2)*log(En(i)));
W1 = sum(P);
HEN4 = sqrt(-W1/log(7));
q(i) = (power(he(i),2)*log(he(i)));
z1 = sum(q);
lhe4 = sqrt(-z1/log(7));
Q(i) = (power(He(i),2)*log(He(i)));
Z1 = sum(Q);
HHE4 = sqrt(-Z1/log(7));
end
 
a=ANS_C5(:,1);
A=ANS_C5(:,2);
b=ANS_C5(:,3);
B=ANS_C5(:,4);
e=ANS_C5(:,5);
E=ANS_C5(:,6);
h=ANS_C5(:,7);
H=ANS_C5(:,8);
S1=sum(B);
sprintf('%0.6f', S1);
R2= sum(power(E,2));
S2=sqrt(R2);
sprintf('%0.6f', R2);
sprintf('%0.6f', S2);
R3= sum(power(H,2));
S3=sqrt(R3);
sprintf('%0.6f', R3);
sprintf('%0.6f', S3);
S1=sum(B);
sprintf('%0.6f', S1);
S2=sqrt(sum(power(E,2)));
sprintf('%0.6f', S2);
S3=sqrt(sum(power(H,2)));
sprintf('%0.6f', S2);
for i=1:7
ex(i)=a(i)/S1;
Ex(i)=A(i)/S1;
eX(i)=b(i)/S1;
EX(i)=B(i)/S1;
en(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(e(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
En(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(E(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
he(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(h(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
He(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(H(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
m(i)=ex(i)*log(ex(i));
T1 = sum(m);
lex5 = -T1/log(7);
M(i)=Ex(i)*log(Ex(i));
T2 = sum(M);
Hex5 = -T2/log(7);
n(i)=eX(i)*log(eX(i));
T3 = sum(n);
lEX5= -T3/log(7);
N(i)=EX(i)*log(EX(i));
T4 = sum(N);
HEX5 = -T4/log(7);
p(i) = (power(en(i),2)*log(en(i)));
w1 = sum(p);
len5 = sqrt(-w1/log(7));
P(i) = (power(En(i),2)*log(En(i)));
W1 = sum(P);
HEN5 = sqrt(-W1/log(7));
q(i) = (power(he(i),2)*log(he(i)));
z1 = sum(q);
lhe5 = sqrt(-z1/log(7));
Q(i) = (power(He(i),2)*log(He(i)));
Z1 = sum(Q);
HHE5 = sqrt(-Z1/log(7));
end

a=ANS_C6(:,1);
A=ANS_C6(:,2);
b=ANS_C6(:,3);
B=ANS_C6(:,4);
e=ANS_C6(:,5);
E=ANS_C6(:,6);
h=ANS_C6(:,7);
H=ANS_C6(:,8);
S1=sum(B);
sprintf('%0.6f', S1);
R2= sum(power(E,2));
S2=sqrt(R2);
sprintf('%0.6f', R2);
sprintf('%0.6f', S2);
R3= sum(power(H,2));
S3=sqrt(R3);
sprintf('%0.6f', R3);
sprintf('%0.6f', S3);
S1=sum(B);
sprintf('%0.6f', S1);
S2=sqrt(sum(power(E,2)));
sprintf('%0.6f', S2);
S3=sqrt(sum(power(H,2)));
sprintf('%0.6f', S2);
for i=1:7
ex(i)=a(i)/S1;
Ex(i)=A(i)/S1;
eX(i)=b(i)/S1;
EX(i)=B(i)/S1;
en(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(e(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
En(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(E(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
he(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(h(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
He(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(H(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
m(i)=ex(i)*log(ex(i));
T1 = sum(m);
lex6 = -T1/log(7);
M(i)=Ex(i)*log(Ex(i));
T2 = sum(M);
Hex6 = -T2/log(7);
n(i)=eX(i)*log(eX(i));
T3 = sum(n);
lEX6= -T3/log(7);
N(i)=EX(i)*log(EX(i));
T4 = sum(N);
HEX6 = -T4/log(7);
p(i) = (power(en(i),2)*log(en(i)));
w1 = sum(p);
len6 = sqrt(-w1/log(7));
P(i) = (power(En(i),2)*log(En(i)));
W1 = sum(P);
HEN6 = sqrt(-W1/log(7));
q(i) = (power(he(i),2)*log(he(i)));
z1 = sum(q);
lhe6 = sqrt(-z1/log(7));
Q(i) = (power(He(i),2)*log(He(i)));
Z1 = sum(Q);
HHE6 = sqrt(-Z1/log(7));
end
 
a=ANS_C7(:,1);
A=ANS_C7(:,2);
b=ANS_C7(:,3);
B=ANS_C7(:,4);
e=ANS_C7(:,5);
E=ANS_C7(:,6);
h=ANS_C7(:,7);
H=ANS_C7(:,8);
S1=sum(B);
sprintf('%0.6f', S1);
R2= sum(power(E,2));
S2=sqrt(R2);
sprintf('%0.6f', R2);
sprintf('%0.6f', S2);
R3= sum(power(H,2));
S3=sqrt(R3);
sprintf('%0.6f', R3);
sprintf('%0.6f', S3);
S1=sum(B);
sprintf('%0.6f', S1);
S2=sqrt(sum(power(E,2)));
sprintf('%0.6f', S2);
S3=sqrt(sum(power(H,2)));
sprintf('%0.6f', S2);
for i=1:7
ex(i)=a(i)/S1;
Ex(i)=A(i)/S1;
eX(i)=b(i)/S1;
EX(i)=B(i)/S1;
en(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(e(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
En(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(E(i),2)/(a(i)*A(i)))+((power((S2),2))/(S1*S1)));
he(i)=abs(sqrt(a(i)*A(i))/(S1*S1))*sqrt((power(h(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
He(i)=abs(sqrt(b(i)*B(i))/(S1*S1))*sqrt((power(H(i),2)/(a(i)*A(i)))+((power((S3),2))/(S1*S1)));
m(i)=ex(i)*log(ex(i));
T1 = sum(m);
lex7 = -T1/log(7);
M(i)=Ex(i)*log(Ex(i));
T2 = sum(M);
Hex7 = -T2/log(7);
n(i)=eX(i)*log(eX(i));
T3 = sum(n);
lEX7= -T3/log(7);
N(i)=EX(i)*log(EX(i));
T4 = sum(N);
HEX7 = -T4/log(7);
p(i) = (power(en(i),2)*log(en(i)));
w1 = sum(p);
len7 = sqrt(-w1/log(7));
P(i) = (power(En(i),2)*log(En(i)));
W1 = sum(P);
HEN7 = sqrt(-W1/log(7));
q(i) = (power(he(i),2)*log(he(i)));
z1 = sum(q);
lhe7 = sqrt(-z1/log(7));
Q(i) = (power(He(i),2)*log(He(i)));
Z1 = sum(Q);
HHE7 = sqrt(-Z1/log(7));
end
 
%Finding Entropy values of five criteria
R101=[lex1,Hex1,lEX1,HEX1,len1,HEN1,lhe1,HHE1];
R102=[lex2,Hex2,lEX2,HEX2,len2,HEN2,lhe2,HHE2];
R103=[lex3,Hex3,lEX3,HEX3,len3,HEN3,lhe3,HHE3];
R104=[lex4,Hex4,lEX4,HEX4,len4,HEN4,lhe4,HHE4];
R105=[lex5,Hex5,lEX5,HEX5,len5,HEN5,lhe5,HHE5];
R106=[lex6,Hex6,lEX6,HEX6,len6,HEN6,lhe6,HHE6];
R107=[lex7,Hex7,lEX7,HEX7,len7,HEN7,lhe7,HHE7];
ENTROPY_VALUE=[R101;R102;R103;R104;R105;R106;R107]
llex=ENTROPY_VALUE(:,1);
HHex=ENTROPY_VALUE(:,2);
LLEX=ENTROPY_VALUE(:,3);
HHEX=ENTROPY_VALUE(:,4);
llen=ENTROPY_VALUE(:,5);
HHEN=ENTROPY_VALUE(:,6);
llhe=ENTROPY_VALUE(:,7);
HHHE=ENTROPY_VALUE(:,8);
for i=1:7
    ex(i)= 1-HHEX(i);
    Ex(i)= 1-LLEX(i);
    eX(i)= 1-HHex(i);
    EX(i)= 1-llex(i);
end
S1=sum(EX);
sprintf('%0.6f', S1);
S2=sqrt(sum(power(HHEN,2)));
sprintf('%0.6f', S2);
S3=sqrt(sum(power(HHHE,2)));
sprintf('%0.6f', S3);
for i=1:7
exp(i) = ex(i) / S1;
Exp(i) = Ex(i) / S1;
eXP(i) = eX(i) / S1;
EXP(i) = EX(i) / S1;
ent(i)=abs(sqrt(ex(i)*Ex(i))/(S1*S1))*sqrt((power(llen(i),2)/(ex(i)*Ex(i)))+(power((S2),2))/(S1*S1));
ENT(i)=abs(sqrt(eX(i)*EX(i))/(S1*S1))*sqrt((power(HHEN(i),2)/(eX(i)*EX(i)))+(power((S2),2))/(S1*S1));
hyp(i)=abs(sqrt(ex(i)*Ex(i))/(S1*S1))*sqrt((power(llhe(i),2)/(ex(i)*Ex(i)))+(power((S3),2))/(S1*S1));
HYP(i)=abs(sqrt(eX(i)*EX(i))/(S1*S1))*sqrt((power(HHHE(i),2)/(eX(i)*EX(i)))+(power((S3),2))/(S1*S1));
end
for i=1:7
NORMALIZED_CRITERIA_OBJECTIVE_WEIGHT(i,:)=[exp(i),Exp(i),eXP(i),EXP(i),ent(i),ENT(i),hyp(i),HYP(i)];

end

CRITERIA_SUBJECTIVE_WEIGHT = [subjective_weight_criteria_1,subjective_weight_criteria_2,subjective_weight_criteria_3,subjective_weight_criteria_4,subjective_weight_criteria_5,subjective_weight_criteria_6,subjective_weight_criteria_7];

for i=1:7
NORMALIZED_CRITERIA_SUBJECTIVE_WEIGHT(i)=CRITERIA_SUBJECTIVE_WEIGHT(i)/sum(CRITERIA_SUBJECTIVE_WEIGHT);
end
NORMALIZED_CRITERIA_SUBJECTIVE_WEIGHT
NORMALIZED_CRITERIA_OBJECTIVE_WEIGHT
 
INITIAL_HYBRID_WEIGHT = zeros(7, 8);

for i = 1:7
    for j = 1:8
        if j == 1
            HW1(i) = NORMALIZED_CRITERIA_SUBJECTIVE_WEIGHT(i) * NORMALIZED_CRITERIA_OBJECTIVE_WEIGHT(i, j);
        elseif j == 2
            HW2(i) = NORMALIZED_CRITERIA_SUBJECTIVE_WEIGHT(i) * NORMALIZED_CRITERIA_OBJECTIVE_WEIGHT(i, j);
        elseif j == 3
            HW3(i) = NORMALIZED_CRITERIA_SUBJECTIVE_WEIGHT(i) * NORMALIZED_CRITERIA_OBJECTIVE_WEIGHT(i, j);
        elseif j == 4
            HW4(i) = NORMALIZED_CRITERIA_SUBJECTIVE_WEIGHT(i) * NORMALIZED_CRITERIA_OBJECTIVE_WEIGHT(i, j);
        elseif j == 5
            HW5(i) = sqrt(NORMALIZED_CRITERIA_SUBJECTIVE_WEIGHT(i)) * NORMALIZED_CRITERIA_OBJECTIVE_WEIGHT(i, j);
        elseif j == 6
            HW6(i) = sqrt(NORMALIZED_CRITERIA_SUBJECTIVE_WEIGHT(i)) * NORMALIZED_CRITERIA_OBJECTIVE_WEIGHT(i, j);
        elseif j == 7
            HW7(i) = sqrt(NORMALIZED_CRITERIA_SUBJECTIVE_WEIGHT(i)) * NORMALIZED_CRITERIA_OBJECTIVE_WEIGHT(i, j);
        elseif j == 8
            HW8(i) = sqrt(NORMALIZED_CRITERIA_SUBJECTIVE_WEIGHT(i)) * NORMALIZED_CRITERIA_OBJECTIVE_WEIGHT(i, j);
        end
    end
end

INITIAL_HYBRID_WEIGHT=[HW1; HW2; HW3; HW4; HW5; HW6; HW7; HW8]

S1=sum(HW4);
sprintf('%0.6f', S1);
S2=sqrt(sum(power(HW6,2)));
sprintf('%0.6f', S2);
S3=sqrt(sum(power(HW8,2)));
sprintf('%0.6f', S3);
for i=1:7
exp(i) = HW1(i) / S1;
Exp(i) = HW2(i) / S1;
eXP(i) = HW3(i) / S1;
EXP(i) = HW4(i) / S1;
ent(i)=abs(sqrt(HW1(i)*HW3(i))/(S1*S1))*sqrt((power(HW5(i),2)/(HW1(i)*HW3(i)))+(power((S2),2))/(S1*S1));
ENT(i)=abs(sqrt(HW2(i)*HW4(i))/(S1*S1))*sqrt((power(HW6(i),2)/(HW2(i)*HW4(i)))+(power((S2),2))/(S1*S1));
hyp(i)=abs(sqrt(HW1(i)*HW3(i))/(S1*S1))*sqrt((power(HW7(i),2)/(HW1(i)*HW3(i)))+(power((S3),2))/(S1*S1));
HYP(i)=abs(sqrt(HW2(i)*HW4(i))/(S1*S1))*sqrt((power(HW8(i),2)/(HW2(i)*HW4(i)))+(power((S3),2))/(S1*S1));
end
for i=1:7
HYBRIDWEIGHT(i,:)=[exp(i),Exp(i),eXP(i),EXP(i),ent(i),ENT(i),hyp(i),HYP(i)];
end
HYBRIDWEIGHT

%COST AND BENEFIT NORMALIZATION
a=ANS_C1(:,1);
A=ANS_C1(:,2);
b=ANS_C1(:,3);
B=ANS_C1(:,4);
e=ANS_C1(:,5);
E=ANS_C1(:,6);
h=ANS_C1(:,7);
H=ANS_C1(:,8);
S1=max(B);
S2=min(e);
S3=min(h);
for i=1:7
ex(i) = S1 / B(i);
Ex(i) = S1 / b(i);
eX(i) = S1 / A(i);
EX(i) = S1 / a(i);
en(i)=abs(sqrt((S1)^2 /(b(i)*B(i))))*sqrt(((S2/S1)^2)+(e(i)^2)/((b(i)*B(i))));
En(i)=abs(sqrt((S1)^2 /(a(i)*A(i))))*sqrt(((S2/S1)^2)+(E(i)^2)/((a(i)*A(i))));
he(i)=abs(sqrt((S1)^2 /(b(i)*B(i))))*sqrt(((S3/S1)^2)+(h(i)^2)/((b(i)*B(i))));
He(i)=abs(sqrt((S1)^2 /(a(i)*A(i))))*sqrt(((S3/S1)^2)+(H(i)^2)/((a(i)*A(i))));
end
for i=1:7
NORMCOST_C1(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),En(i),he(i),He(i)];
end
 
a=ANS_C2(:,1);
A=ANS_C2(:,2);
b=ANS_C2(:,3);
B=ANS_C2(:,4);
e=ANS_C2(:,5);
E=ANS_C2(:,6);
h=ANS_C2(:,7);
H=ANS_C2(:,8);
S1=min(a);
S2=max(E);
S3=max(H);
for i=1:7
ex(i) = S1 / B(i);
Ex(i) = S1 / b(i);
eX(i) = S1 / A(i);
EX(i) = S1 / a(i);
en(i)=abs(sqrt((S1)^2 /(b(i)*B(i))))*sqrt(((S2/S1)^2)+(e(i)^2)/((b(i)*B(i))));
En(i)=abs(sqrt((S1)^2 /(a(i)*A(i))))*sqrt(((S2/S1)^2)+(E(i)^2)/((a(i)*A(i))));
he(i)=abs(sqrt((S1)^2 /(b(i)*B(i))))*sqrt(((S3/S1)^2)+(h(i)^2)/((b(i)*B(i))));
He(i)=abs(sqrt((S1)^2 /(a(i)*A(i))))*sqrt(((S3/S1)^2)+(H(i)^2)/((a(i)*A(i))));
end
for i=1:7
NORMCOST_C2(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),En(i),he(i),He(i)];
end
 
a=ANS_C3(:,1);
A=ANS_C3(:,2);
b=ANS_C3(:,3);
B=ANS_C3(:,4);
e=ANS_C3(:,5);
E=ANS_C3(:,6);
h=ANS_C3(:,7);
H=ANS_C3(:,8);
S1=max(B);
S2=min(e);
S3=min(h);
for i=1:7
ex(i) = S1 / B(i);
Ex(i) = S1 / b(i);
eX(i) = S1 / A(i);
EX(i) = S1 / a(i);
en(i)=abs(sqrt((S1)^2 /(b(i)*B(i))))*sqrt(((S2/S1)^2)+(e(i)^2)/((b(i)*B(i))));
En(i)=abs(sqrt((S1)^2 /(a(i)*A(i))))*sqrt(((S2/S1)^2)+(E(i)^2)/((a(i)*A(i))));
he(i)=abs(sqrt((S1)^2 /(b(i)*B(i))))*sqrt(((S3/S1)^2)+(h(i)^2)/((b(i)*B(i))));
He(i)=abs(sqrt((S1)^2 /(a(i)*A(i))))*sqrt(((S3/S1)^2)+(H(i)^2)/((a(i)*A(i))));
end
for i=1:7
NORMCOST_C3(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),En(i),he(i),He(i)];
end
 
a=ANS_C4(:,1);
A=ANS_C4(:,2);
b=ANS_C4(:,3);
B=ANS_C4(:,4);
e=ANS_C4(:,5);
E=ANS_C4(:,6);
h=ANS_C4(:,7);
H=ANS_C4(:,8);
S1=max(B);
S2=min(e);
S3=min(h);
for i=1:7
ex(i) = a(i) / S1;
Ex(i) = A(i) / S1;
eX(i) = b(i) / S1;
EX(i) = B(i) / S1;
en(i)=abs(sqrt(a(i)*A(i)/(S1)^2))*sqrt((e(i)^2/(a(i)*A(i)))+(S2/S1)^2);
En(i)=abs(sqrt(b(i)*B(i)/(S1)^2))*sqrt((E(i)^2/(b(i)*B(i)))+(S2/S1)^2);
he(i)=abs(sqrt(a(i)*A(i)/(S1)^2))*sqrt((h(i)^2/(a(i)*A(i)))+(S3/S1)^2);
He(i)=abs(sqrt(b(i)*B(i)/(S1)^2))*sqrt((H(i)^2/(b(i)*B(i)))+(S3/S1)^2);
end
for i=1:7
NORMBENEFIT_C4(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),En(i),he(i),He(i)];
end
 
a=ANS_C5(:,1);
A=ANS_C5(:,2);
b=ANS_C5(:,3);
B=ANS_C5(:,4);
e=ANS_C5(:,5);
E=ANS_C5(:,6);
h=ANS_C5(:,7);
H=ANS_C5(:,8);
S1=min(a);
S2=max(E);
S3=max(H);
for i=1:7
ex(i) = a(i) / S1;
Ex(i) = A(i) / S1;
eX(i) = b(i) / S1;
EX(i) = B(i) / S1;
en(i)=abs(sqrt(a(i)*A(i)/(S1)^2))*sqrt((e(i)^2/(a(i)*A(i)))+(S2/S1)^2);
En(i)=abs(sqrt(b(i)*B(i)/(S1)^2))*sqrt((E(i)^2/(b(i)*B(i)))+(S2/S1)^2);
he(i)=abs(sqrt(a(i)*A(i)/(S1)^2))*sqrt((h(i)^2/(a(i)*A(i)))+(S3/S1)^2);
He(i)=abs(sqrt(b(i)*B(i)/(S1)^2))*sqrt((H(i)^2/(b(i)*B(i)))+(S3/S1)^2);
end
for i=1:7
NORMBENEFIT_C5(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),En(i),he(i),He(i)];
end

a=ANS_C6(:,1);
A=ANS_C6(:,2);
b=ANS_C6(:,3);
B=ANS_C6(:,4);
e=ANS_C6(:,5);
E=ANS_C6(:,6);
h=ANS_C6(:,7);
H=ANS_C6(:,8);
S1=min(a);
S2=max(E);
S3=max(H);
for i=1:7
ex(i) = a(i) / S1;
Ex(i) = A(i) / S1;
eX(i) = b(i) / S1;
EX(i) = B(i) / S1;
en(i)=abs(sqrt(a(i)*A(i)/(S1)^2))*sqrt((e(i)^2/(a(i)*A(i)))+(S2/S1)^2);
En(i)=abs(sqrt(b(i)*B(i)/(S1)^2))*sqrt((E(i)^2/(b(i)*B(i)))+(S2/S1)^2);
he(i)=abs(sqrt(a(i)*A(i)/(S1)^2))*sqrt((h(i)^2/(a(i)*A(i)))+(S3/S1)^2);
He(i)=abs(sqrt(b(i)*B(i)/(S1)^2))*sqrt((H(i)^2/(b(i)*B(i)))+(S3/S1)^2);
end
for i=1:7
NORMBENEFIT_C6(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),En(i),he(i),He(i)];
end

a=ANS_C7(:,1);
A=ANS_C7(:,2);
b=ANS_C7(:,3);
B=ANS_C7(:,4);
e=ANS_C7(:,5);
E=ANS_C7(:,6);
h=ANS_C7(:,7);
H=ANS_C7(:,8);
S1=min(a);
S2=max(E);
S3=max(H);
for i=1:7
ex(i) = a(i) / S1;
Ex(i) = A(i) / S1;
eX(i) = b(i) / S1;
EX(i) = B(i) / S1;
en(i)=abs(sqrt(a(i)*A(i)/(S1)^2))*sqrt((e(i)^2/(a(i)*A(i)))+(S2/S1)^2);
En(i)=abs(sqrt(b(i)*B(i)/(S1)^2))*sqrt((E(i)^2/(b(i)*B(i)))+(S2/S1)^2);
he(i)=abs(sqrt(a(i)*A(i)/(S1)^2))*sqrt((h(i)^2/(a(i)*A(i)))+(S3/S1)^2);
He(i)=abs(sqrt(b(i)*B(i)/(S1)^2))*sqrt((H(i)^2/(b(i)*B(i)))+(S3/S1)^2);
end
for i=1:7
NORMBENEFIT_C7(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),En(i),he(i),He(i)];
end




NORMCOST_C1
NORMCOST_C2
NORMCOST_C3
NORMBENEFIT_C4
NORMBENEFIT_C5
NORMBENEFIT_C6
NORMBENEFIT_C7

a=HYBRIDWEIGHT(:,1);
A=HYBRIDWEIGHT(:,2);
b=HYBRIDWEIGHT(:,3);
B=HYBRIDWEIGHT(:,4);
e=HYBRIDWEIGHT(:,5);
E=HYBRIDWEIGHT(:,6);
h=HYBRIDWEIGHT(:,7);
H=HYBRIDWEIGHT(:,8);
p=NORMCOST_C1(:,1);
P=NORMCOST_C1(:,2);
q=NORMCOST_C1(:,3);
Q=NORMCOST_C1(:,4);
r=NORMCOST_C1(:,5);
R=NORMCOST_C1(:,6);
t=NORMCOST_C1(:,7);
T=NORMCOST_C1(:,8);
for i=1:7
ex(i)=(a(1)*p(i));
Ex(i)=(A(1)*P(i));
eX(i)=(b(1)*q(i));
EX(i)=(B(1)*Q(i));
en(i)=0.5*sqrt((e(1)*(p(i)+P(i)))^(2) + (r(i)*(a(1)+A(1)))^(2));
EN(i)=0.5*sqrt((E(1)*(q(i)+Q(i)))^(2) + (R(i)*(b(1)+B(1)))^(2));
he(i)=0.5*sqrt((h(1)*(p(i)+P(i)))^(2) + (t(i)*(a(1)+A(1)))^(2));
HE(i)=0.5*sqrt((H(1)*(q(i)+Q(i)))^(2) + (T(i)*(b(1)+B(1)))^(2));
end
for i=1:7
WEIGHTED_NORMALIZED_C1(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),EN(i),he(i),HE(i)];
end
 
p=NORMCOST_C2(:,1);
P=NORMCOST_C2(:,2);
q=NORMCOST_C2(:,3);
Q=NORMCOST_C2(:,4);
r=NORMCOST_C2(:,5);
R=NORMCOST_C2(:,6);
t=NORMCOST_C2(:,7);
T=NORMCOST_C2(:,8);
for i=1:7
ex(i)=(a(2)*p(i));
Ex(i)=(A(2)*P(i));
eX(i)=(b(2)*q(i));
EX(i)=(B(2)*Q(i));
en(i)=0.2*sqrt((e(2)*(p(i)+P(i)))^(2) + (r(i)*(a(2)+A(2)))^(2));
EN(i)=0.2*sqrt((E(2)*(q(i)+Q(i)))^(2) + (R(i)*(b(2)+B(2)))^(2));
he(i)=0.2*sqrt((h(2)*(p(i)+P(i)))^(2) + (t(i)*(a(2)+A(2)))^(2));
HE(i)=0.2*sqrt((H(2)*(q(i)+Q(i)))^(2) + (T(i)*(b(2)+B(2)))^(2));
end
for i=1:7
WEIGHTED_NORMALIZED_C2(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),EN(i),he(i),HE(i)];
end
 
p=NORMCOST_C3(:,1);
P=NORMCOST_C3(:,2);
q=NORMCOST_C3(:,3);
Q=NORMCOST_C3(:,4);
r=NORMCOST_C3(:,5);
R=NORMCOST_C3(:,6);
t=NORMCOST_C3(:,7);
T=NORMCOST_C3(:,8);
for i=1:7
ex(i)=(a(3)*p(i));
Ex(i)=(A(3)*P(i));
eX(i)=(b(3)*q(i));
EX(i)=(B(3)*Q(i));
en(i)=0.3*sqrt((e(3)*(p(i)+P(i)))^(2) + (r(i)*(a(3)+A(3)))^(2));
EN(i)=0.3*sqrt((E(3)*(q(i)+Q(i)))^(2) + (R(i)*(b(3)+B(3)))^(2));
he(i)=0.3*sqrt((h(3)*(p(i)+P(i)))^(2) + (t(i)*(a(3)+A(3)))^(2));
HE(i)=0.3*sqrt((H(3)*(q(i)+Q(i)))^(2) + (T(i)*(b(3)+B(3)))^(2));
end
for i=1:7
WEIGHTED_NORMALIZED_C3(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),EN(i),he(i),HE(i)];
end
 
p=NORMBENEFIT_C4(:,1);
P=NORMBENEFIT_C4(:,2);
q=NORMBENEFIT_C4(:,3);
Q=NORMBENEFIT_C4(:,4);
r=NORMBENEFIT_C4(:,5);
R=NORMBENEFIT_C4(:,6);
t=NORMBENEFIT_C4(:,7);
T=NORMBENEFIT_C4(:,8);
for i=1:7
ex(i)=(a(4)*p(i));
Ex(i)=(A(4)*P(i));
eX(i)=(b(4)*q(i));
EX(i)=(B(4)*Q(i));
en(i)=0.4*sqrt((e(4)*(p(i)+P(i)))^(2) + (r(i)*(a(4)+A(4)))^(2));
EN(i)=0.4*sqrt((E(4)*(q(i)+Q(i)))^(2) + (R(i)*(b(4)+B(4)))^(2));
he(i)=0.4*sqrt((h(4)*(p(i)+P(i)))^(2) + (t(i)*(a(4)+A(4)))^(2));
HE(i)=0.4*sqrt((H(4)*(q(i)+Q(i)))^(2) + (T(i)*(b(4)+B(4)))^(2));
end
for i=1:7
WEIGHTED_NORMALIZED_C4(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),EN(i),he(i),HE(i)];
end
p=NORMBENEFIT_C5(:,1);
P=NORMBENEFIT_C5(:,2);
q=NORMBENEFIT_C5(:,3);
Q=NORMBENEFIT_C5(:,4);
r=NORMBENEFIT_C5(:,5);
R=NORMBENEFIT_C5(:,6);
t=NORMBENEFIT_C5(:,7);
T=NORMBENEFIT_C5(:,8);
for i=1:7
ex(i)=(a(5)*p(i));
Ex(i)=(A(5)*P(i));
eX(i)=(b(5)*q(i));
EX(i)=(B(5)*Q(i));
en(i)=0.5*sqrt((e(5)*(p(i)+P(i)))^(2) + (r(i)*(a(5)+A(5)))^(2));
EN(i)=0.5*sqrt((E(5)*(q(i)+Q(i)))^(2) + (R(i)*(b(5)+B(5)))^(2));
he(i)=0.5*sqrt((h(5)*(p(i)+P(i)))^(2) + (t(i)*(a(5)+A(5)))^(2));
HE(i)=0.5*sqrt((H(5)*(q(i)+Q(i)))^(2) + (T(i)*(b(5)+B(5)))^(2));
end
for i=1:7
WEIGHTED_NORMALIZED_C5(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),EN(i),he(i),HE(i)];
End
p=NORMBENEFIT_C6(:,1);
P=NORMBENEFIT_C6(:,2);
q=NORMBENEFIT_C6(:,3);
Q=NORMBENEFIT_C6(:,4);
r=NORMBENEFIT_C6(:,5);
R=NORMBENEFIT_C6(:,6);
t=NORMBENEFIT_C6(:,7);
T=NORMBENEFIT_C6(:,8);
for i=1:7
ex(i)=(a(6)*p(i));
Ex(i)=(A(6)*P(i));
eX(i)=(b(6)*q(i));
EX(i)=(B(6)*Q(i));
en(i)=0.5*sqrt((e(6)*(p(i)+P(i)))^(2) + (r(i)*(a(6)+A(6)))^(2));
EN(i)=0.5*sqrt((E(6)*(q(i)+Q(i)))^(2) + (R(i)*(b(6)+B(6)))^(2));
he(i)=0.5*sqrt((h(6)*(p(i)+P(i)))^(2) + (t(i)*(a(6)+A(6)))^(2));
HE(i)=0.5*sqrt((H(6)*(q(i)+Q(i)))^(2) + (T(i)*(b(6)+B(6)))^(2));
end
for i=1:7
WEIGHTED_NORMALIZED_C6(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),EN(i),he(i),HE(i)];
end

p=NORMBENEFIT_C7(:,1);
P=NORMBENEFIT_C7(:,2);
q=NORMBENEFIT_C7(:,3);
Q=NORMBENEFIT_C7(:,4);
r=NORMBENEFIT_C7(:,5);
R=NORMBENEFIT_C7(:,6);
t=NORMBENEFIT_C7(:,7);
T=NORMBENEFIT_C7(:,8);
for i=1:7
ex(i)=(a(7)*p(i));
Ex(i)=(A(7)*P(i));
eX(i)=(b(7)*q(i));
EX(i)=(B(7)*Q(i));
en(i)=0.5*sqrt((e(7)*(p(i)+P(i)))^(2) + (r(i)*(a(7)+A(7)))^(2));
EN(i)=0.5*sqrt((E(7)*(q(i)+Q(i)))^(2) + (R(i)*(b(7)+B(7)))^(2));
he(i)=0.5*sqrt((h(7)*(p(i)+P(i)))^(2) + (t(i)*(a(7)+A(7)))^(2));
HE(i)=0.5*sqrt((H(7)*(q(i)+Q(i)))^(2) + (T(i)*(b(7)+B(7)))^(2));
end
for i=1:7
WEIGHTED_NORMALIZED_C7(i,:)=[ex(i),Ex(i),eX(i),EX(i),en(i),EN(i),he(i),HE(i)];
end

WEIGHTED_NORMALIZED_C1
WEIGHTED_NORMALIZED_C2
WEIGHTED_NORMALIZED_C3
WEIGHTED_NORMALIZED_C4
WEIGHTED_NORMALIZED_C5
WEIGHTED_NORMALIZED_C6
WEIGHTED_NORMALIZED_C7
 
a=WEIGHTED_NORMALIZED_C1(:,1);
A=WEIGHTED_NORMALIZED_C1(:,2);
b=WEIGHTED_NORMALIZED_C1(:,3);
B=WEIGHTED_NORMALIZED_C1(:,4);
e=WEIGHTED_NORMALIZED_C1(:,5);
E=WEIGHTED_NORMALIZED_C1(:,6);
h=WEIGHTED_NORMALIZED_C1(:,7);
H=WEIGHTED_NORMALIZED_C1(:,8);
for i=1:7
    for j=1:7
        if(a(i)>=a(j))
        D(i,j)=sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        if(a(i)<a(j))
        D(i,j)=-sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        end
end
s1=sum(D,2);
D
s1
 
a=WEIGHTED_NORMALIZED_C2(:,1);
A=WEIGHTED_NORMALIZED_C2(:,2);
b=WEIGHTED_NORMALIZED_C2(:,3);
B=WEIGHTED_NORMALIZED_C2(:,4);
e=WEIGHTED_NORMALIZED_C2(:,5);
E=WEIGHTED_NORMALIZED_C2(:,6);
h=WEIGHTED_NORMALIZED_C2(:,7);
H=WEIGHTED_NORMALIZED_C2(:,8);
for i=1:7
    for j=1:7
        if(a(i)>=a(j))
        D(i,j)=sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        if(a(i)<a(j))
        D(i,j)=-sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        end
end
s2=sum(D,2);
D
s2
 
a=WEIGHTED_NORMALIZED_C3(:,1);
A=WEIGHTED_NORMALIZED_C3(:,2);
b=WEIGHTED_NORMALIZED_C3(:,3);
B=WEIGHTED_NORMALIZED_C3(:,4);
e=WEIGHTED_NORMALIZED_C3(:,5);
E=WEIGHTED_NORMALIZED_C3(:,6);
h=WEIGHTED_NORMALIZED_C3(:,7);
H=WEIGHTED_NORMALIZED_C3(:,8);
for i=1:7
    for j=1:7
        if(a(i)>=a(j))
        D(i,j)=sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        if(a(i)<a(j))
        D(i,j)=-sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        end
end
s3=sum(D,2);
D
s3
a=WEIGHTED_NORMALIZED_C4(:,1);
A=WEIGHTED_NORMALIZED_C4(:,2);
b=WEIGHTED_NORMALIZED_C4(:,3);
B=WEIGHTED_NORMALIZED_C4(:,4);
e=WEIGHTED_NORMALIZED_C4(:,5);
E=WEIGHTED_NORMALIZED_C4(:,6);
h=WEIGHTED_NORMALIZED_C4(:,7);
H=WEIGHTED_NORMALIZED_C4(:,8);
for i=1:7
    for j=1:7
        if(a(i)>=a(j))
        D(i,j)=sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        if(a(i)<a(j))
        D(i,j)=-sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        end
end
s4=sum(D,2);
D
s4
a=WEIGHTED_NORMALIZED_C5(:,1);
A=WEIGHTED_NORMALIZED_C5(:,2);
b=WEIGHTED_NORMALIZED_C5(:,3);
B=WEIGHTED_NORMALIZED_C5(:,4);
e=WEIGHTED_NORMALIZED_C5(:,5);
E=WEIGHTED_NORMALIZED_C5(:,6);
h=WEIGHTED_NORMALIZED_C5(:,7);
H=WEIGHTED_NORMALIZED_C5(:,8);
for i=1:7
    for j=1:7
        if(a(i)>=a(j))
        D(i,j)=sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        if(a(i)<a(j))
        D(i,j)=-sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        end
end
s5=sum(D,2);
D
s5
 
a=WEIGHTED_NORMALIZED_C6(:,1);
A=WEIGHTED_NORMALIZED_C6(:,2);
b=WEIGHTED_NORMALIZED_C6(:,3);
B=WEIGHTED_NORMALIZED_C6(:,4);
e=WEIGHTED_NORMALIZED_C6(:,5);
E=WEIGHTED_NORMALIZED_C6(:,6);
h=WEIGHTED_NORMALIZED_C6(:,7);
H=WEIGHTED_NORMALIZED_C6(:,8);
for i=1:7
    for j=1:7
        if(a(i)>=a(j))
        D(i,j)=sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        if(a(i)<a(j))
        D(i,j)=-sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        end
end
s6=sum(D,2);
D
S6

a=WEIGHTED_NORMALIZED_C7(:,1);
A=WEIGHTED_NORMALIZED_C7(:,2);
b=WEIGHTED_NORMALIZED_C7(:,3);
B=WEIGHTED_NORMALIZED_C7(:,4);
e=WEIGHTED_NORMALIZED_C7(:,5);
E=WEIGHTED_NORMALIZED_C7(:,6);
h=WEIGHTED_NORMALIZED_C7(:,7);
H=WEIGHTED_NORMALIZED_C7(:,8);
for i=1:7
    for j=1:7
        if(a(i)>=a(j))
        D(i,j)=sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        if(a(i)<a(j))
        D(i,j)=-sqrt((1/8)*(power((a(i)-a(j)),2)+power((A(i)-A(j)),2)+power((b(i)-b(j)),2)+power((B(i)-B(j)),2)+power((e(i)-e(j)),2)+power((E(i)-E(j)),2)+power((h(i)-h(j)),2)+power((H(i)-H(j)),2)));
        end
        end
end
s7=sum(D,2);
D
S7

S=s1+s2+s3+s4+s5+s6+s7;
S
 
 
 
 
    
  
 

