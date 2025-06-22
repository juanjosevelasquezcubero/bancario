#Sistema bancario basico
>Funcionalidades : deposito , extrato , saque , saida do app
# Banco Amazonia

#menu = """Banco Amazonia
#1.Depositar
#2.Sacar
#3.Extrato
#4.Sair
=>  """
saldo = 0
extrato = ""
saque = 0
tentativas = 3
LIMITE_SAQUE = 500
while True:
    try:
        opcao = int(input(menu))

        if opcao == 1:
            deposito = float(
                input('informe o valor do saldo a depositar =>  '))
            if deposito > 0:
                saldo = deposito
                extrato = f'seu deposito foi R$ {deposito:.2f}\t'
                print(extrato)
            elif deposito <= 0:
                print('quantidade informada invalida')

        elif opcao == 2:

            if saque >= tentativas:
                print("excedeu seu limite de tentativas")
            else:
                sacar = float(input('digite o saldo que deseja sacar => '))
            if sacar > saldo:
                print('valor do saque maior que seu saldo')
            elif sacar > LIMITE_SAQUE:
                print("o valor excedeu o total de R$ 500 disponivel para saque")
            elif sacar <= 0:
                print("valor de saque invalido!!")
            else:
                saldo -= sacar
                extrato = f'seu deposito  foi R$ {deposito:.2f}|seu saque foi {sacar:.2f}'
                saque += 1
        elif opcao == 3:
            print('******extrato******')
            print(extrato if extrato else 'nenhuma transacao feita')
            print(f'seu saldo e {saldo:.2f}')
            print("*******************")

        elif opcao == 4:
            print('saindo')
            break
        else:
            print('opcao invalida seleccione nuevamente una opcion')
    except:
        print("operacion invalida")



