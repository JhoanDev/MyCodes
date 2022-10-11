código feito com base nessa questão:
=====

Faça um programa que leia o nome de um vendedor, o seu salário fixo e o total de vendas efetuadas por ele no mês (em dinheiro).

Sabendo que este vendedor ganha 15% de comissão sobre suas vendas efetuadas, informar o total a receber no final do mês, com duas casas decimais.

*linguagem utilizada: C*

Resolution:
=====

    #include <stdio.h>

    int main(){
    
        char f[1000];
        double v,fx;
        scanf("%s %lf %lf",f,&fx,&v);

        double comissao = v*0.15;
        double total = comissao+fx;

        printf("TOTAL = R$ %.2lf\n",total);
        return 0;
    }
