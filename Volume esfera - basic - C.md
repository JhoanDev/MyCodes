código feito com base nessa questão.
===============================================================================================================
Faça um programa que calcule e mostre o volume de uma esfera sendo fornecido o valor de seu raio (R). A fórmula para calcular o volume é: (4/3) * pi * R3. Considere (atribua) para pi o valor 3.14159.

linguagem utilizada: C
===============================================================================================================
resolution:

#include <stdio.h>

int main()
{
    double r, volume;
    scanf("%lf",&r);
    volume = (4.0/3)*3.14159*(r*r*r);
    printf("VOLUME = %.3lf\n",volume);
    return 0;
}