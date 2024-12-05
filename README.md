import keyboard
import time

# Definir o Menu Interativo
class Menu:
    def __init__(self):
        self.is_active = False
        self.options = {
            1: "Pegar Bola (Tecla F)",
            2: "Fazer Gol (Tecla G)",
            3: "Ativar Hitbox de 200",
            4: "Fechar Menu"
        }

    def show(self):
        print("Menu Interativo:")
        for key, value in self.options.items():
            print(f"{key}. {value}")
        print("\nPressione o número da opção para selecionar:")

    def select_option(self, option):
        if option == 1:
            print("Função de pegar bola ativada!")
            self.pegar_bola()
        elif option == 2:
            print("Função de fazer gol ativada!")
            self.fazer_gol()
        elif option == 3:
            print("Hitbox de 200 ativada!")
            self.ativar_hitbox()
        elif option == 4:
            self.is_active = False
            print("Menu fechado.")
        else:
            print("Opção inválida!")

    def pegar_bola(self):
        # Lógica para pegar a bola com a tecla F
        while True:
            if keyboard.is_pressed('f'):
                print("Bola pega!")
                break
            time.sleep(0.1)

    def fazer_gol(self):
        # Lógica para fazer gol com a tecla G
        while True:
            if keyboard.is_pressed('g'):
                print("Gol marcado!")
                break
            time.sleep(0.1)

    def ativar_hitbox(self):
        # Simula a ativação de uma hitbox de 200
        print("Hitbox ativada com tamanho 200.")
        # Aqui você pode adicionar mais lógica para a hitbox, como alterar o comportamento do personagem

def main():
    menu = Menu()
    while True:
        if not menu.is_active:
            menu.show()
            try:
                option = int(input("Escolha uma opção: "))
                menu.select_option(option)
            except ValueError:
                print("Por favor, insira um número válido.")
            time.sleep(1)
        else:
            time.sleep(0.1)

if __name__ == "__main__":
    main()
