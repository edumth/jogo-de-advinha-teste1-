#include <stdio.h>
#include <time.h>

//--------------------------------------------------

void dicas(int number, int password, int attempt);

int main()
{
    int continuar=1,
        password,
        attempt,
        number,
        escolha;

    do
    {
        printf("Escolha um numero inteiro entre 1 a 10\n");
        scanf("%d", &password);

        printf("Comecou! Tente adivinhar o numero!\n\n");
        attempt = 0;

        do
        {
            attempt++;
            printf("Tentativa %d: ", attempt);
            scanf("%d", &number);
            dicas(number,password,attempt);
        }
        while( number != password);

        printf("Digite 0 para sair, ou qualquer outro numero para continuar: ");
        scanf("%d", &continuar);
    }
        while(continuar);

}

void dicas(int number, int password, int attempt)
{
        if(number > password)
            printf("O numero sorteado e menor que %d\n\n", number);
        else
        if(number < password)
            printf("O numero sorteado e maior que %d\n\n", number);
        else
            printf("Parabens! Voce acertou o numero em %d tentativas!\n\n", attempt);
}

