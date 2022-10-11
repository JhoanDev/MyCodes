código feito com base nessa questão:
=====

Leia a hora inicial, minuto inicial, hora final e minuto final de um jogo. A seguir calcule a duração do jogo.

Obs: O jogo tem duração mínima de um (1) minuto e duração máxima de 24 horas.

*linguagem utilizada: C*

Resolution:

=====

    #include <stdio.h>
    int main()
    {
        int a,b,c,d,dif;
        scanf("%d %d %d %d", &a, &c, &b, &d);
        dif = ((b*60)+d) - ((a*60)+c);
        if(dif<=0) dif += 24*60;
        printf("O JOGO DUROU %d HORA(S) E %d MINUTO(S)\n", dif/60, dif%60);
        return 0;
    }