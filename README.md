# Orientação a objetos com C#

Resumo do curso:

https://www.schoolofnet.com/curso-orientacao-objetos-com-c/


---

## <a name="indice">Índice</a>

- [Introdução](#parte1)
- [Cenário Classes](#parte2)
- [Encapsulamento 1](#parte3)
- [Encapsulamento 2](#parte4)
- [Herança Conceito](#parte5)
- [Herança GenerEspec](#parte6)
- [Herança Construtor](#parte7)
- [Métodos Virtuais](#parte8)
- [Polimorf Herança](#parte9)
- [Polimorf Método](#parte10)
- [Classe Abstrata](#parte11)
- [Métodos Abstratos](#parte12)
- [Interface Conceito](#parte13)
- [Interface Aplicação](#parte14)
- [Exceção Introdução](#parte15)
- [Exceção Tratamento](#parte16)
- [Exceção Níveis](#parte17)
- [Exceção Finally](#parte18)
- [Exceção Custom](#parte19)
- [Debugging Break](#parte20)
- [Debugging Watch](#parte21)

---

## <a name="parte1">Introdução</a>

Material de Referência: (Apostila Caelum c#)[https://www.caelum.com.br/apostila-csharp-orientacao-objetos/]





[Voltar ao Índice](#indice)

---

## <a name="parte2">Cenário Classes</a>

ContaCorrente.cs
```csharp
using System;

namespace CSharpOO
{
    public class ContaCorrente
    {
        private int agencia;
        private int numeroCOnta;
        private decimal saldo;

        public void Sacar(decimal valor)
        {
            if (saldo >= valor)
            {
                saldo -= valor;
            }
            else
            {
                //mesagem
            }
            
        }

        public void Depositar(decimal valor)
        {
            saldo += valor;
        }
    }
}
```

Programa.cc
```csharp
using System;

namespace CSharpOO
{
    class Program
    {
        static void Main(string[] args)
        {
            ContaCorrente cc = new ContaCorrente();
            cc.Depositar(100);
        }
    }
}
```

[Voltar ao Índice](#indice)

---

## <a name="parte3">Encapsulamento 1</a>

[Voltar ao Índice](#indice)

---

## <a name="parte4">Encapsulamento 2</a>

```csharp
using System;

namespace CSharpOO
{
    public class ContaCorrente
    {
        private int numeroConta;
        private decimal saldo;


        private int agencia;
        public ContaCorrente()
        {
            agencia = 44512;
        }

        public int Agencia
        {
            get { return agencia; }
            private set
            {
                agencia = value;
            }
        }

        public void SetAgencia(int agencia)
        {
            this.agencia = agencia;
        }

        public void Sacar(decimal valor)
        {
            if (saldo >= valor)
            {
                saldo -= valor;
            }
            else
            {
                Console.WriteLine("Hello World!");
            }
        }

        public void Depositar(decimal valor)
        {
            saldo += valor;
        }
    }
}

```

```csharp
using System;

namespace CSharpOO
{
    class Program
    {
        static void Main(string[] args)
        {
            ContaCorrente cc = new ContaCorrente();
            //cc.Agencia = 1;
            cc.SetAgencia(33);
            Console.WriteLine(cc.Agencia);

            Console.Read();
        }
    }
}
```

(Encapsulamento e Modificadores de Acesso)[https://www.caelum.com.br/apostila-csharp-orientacao-objetos/encapsulamento-e-modificadores-de-acesso/]

A partir do C# 3.0, temos as propriedades que são implementadas automaticamente pelo compilador, as auto-implemented properties. Para declararmos uma auto-implemented property para expor o número da conta, utilizamos o seguinte código:

```csharp
class Conta
{
    // outras propriedades
    
    // get é público e pode ser acessado por qualquer classe
    // set é privado e por isso só pode ser usado pela conta.
    public double Saldo { get; private set; }
    
    // resto do código da classe.
}
```
 podemos deixar a classe AtualizadorDeContas ou o método Atualiza com visibilidade internal:

 ```csharp
 // internal é a visibilidade padrão para a classe,
// portanto a palavra internal é opcional
internal class AtualizadorDeContas
{
    // implementação da classe
}
```

(Construtores)[https://www.caelum.com.br/apostila-csharp-orientacao-objetos/construtores/]

```csharp
class Cliente 
{
    public string Nome { get; set; }
    
    public int Idade { get; set; }
    
    // construtor que só recebe o nome
    public Cliente (string nome)
    {
        this.Nome = nome;
    }
    // construtor que recebe o nome e a idade
    public Cliente (string nome, int idade)
    {
        this.Nome = nome;
        this.Idade = idade;
    }
}
```

### Initializer

Para evitar essa repetição, podemos utilizar os initializers do C#. O Initializer é um bloco de código que serve para inicializar as propriedades públicas do objeto.

```csharp
Cliente cliente = new Cliente ("Victor Harada")
{
    // bloco de inicialização
    Cpf = "123.456.789-01",
    Rg = "21.345.987-x",
    Idade = 25
};
```




[Voltar ao Índice](#indice)

---

## <a name="parte5">Herança Conceito</a>

[Voltar ao Índice](#indice)

---

## <a name="parte6">Herança GenerEspec</a>

[Voltar ao Índice](#indice)

---

## <a name="parte7">Herança Construtor</a>

[Voltar ao Índice](#indice)

---

## <a name="parte8">Métodos Virtuais</a>

[Voltar ao Índice](#indice)

---

## <a name="parte9">Polimorf Herança</a>

[Voltar ao Índice](#indice)

---

## <a name="parte10">Polimorf Método</a>

[Voltar ao Índice](#indice)

---

## <a name="parte11">Classe Abstrata</a>

[Voltar ao Índice](#indice)

---

## <a name="parte12">Métodos Abstratos</a>

[Voltar ao Índice](#indice)

---

## <a name="parte13">Interface Conceito</a>

[Voltar ao Índice](#indice)

---

## <a name="parte14">Interface Aplicação</a>

[Voltar ao Índice](#indice)

---

## <a name="parte15">Exceção Introdução</a>

[Voltar ao Índice](#indice)

---

## <a name="parte16">Exceção Tratamento</a>

[Voltar ao Índice](#indice)

---

## <a name="parte17">Exceção Níveis</a>

[Voltar ao Índice](#indice)

---

## <a name="parte18">Exceção Finally</a>

[Voltar ao Índice](#indice)

---

## <a name="parte19">Exceção Custom</a>

[Voltar ao Índice](#indice)

---

## <a name="parte20">Debugging Break</a>

[Voltar ao Índice](#indice)

---

## <a name="parte21">Debugging Watch</a>

[Voltar ao Índice](#indice)

---