# TPC2

## Autor
Catarina Pereira Costa, A111924, (![foto](foto.jpeg))

## Resumo
Resolução do jogo "Adivinha o número" de 0 a 100 em que há opção de jogar o utilizador ou o computador.
O objetivo é adivinhar o número com o mínimo de tentativas possível (7), utilizando a regra de divisão binária.

## Resultados
* Res1 
import random

def joga_computador():
    print("Utilizador pensa num número de 0 a 100")

    lim_inf = 0
    lim_sup = 100
    acertou = False
    while lim_inf <= lim_sup and not acertou:
        tentativa = (lim_inf + lim_sup) // 2

        print(f"Tentativa: O número que escolheste foi o {tentativa}")
        resposta = input("O teu número é >, < ou =? ").strip()

        if resposta == "=":
            print(f"Acertei! O teu número é o {tentativa}")
            acertou = True
        elif resposta == ">":
            lim_inf = tentativa + 1
        elif resposta == "<":
            lim_sup = tentativa - 1

def joga_utilizador():
    print("Computador pensa num número de 0 a 100!")

    n_computador = random.randint(0, 100)
    acertou = False
    while not acertou:
        tentativa = int(input("Qual achas que é o meu número? "))


        if tentativa == n_computador:
            print(f"Acertaste! O meu número é o {n_computador}!")
            acertou = True
        elif tentativa < n_computador:
            print("O meu número é MAIOR.")
        elif tentativa > n_computador:
            print("O meu número é MENOR.")


def menu():
    a_jogar = True
    while a_jogar:
        print("\n--- ADIVINHA O NÚMERO (0 a 100) ---")
        print("1 - O computador adivinha o número do utilizador")
        print("2 - Utilizador adivinha o número do computador")
        print("3 - Sair")
        
        opcao = input("Escolhe uma opção (1-3): ").strip()
        
        if opcao == "1":
            joga_computador()
        elif opcao == "2":
            joga_utilizador()
        elif opcao == "3":
            print("A sair do jogo. Até à próxima!")
            a_jogar = False
        else:
            print("Opção inválida. Tenta novamente.")



if __name__ == "__main__":
    menu()