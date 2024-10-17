Jogo Adivinhação com Limite de Tentativas:



import random

def jogo_adivinhacao():
    numero_secreto = random.randint(1, 100)
    tentativas_restantes = 5
    print("Bem-vindo ao jogo de adivinhação!")
    print("Tente adivinhar o número secreto entre 1 e 100.")
    print(f"Você tem {tentativas_restantes} tentativas.")

    while tentativas_restantes > 0:
        try:
            palpite = int(input("Digite seu palpite: "))
        except ValueError:
            print("Por favor, insira um número válido.")
            continue

        if palpite < 1 or palpite > 100:
            print("O número deve estar entre 1 e 100.")
            continue

        tentativas_restantes -= 1

        if palpite == numero_secreto:
            print(f"Parabéns! Você adivinhou o número {numero_secreto}!")
            break
        elif palpite < numero_secreto:
            print("O número secreto é maior.")
        else:
            print("O número secreto é menor.")

        if tentativas_restantes > 0:
            print(f"Você ainda tem {tentativas_restantes} tentativas.")
        else:
            print(f"Suas tentativas acabaram! O número secreto era {numero_secreto}.")

# Executa o jogo
jogo_adivinhacao()
