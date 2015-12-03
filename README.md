# proyecto-for-while
D=6;
syms Tab Tac;
Lab=3;
W=2000;
Lac=6.7;

while Lac <=6.7 | Lac>Lacmin
    X=((D^2)+(Lab^2)-(Lac^2))/(2*D*Lab);%ecuacion para hallar theta
    theta=acos(X);%Valor de thetha
    t=theta;
    Y=(Lab*sin(t))/Lac;%ecuacion para hallar phi
    phi=asin(Y);%Valor de Phi
    p=phi;
    [Tab,Tac]=solve('-Tab*cos(t)+Tac*cos(p)=0','Tab*sin(t)+Tac*sin(p)=2000');%Encotra Tab y Tac para los valores de theta y phi encontrados antes
    
    if Tab>2000 | Tac>2000
        Lacmin==Lac;
    end
    Lac=Lac-0.1;
    
end
