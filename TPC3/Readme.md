# TPC3

## Autor
Catarina Pereira Costa, A111924, (![foto](foto.jpeg))

## Resumo
Resolução do jogo "Corrida para o 100" em que o objetivo é ir escolhendo números inteiros de 1 a 10 alternadamente, utilizador e computador, e que o vencedor seja o que chega a 100 primeiro. 
Há a opção de escolher quem começa a jogar.

## Resultados
* Res1 
print("Bem vindo ao jogo CORRIDA PARA O 100!")
print("Em cada jogada podes escolher qualquer número inteiro de 1 a 10.")
print("O primeiro a chegar a 100 ganha, BOA SORTE!")

#Decidir quem começa a jogar ("c" - computador; "u" - utilizador)
jogador_1 = input("Quem vai jogar primeiro?  ")

while jogador_1 != "c" and jogador_1 != "u":
    jogador_1 = input("Resposta inválida. Escreva c para computador ou u para utilizador: ")


total = 0
while total < 100:
    if jogador_1 == "c": #computador começa
        faltam = 100 - total
        jogada_computador = faltam % 11

        if jogada_computador == 0:
            jogada_computador = 1

        total = total + jogada_computador
        print(f"Computador: {jogada_computador}. Total atual: {total}")

        if total != 100:
            jogada_utilizador = int(input("Escolhe um número inteiro de 1 a 10: "))

            while jogada_utilizador < 1 or jogada_utilizador > 10 or (total + jogada_utilizador > 100):
                print("Jogada inválida! Escolhe um valor entre 1 e 10 que não ultrapasse 100.")
                jogada_utilizador = int(input("Escolhe um número inteiro de 1 a 10: "))
            
            total = total + jogada_utilizador
            print(f"Utilizador = {jogada_utilizador}. Total atual: {total}")
        else:
            print("O computador ganhou!")

    else: #utilizador começa
        jogada_utilizador = int(input("Escolhe um número inteiro de 1 a 10: "))
        
        while jogada_utilizador < 1 or jogada_utilizador > 10 or (total + jogada_utilizador > 100):
                print("Jogada inválida! Escolhe um valor entre 1 e 10 que não ultrapasse 100.")
                jogada_utilizador = int(input("Escolhe um número inteiro de 1 a 10: "))
        
        total = total + jogada_utilizador
        print(f"Utilizador = {jogada_utilizador}. Total atual: {total}")


        if total != 100:
            faltam = 100 - total
            jogada_computador = faltam % 11

            if jogada_computador == 0: 
                jogada_computador = 1

            total = total + jogada_computador
            print(f"Computador: {jogada_computador}. Total atual: {total}")

            if total == 100:
                print("O computador ganhou!")
        else:
            print("O utilizador ganhou!")