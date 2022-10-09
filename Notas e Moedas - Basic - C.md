Use a função display the source blob (<>) para visualizar melhor meu código!
===============================================================================================================
código feito com base nessa questão.

Leia um valor de ponto flutuante com duas casas decimais. Este valor representa um valor monetário. A seguir, calcule o menor número de notas e moedas possíveis no qual o valor pode ser decomposto. As notas consideradas são de 100, 50, 20, 10, 5, 2. As moedas possíveis são de 1, 0.50, 0.25, 0.10, 0.05 e 0.01. A seguir mostre a relação de notas necessárias.
===============================================================================================================

linguagem utilizada: C
===============================================================================================================
resolution:

#include <stdio.h>
#include <math.h>

int main (){
	int a,b,c,e,f,g,t;
    float d ;
    scanf("%f",&d);
	if (d>=0 && d<=1000000.00){
	a = d/100;
	b = (d-(a*100))/50;
	c = (d - (a*100 + b*50))/20;
	e = (d - (a*100 + b*50 + c*20))/10;
	f = (d - (a*100 + b*50 + c*20 + e*10))/5;
	g = (d - (a*100 + b*50 + c*20 + e*10 + f*5))/2;	
	
	printf("NOTAS:\n");
	printf("%d nota(s) de R$ 100.00\n",a);
	printf("%d nota(s) de R$ 50.00\n",b);
	printf("%d nota(s) de R$ 20.00\n",c);
	printf("%d nota(s) de R$ 10.00\n",e);
	printf("%d nota(s) de R$ 5.00\n",f);
	printf("%d nota(s) de R$ 2.00\n",g);
	
	int h = (d - (a*100 + b*50 + c*20 + e*10 + f*5 + g*2));
	int i = (d - (a*100 + b*50 + c*20 + e*10 + f*5 + g*2 + h))*2;
	int j = (d - (a*100 + b*50 + c*20 + e*10 + f*5 + g*2 + h + i/2.0))*4;
	int k = (d - (a*100 + b*50 + c*20 + e*10 + f*5 + g*2 + h + i/2.0 + j/4.0))*10;
	int l = (d - (a*100 + b*50 + c*20 + e*10 + f*5 + g*2 + h + i/2.0 + j/4.0 + k/10.0))*20;
	float m = (d - (a*100 + b*50 + c*20 + e*10 + f*5 + g*2 + h + i/2.0 + j/4.0 + k/10.0 + l/20.0))*100;
	int z = round(m);
	printf("MOEDAS:\n");
	printf("%d moeda(s) de R$ 1.00\n",h);
	printf("%d moeda(s) de R$ 0.50\n",i);
	printf("%d moeda(s) de R$ 0.25\n",j);
	printf("%d moeda(s) de R$ 0.10\n",k);
	printf("%d moeda(s) de R$ 0.05\n",l);
	printf("%d moeda(s) de R$ 0.01\n",z);
}
	return 0;
}