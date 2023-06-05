# VendingMachine
//VENDING MACHINE - PROJETO AVALIATIVO SEMESTRAL
//NOME: JUAN SOARES DOS REIS
//RA: 2840482313001

#include <iostream>
using namespace std;

int main() {
  int Opcao_Consumidor; // Primeira decisão que o usuário toma
  int Opcao_Administrador; // Opção para o Administrador
  int Add_Bebidas; // Opção para o Administrador controlar a quantidade de bebidas
  int Bebida_Adicionada; // Qual bebida o Administrador adicionou
  int Quantidade_Bebidas_Cliente; // Quantas bebidas o cliente irá retirar
  int Valor_Inserido_Cliente; // Valor inserido pelo cliente
  double Faturamento_Total = 0; // Informacoes financeiras a respeito do faturamento que a vending já vendeu
  double Pode_Faturar = 0; // Informacoes financeiras a respeito de quanto a vending ainda pode faturar
  int Senha_Administrador; //Senha administrador pré setada pelo proprio programa

  // Bebidas comecam com zero no estoque, é adicionada conforme o administrador gerencia a vending machine
  int Coca_Cola = 0, Pepsi = 0, Guarana_Antartica = 0, Redbull = 0, Agua = 0, Guarana_Jesus = 0, Coca_Zero = 0, Cha_Mate = 0, Sprite = 0;

  //Vale ressaltar que não há verificacoes para numeros negativos pois na vending machine nao ha como digitar valor menor que zero

  // Loop principal
inicio:
  cout << "Ola, essa eh a Vending Machine Fatequiana!" << endl;
  cout << "Informe o codigo do produto desejado:\n" << endl;
  cout << "1 - R$5,00 - Coca-Cola " << endl;
  cout << "2 - R$4,50 - Pepsi" << endl;
  cout << "3 - R$4,50 - Guarana Antartica" << endl;
  cout << "4 - R$8,00 - Redbull" << endl;
  cout << "5 - R$3,00 - Agua" << endl;
  cout << "6 - R$4,50 - Guarana Jesus" << endl;
  cout << "7 - R$5,00 - Coca-Cola Zero" << endl;
  cout << "8 - R$5,00 - Cha Mate" << endl;
  cout << "9 - R$4,50 - Sprite" << endl;
  cout << "0 - Administrador" << endl;
  cin >> Opcao_Consumidor;

  //Se a opcao digitada for maior que nove, o código exibe inválido e retorna para inicio - já que o máximo de bebidas que a vending possui é 9
  if (Opcao_Consumidor > 9) {
    cout << "Opcao invalida!" << endl;
    goto inicio;
  }

  // Cliente escolhe a quantidade da bebida desejada caso não selecione a opção de administrador
  else if (Opcao_Consumidor != 0) {
    cout << "Digite a quantidade de bebidas: " << endl;
    cout << "Digite 0 para retornar" << endl;
    cin >> Quantidade_Bebidas_Cliente;

   // Caso se arrependa da opção, ainda pode retornar para a página inicial
    if (Quantidade_Bebidas_Cliente == 0) {
      goto inicio;
    }

    // Diminui a quantidade de bebidas escolhidas pelo cliente e apresenta a mensagem para retirar a bebida
    // Caso não tenha a quantidade que o cliente deseja, uma mensagem de erro é apresentada e volta para inicio
    // O usario digita o valor que foi inserido, é calculado se é sufuciente e se há troco - exibindo também o troco
    // O valor da venda é somada com o faturamento total da vending
    // Depois, o cliente retorna para a inicio
    switch (Opcao_Consumidor) {

      case 1:
        if (Coca_Cola >= Quantidade_Bebidas_Cliente) {
        cout << "O total eh R$" << Quantidade_Bebidas_Cliente * 5 << endl;
        cout << "Digite a quantia inserida" << endl;
        cin >> Valor_Inserido_Cliente;

        if (Valor_Inserido_Cliente >= Quantidade_Bebidas_Cliente * 5) {
        cout << "Retire a bebida e seu troco de R$" << Valor_Inserido_Cliente - Quantidade_Bebidas_Cliente * 5 << endl;
        Coca_Cola -= Quantidade_Bebidas_Cliente;
        Faturamento_Total += Quantidade_Bebidas_Cliente * 5;
        } else {
         cout << "Valor insuficiente." << endl;
        }

       } else if (Coca_Cola == 0) {
       cout << "Nos desculpe, estamos sem nenhuma lata de Coca-Cola" << endl;
       } else {
       cout << "Nos desculpe, temos apenas " << Coca_Cola << " lata(s) de Coca-Cola." << endl;
       }
    goto inicio;

    case 2:
      if (Pepsi >= Quantidade_Bebidas_Cliente) {
      cout << "O total eh R$" << Quantidade_Bebidas_Cliente * 4.5 << endl;
      cout << "Digite a quantia inserida" << endl;
      cin >> Valor_Inserido_Cliente;

      if (Valor_Inserido_Cliente >= Quantidade_Bebidas_Cliente * 4.5) {
      cout << "Retire a bebida e seu troco de R$" << Valor_Inserido_Cliente - Quantidade_Bebidas_Cliente * 4.5 << endl;
      Pepsi -= Quantidade_Bebidas_Cliente;
      Faturamento_Total += Quantidade_Bebidas_Cliente * 4.5;
      } else {
      cout << "Valor insuficiente." << endl;
      }
  
      } else if (Pepsi == 0){
      cout << "Nos desculpe, estamos sem nenhuma lata de Pepsi." << endl;
      } else {
      cout << "Nos desculpe, temos apenas " << Pepsi << " lata(s) de Pepsi." << endl;
      }
    goto inicio;
          
    case 3:
      if (Guarana_Antartica >= Quantidade_Bebidas_Cliente) {
      cout << "O total é R$" << Quantidade_Bebidas_Cliente * 4.5 << endl;
      cout << "Digite a quantia inserida" << endl;
      cin >> Valor_Inserido_Cliente;

      if (Valor_Inserido_Cliente >= Quantidade_Bebidas_Cliente * 4.5) {
      cout << "Retire a bebida e seu troco de R$" << Valor_Inserido_Cliente - Quantidade_Bebidas_Cliente * 4.5 << endl;
      Guarana_Antartica -= Quantidade_Bebidas_Cliente;
      Faturamento_Total += Quantidade_Bebidas_Cliente * 4.5;
      } else {
      cout << "Valor insuficiente." << endl;
      }

      } else if (Guarana_Antartica == 0){
      cout << "Nos desculpe, estamos sem nenhuma lata de Guaraná Antartica." << endl;
      } else {
      cout << "Nos desculpe, temos " << Guarana_Antartica << " unidades de Guaraná Antártica." << endl;
      }
    goto inicio;

    case 4:
      if (Redbull >= Quantidade_Bebidas_Cliente) {
      cout << "O total é R$" << Quantidade_Bebidas_Cliente * 8 << endl;
      cout << "Digite a quantia inserida" << endl;
      cin >> Valor_Inserido_Cliente;

      if (Valor_Inserido_Cliente >= Quantidade_Bebidas_Cliente * 8) {
      cout << "Retire a bebida e seu troco de R$" << Valor_Inserido_Cliente - Quantidade_Bebidas_Cliente * 8 << endl;
      Redbull -= Quantidade_Bebidas_Cliente;
      Faturamento_Total += Quantidade_Bebidas_Cliente * 8;
      } else {
      cout << "Valor insuficiente." << endl;
      }

      } else if (Redbull == 0){
      cout << "Nos desculpe, estamos sem nenhuma lata de Redbull." << endl;
      } else {
      cout << "Nos desculpe, temos " << Redbull << " unidades de Red Bull." << endl;
      }
    goto inicio;

    case 5:
      if (Agua >= Quantidade_Bebidas_Cliente) {
      cout << "O total é R$" << Quantidade_Bebidas_Cliente * 3 << endl;
      cout << "Digite a quantia inserida" << endl;
      cin >> Valor_Inserido_Cliente;

      if (Valor_Inserido_Cliente >= Quantidade_Bebidas_Cliente * 3) {
      cout << "Retire a bebida e seu troco de R$" << Valor_Inserido_Cliente - Quantidade_Bebidas_Cliente * 3 << endl;
      Agua -= Quantidade_Bebidas_Cliente;
      Faturamento_Total += Quantidade_Bebidas_Cliente * 3;
      } else {
      cout << "Valor insuficiente." << endl;
      }

      } else if (Agua == 0){
      cout << "Nos desculpe, estamos sem nenhuma garrafa de agua." << endl;
      } else {
      cout << "Nos desculpe, temos " << Agua << " unidades de Água." << endl;
      }
    goto inicio;

    case 6:
      if (Guarana_Jesus >= Quantidade_Bebidas_Cliente) {
      cout << "O total é R$" << Quantidade_Bebidas_Cliente * 4.5 << endl;
      cout << "Digite a quantia inserida" << endl;
      cin >> Valor_Inserido_Cliente;

      if (Valor_Inserido_Cliente >= Quantidade_Bebidas_Cliente * 4.5) {
      cout << "Retire a bebida e seu troco de R$" << Valor_Inserido_Cliente - Quantidade_Bebidas_Cliente * 4.5 << endl;
      Guarana_Jesus -= Quantidade_Bebidas_Cliente;
      Faturamento_Total += Quantidade_Bebidas_Cliente * 4.5;
      } else {
      cout << "Valor insuficiente." << endl;
      }

      } else if (Guarana_Jesus == 0){
      cout << "Nos desculpe, estamos sem nenhuma lata de Guaraná Jesus." << endl;
      } else {
     cout << "Nos desculpe, temos apenas " << Guarana_Jesus << " lata(s) de Guaraná Jesus." << endl;
      }
    goto inicio;

    case 7:
      if (Coca_Zero >= Quantidade_Bebidas_Cliente) {
      cout << "O total é R$" << Quantidade_Bebidas_Cliente * 5 << endl;
      cout << "Digite a quantia inserida" << endl;
      cin >> Valor_Inserido_Cliente;

      if (Valor_Inserido_Cliente >= Quantidade_Bebidas_Cliente * 5) {
      cout << "Retire a bebida e seu troco de R$" << Valor_Inserido_Cliente - Quantidade_Bebidas_Cliente * 5 << endl;
      Coca_Zero -= Quantidade_Bebidas_Cliente;
      Faturamento_Total += Quantidade_Bebidas_Cliente * 5;
      } else {
      cout << "Valor insuficiente." << endl;
      }

      } else if (Coca_Zero == 0){
      cout << "Nos desculpe, estamos sem nenhuma lata de Coca-Cola Zero." << endl;
      } else {
      cout << "Nos desculpe, temos apenas" << Coca_Zero << " lata(s) de Coca-Cola Zero." << endl;
      }
    goto inicio;

    case 8:
      if (Cha_Mate >= Quantidade_Bebidas_Cliente) {
      cout << "O total é R$" << Quantidade_Bebidas_Cliente * 5 << endl;
      cout << "Digite a quantia inserida" << endl;
      cin >> Valor_Inserido_Cliente;

      if (Valor_Inserido_Cliente >= Quantidade_Bebidas_Cliente * 5) {
      cout << "Retire a bebida e seu troco de R$" << Valor_Inserido_Cliente - Quantidade_Bebidas_Cliente * 5 << endl;
      Cha_Mate -= Quantidade_Bebidas_Cliente;
      Faturamento_Total += Quantidade_Bebidas_Cliente * 5;
      } else {
      cout << "Valor insuficiente." << endl;
     }

     } else if (Cha_Mate == 0){
      cout << "Nos desculpe, estamos sem nenhuma lata de Cha Mate." << endl;
      }
     else {
     cout << "Nos desculpe, temos apenas " << Cha_Mate << " lata(s) de Chá Mate." << endl;
     }
    goto inicio;

    case 9:
      if (Sprite >= Quantidade_Bebidas_Cliente) {
      cout << "O total é R$" << Quantidade_Bebidas_Cliente * 4 << endl;
      cout << "Digite a quantia inserida" << endl;
      cin >> Valor_Inserido_Cliente;

      if (Valor_Inserido_Cliente >= Quantidade_Bebidas_Cliente * 4) {
      cout << "Retire a bebida e seu troco de R$" << Valor_Inserido_Cliente - Quantidade_Bebidas_Cliente * 4 << endl;
      Sprite -= Quantidade_Bebidas_Cliente;
      Faturamento_Total += Quantidade_Bebidas_Cliente * 4;
      } else {
      cout << "Valor insuficiente." << endl;
      }

      } else if (Sprite == 0){
      cout << "Nos desculpe, estamos sem nenhuma lata de Sprite." << endl;
      }else {
      cout << "Nos desculpe, temos apenas " << Sprite << " lata(s) de Sprite." << endl;
      }
    goto inicio;

    //Se a opcao escolhida nao forem nenhuma daquelas exibidas:
    default:
     cout << "Opção inválida!" << endl;
     goto inicio;
   }
 
    //Se digitado 0 vamos para o administrador, que precisa de uma senha
    } else {
      cout << "Ola administrador, digite sua senha:" << endl;
      cin >> Senha_Administrador;
      if (Senha_Administrador == 123){

      //O administrador pode escolher o que quer fazer:
      cout << "Selecione a opção desejada:" << endl;
      cout << "1 - Repor o Estoque" << endl;
      cout << "2 - Estoque de bebidas" << endl;
      cout << "3 - Informacoes financeiras" << endl;
      cout << "0 - Retornar" << endl;
      cin >> Opcao_Administrador;

      switch (Opcao_Administrador) {
        // Case 1 - Administrador irá repor a Vending Machine, selecionando a qual bebida e a quantidade
        case 1:

          cout << "Qual bebida deseja adicionar?" << endl;
          cout << "1 - Coca-Cola" << endl;
          cout << "2 - Pepsi" << endl;
          cout << "3 - Guarana Antartica" << endl;
          cout << "4 - Redbull" << endl;
          cout << "5 - Agua" << endl;
          cout << "6 - Guarana Jesus" << endl;
          cout << "7 - Coca-Cola Zero" << endl;
          cout << "8 - Cha Mate" << endl;
          cout << "9 - Sprite" << endl;
          cin >> Bebida_Adicionada;

          cout << "Quantos produtos deseja adicionar?" << endl;
          cin >> Add_Bebidas;

          switch (Bebida_Adicionada) {
            case 1:
              Coca_Cola += Add_Bebidas;
              break;
            case 2:
              Pepsi += Add_Bebidas;
              break;
            case 3:
              Guarana_Antartica += Add_Bebidas;
              break;
            case 4:
              Redbull += Add_Bebidas;
              break;
            case 5:
              Agua += Add_Bebidas;
              break;
            case 6:
              Guarana_Jesus += Add_Bebidas;
              break;
            case 7:
              Coca_Zero += Add_Bebidas;
              break;
            case 8:
              Cha_Mate += Add_Bebidas;
              break;
            case 9:
              Sprite += Add_Bebidas;
              break;
            default:
              cout << "Opção inválida!" << endl;
              break;
        }
        goto inicio;

       case 2: 
        //Informacao de quantas bebidas ainda tem na vending machine
          cout << "A Vending Machine Fatequiana possui em seu estoque: " << endl;
          cout << "Coca-Cola - " << Coca_Cola << " lata(s)" << endl;
          cout << "Pepsi - " << Pepsi << " lata(s)" << endl;
          cout << "Guaraná Antartica - " << Guarana_Antartica << " lata(s)" << endl;
          cout << "Redbull - " << Redbull << " lata(s)" << endl;
          cout << "Agua - " << Agua << " garrafa(s)" << endl;
          cout << "Guarana Jesus - " << Guarana_Jesus << " lata(s)" << endl;
          cout << "Coca-Cola Zero - " << Coca_Zero << " lata(s)" << endl;
          cout << "Cha-Mate - " << Cha_Mate << " lata(s)" << endl;
          cout << "Sprite - " << Sprite << " lata(s)" << endl;
          goto inicio;

       case 3:
        // Opção para o administrador verificar as informações financeiras
          Pode_Faturar = (Coca_Cola * 5) + (Pepsi * 4.5) + (Guarana_Antartica * 4.5) + (Redbull * 8) + (Agua * 3) + (Guarana_Jesus * 4.5) + (Coca_Zero * 5) + (Cha_Mate * 5) + (Sprite * 4.5);
          cout << "Informações financeiras:" << endl;
          cout << "A Vending Machine Fatequiana faturou R$" << Faturamento_Total << endl;
          cout << "E ainda pode faturar R$" << Pode_Faturar << endl;
          goto inicio;

          case 0:
          goto inicio;
          break;

      //Caso nenhuma das opcoes exibidas seja digitada:
       default:
        cout << "Opção inválida!" << endl;;
        goto inicio;
      }

      //Se a senha do administrador estiver incorreta:
      } else {
      cout << "senha invalida!" << endl;
      goto inicio;
      }
    }
  return 0;
}
