# DIO Inn

<img style = "width: 200px" src = "https://hermes.dio.me/tracks/169e3d0f-263a-4efb-86c5-244bdf1ce8d6.png" alt = "Formação .Net Developer"> <img style = "width: 200px" src = "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRdjqTkPkxvNF5yqLhPRNhYXnwXuW422OWMGMyn2KkNTjRyuqZriAq26YEAK35FIOgKAwY&usqp=CAU" alt = "DIO"> 


# Sobre o Projeto

Desenolvido em Agosto de 2023 durante a **Formação .Net Developer** oeferecido pela **Digital Innovation One (DIO)**, o projeto apresenta uma aplicação console simulando um sistema de hospedagem de um hotel. Ele verifica a quantidade de dias e hóspede e fornece um desconto caso a quantidade de dias seja maior que 10.

<details><summary>Desafio</summary>

# DIO - Trilha .NET - Explorando a linguagem C#
www.dio.me

## Desafio de projeto
Para este desafio, você precisará usar seus conhecimentos adquiridos no módulo de explorando a linguagem C#, da trilha .NET da DIO.

## Contexto
Você foi contratado para construir um sistema de hospedagem, que será usado para realizar uma reserva em um hotel. Você precisará usar a classe Pessoa, que representa o hóspede, a classe Suíte, e a classe Reserva, que fará um relacionamento entre ambos.

O seu programa deverá cálcular corretamente os valores dos métodos da classe Reserva, que precisará trazer a quantidade de hóspedes e o valor da diária, concedendo um desconto de 10% para caso a reserva seja para um período maior que 10 dias.

## Regras e validações
1. Não deve ser possível realizar uma reserva de uma suíte com capacidade menor do que a quantidade de hóspedes. Exemplo: Se é uma suíte capaz de hospedar 2 pessoas, então ao passar 3 hóspedes deverá retornar uma exception.
2. O método ObterQuantidadeHospedes da classe Reserva deverá retornar a quantidade total de hóspedes, enquanto que o método CalcularValorDiaria deverá retornar o valor da diária (Dias reservados x valor da diária).
3. Caso seja feita uma reserva igual ou maior que 10 dias, deverá ser concedido um desconto de 10% no valor da diária.


![Diagrama de classe estacionamento](diagrama_classe_hotel.png)

## Solução
O código está pela metade, e você deverá dar continuidade obedecendo as regras descritas acima, para que no final, tenhamos um programa funcional. Procure pela palavra comentada "TODO" no código, em seguida, implemente conforme as regras acima.
</details>

<details><summary>Solução</summary>

# Método CadastrarHospede()

Foi inserida uma verificação com **if** e adicionada uma **Exception** como solicitado no desafio:

```c#
        public void CadastrarHospedes(List<Pessoa> hospedes)
        {
            // TODO: Verificar se a capacidade é maior ou igual ao número de hóspedes sendo recebido
            // *IMPLEMENTE AQUI*
            if (Suite.Capacidade >= hospedes.Count())
            {
                Hospedes = hospedes;
            }
            else
            {
                // TODO: Retornar uma exception caso a capacidade seja menor que o número de hóspedes recebido
                // *IMPLEMENTE AQUI*  
                Console.WriteLine(new Exception("Ocorreu um erro! A capacidade de hóspede deve ser maior que o número de hóspedes digitado."));   
            }
        }
```


## Método ObterQuantidadeHospede:

Retorna a contagem total de hóspedes a partir da propriedade:

```c#
        public int ObterQuantidadeHospedes()
        {
            // TODO: Retorna a quantidade de hóspedes (propriedade Hospedes)
            // *IMPLEMENTE AQUI*
            return Hospedes.Count();
        }
```

## Método CalcularValorDiaria():

Realiza o cálculo da diária e fornece um desconto de 10% caso a quantidade de dias de hospedagem seja igual ou maior que 10:
```c#
        public decimal CalcularValorDiaria()
        {
            // TODO: Retorna o valor da diária
            // Cálculo: DiasReservados X Suite.ValorDiaria
            // *IMPLEMENTE AQUI*
            decimal valor = DiasReservados * Suite.ValorDiaria;

            // Regra: Caso os dias reservados forem maior ou igual a 10, conceder um desconto de 10%
            // *IMPLEMENTE AQUI*
            if (DiasReservados >= 10)
            {
                decimal desconto = valor * 0.1m;
                valor -= desconto;
            }

            return valor;
        }
```


</details>

# Tecnologias Utilizadas

- [.Net 7.0.302](https://dotnet.microsoft.com/en-us/download/dotnet/7.0) 
- [Visual Studio Code](https://code.visualstudio.com/download)

# Como Clonar o Projeto

- Instale o [Git](https://git-scm.com/downloads) no seu computador. Durante a instalação, certifique-se se a opção **Git Bash** está adicionada.
- Após a instalação, crie uma pasta em sua área de trabalho
- Dentro da pasta, clique com o botão direito e selecione **Git Bash Here**
- Após abrir o terminal, copie o seguinte comando:
   
```bash
git clone https://github.com/PhilTisoni/trilha-net-explorando-desafio.git
```
O projeto deverá ser clonado para a sua pasta. Abra a solução em seu compilador de preferência.


# Autor

- [Phelipe Augusto Tisoni](https://www.linkedin.com/in/phelipetisoni "Phelipe Linkedin")





