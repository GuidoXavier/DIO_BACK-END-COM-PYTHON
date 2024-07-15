menu = "1 - Depositar\n2 - Sacar\n3 - Extrato\n4 - Sair\n"
saldo = 0
limite_saque = 3
saque_diario = 0

while True:
    opcao = input(menu)
    match opcao:
        case "1":
            deposito = input("Quanto você deseja depositar?\n")
            if deposito.isnumeric() and float(deposito) > 0:
                saldo = saldo + float(deposito)
                print("Deposito realizado com sucesso\n")
            else:
                print("Valor inválido\n")
        case "2":
            if saque_diario >= limite_saque:
                print("Limite de saque diário atingido\n")
                pass
            else:
                saque = input("Quanto você deseja sacar?\n")
                if saque.isnumeric() and float(saque) < saldo:
                    saldo = saldo - float(saque)
                    saque_diario = saque_diario + 1
                    print("Saque realizado com sucesso\n")
                else:
                    print(
                        "Valor inválido ou você não possui saldo suficiente\n")
        case "3":
            print("Seu saldo é de: ", saldo, "\n")
        case "4":
            print("Obrigado por usar nosso sistema. \nDesligando...")
            break
        case _:
            print("Opção inválida\nPor favor tente outra")
