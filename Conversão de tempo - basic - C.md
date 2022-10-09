Use a função display the source blob (<>) para visualizar melhor meu código!
===============================================================================================================
<<<<<<< HEAD
código feito com base nessa questão:

Leia um valor inteiro, que é o tempo de duração em segundos de um determinado evento em uma fábrica, e informe-o expresso no formato horas:minutos:segundos.
===============================================================================================================
=======
Leia um valor inteiro, que é o tempo de duração em segundos de um determinado evento em uma fábrica,
e informe-o expresso no formato horas:minutos:segundos.
 
>>>>>>> 5cf0879bf0f346bf549da333915a622005eeaa69
linguagem utilizada: C
===============================================================================================================
resolution:
 
#include<stdio.h>

int main(){
	int d,m,a,dd;
	scanf("%d",&d);
	a = d/3600;
	m = (d - a*3600)/60;
	dd = d - (a*3600 + m*60);
	printf("%d:%d:%d\n",a,m,dd);
    return 0;
}
