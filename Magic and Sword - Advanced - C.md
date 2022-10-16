código feito com base nessa questão:
=====

No tower defense Magic and Sword, o jogador pode lançar magias de área para derrotar as unidades inimigas. As magias são elementais: fogo, água, ar e terra, e a região afetada é determinada por um círculo cujo raio depende do nível da magia.

A tabela abaixo lista cada magia, o dano e o respectivo raio por nível:

Magia | Dano | Lv1 | lv2 | lv3

Fire | 200 | 20 | 30 | 50

Water | 300 | 10 | 25 | 40

Earth | 400 | 25 | 55 | 70

Air | 100 | 18 | 38 | 60

As unidades inimigas são delimitadas por um retângulo de largura w e altura h, com canto inferior esquerdo posicionado no ponto (x0, y0). O inimigo sofrerá dano caso seu retângulo delimitador tenha qualquer intercessão com a área deﬁnida pelo círculo da magia.

Dada a posição e o retângulo delimitador da unidade inimiga, o centro da explosão e o identiﬁcador e o nível da magia, determine o dano sofrido pela unidade. Caso a unidade esteja fora do alcance da magia, o dano sofrido é igual a zero.

*linguagem utilizada: C*

Resolution:
=====
    #include <stdio.h>
    #include <math.h>
    #include <string.h>

    struct magic_t
    {
        char type[10];
        int power;
        int cordenadaX, cordenadaY;
    };

    #define max(a, b) ((a > b) ? a : b) // se a for maior que b max retornará (a) caso contrario (b)
    #define min(a, b) ((a < b) ? a : b) // se a for menor que b min retornará (a) caso contrario (b)

    double distance(int x, int y);

    int point_near(int dxy, int xy, int mxy, int la);

    int area_power_fire(int p, int ap);
    int area_power_water(int p, int ap);
    int area_power_earth(int p, int ap);
    int area_power_air(int p, int ap);

    int main()
    {
        int teste, largura, altura, x0, y0, areapower, dx, dy;
        scanf("%d", &teste);
        struct magic_t magic; // puxando a estrutura
        for (teste; teste > 0; teste--)
        { // quantidade de testes
            scanf("%d %d %d %d", &largura, &altura, &x0, &y0);
            scanf("%s %d %d %d", magic.type, &magic.power, &magic.cordenadaX, &magic.cordenadaY);
            // dx e dy é a coordenada do ponto sobre ou dentro do retângulo mais próximo do centro do círculo
            dx = point_near(dx, x0, magic.cordenadaX, largura);
            dy = point_near(dy, y0, magic.cordenadaY, altura);

            if (strcmp(magic.type, "fire") == 0)
            {
                if (distance(dx, dy) <= area_power_fire(magic.power, areapower))// testando se a area de efeito toca no retângulo
                { 
                    printf("200\n");
                }
                else
                {
                    printf("0\n");
                }
            }
            else if (strcmp(magic.type, "water") == 0)
            {
                if (distance(dx, dy) <= area_power_water(magic.power, areapower))
                {
                    printf("300\n");
                }
                else
                {
                    printf("0\n");
                }
            }
            else if (strcmp(magic.type, "earth") == 0)
            {
                if (distance(dx, dy) <= area_power_earth(magic.power, areapower))
                {
                    printf("400\n");
                }
                else
                {
                    printf("0\n");
                }
            }
            else if (strcmp(magic.type, "air") == 0)
            {
                if (distance(dx, dy) <= area_power_air(magic.power, areapower))
                {
                    printf("100\n");
                }
                else
                {
                    printf("0\n");
                }
            }
        }
        return 0;
    }

    double distance(int x, int y)
    {
        return (sqrt((x * x) + (y * y)));
    }
    int point_near(int dxy, int xy, int mxy, int la)
    {
        dxy = max(xy, min(mxy, xy + la));
        return (dxy - mxy);
    }

    int area_power_fire(int p, int ap)
    {
        switch (p)
        { // area de ataque do meu poder de acordo com o tipo
        case 1:
            ap = 20;
            break;
        case 2:
            ap = 30;
            break;
        case 3:
            ap = 50;
            break;
        default:
            break;
        }
        return (ap);
    }

    int area_power_water(int p, int ap)
    {
        switch (p)
        {
        case 1:
            ap = 10;
            break;
        case 2:
            ap = 25;
            break;
        case 3:
            ap = 40;
            break;
        default:
            break;
        }
        return (ap);
    }

    int area_power_earth(int p, int ap)
    {
        switch (p)
        {
        case 1:
            ap = 25;
            break;
        case 2:
            ap = 55;
            break;
        case 3:
            ap = 70;
            break;
        default:
            break;
        }
        return (ap);
    }

    int area_power_air(int p, int ap)
    {
        switch (p)
        {
        case 1:
            ap = 18;
            break;
        case 2:
            ap = 38;
            break;
        case 3:
            ap = 60;
            break;
        default:
            break;
        }
        return (ap);
    }