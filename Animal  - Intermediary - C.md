Use a função display the source blob (<>) para visualizar melhor meu código
===============================================================================================================

código feito com base nessa questão:

Neste problema, você deverá ler 3 palavras que definem o tipo de animal possível segundo o esquema abaixo, da esquerda para a direita.  Em seguida conclua qual dos animais seguintes foi escolhido, através das três palavras fornecidas.

===============================================================================================================

linguagem utilizada: C

===============================================================================================================
resolution:

    #include <stdio.h>
    #include <math.h>
    #include <string.h>

    int main(){
        char osso[20],tipo[20],alimento[20];
        scanf("%s%s%s",osso,tipo,alimento);
        if (strcmp (osso,"vertebrado") == 0){
            if (strcmp(tipo,"mamifero")==0){
                if (strcmp(alimento, "herbivoro")==0){
                    printf("vaca\n");}
                else if(strcmp(alimento, "onivoro")==0){
                    printf("homem\n");}
            }
            else if (strcmp(tipo,"ave")==0){
                if (strcmp(alimento,"carnivoro")==0){
                    printf("aguia\n");}
                else if (strcmp(alimento,"onivoro")==0){
                    printf("pomba\n");}
            }
        }
        else if (strcmp(osso,"invertebrado")==0){
            if (strcmp(tipo,"inseto")==0){
                if (strcmp(alimento,"herbivoro")==0){
                    printf("lagarta\n");}
                else if (strcmp(alimento,"hematofago")==0){
                    printf("pulga\n");}
            }
            else if (strcmp(tipo,"anelideo")==0){
                if (strcmp(alimento, "hematofago")==0){
                    printf("sanguessuga\n");}
                else if (strcmp(alimento,"onivoro")==0){
                    printf("minhoca\n");}
            }
        }
        return 0;
    }
