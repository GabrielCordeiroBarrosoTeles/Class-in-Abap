# Class-in-Abap

ABAP (Advanced Business Application Programming) é uma linguagem de programação criada pela SAP (Sistemas, Aplicações e Produtos em Processamento de Dados) para desenvolvimento de aplicações empresariais. No contexto do ABAP, as "classes" referem-se a construções de programação orientada a objetos (OOP). Vou explicar um pouco sobre classes em ABAP e quando usá-las:

1. **Orientação a Objetos (OOP):**
   - Em ABAP, a OOP é implementada usando conceitos como classes, objetos, métodos, herança, polimorfismo, encapsulamento, etc.
   - As classes são estruturas fundamentais na programação orientada a objetos. Elas representam um modelo ou um "molde" para criar objetos, que são instâncias dessas classes.

2. **Características de uma Classe em ABAP:**
   - **Atributos (ou Propriedades):** São as variáveis que armazenam dados na classe.
   - **Métodos:** São as funções ou procedimentos que operam sobre os dados da classe.
   - **Eventos:** São gatilhos que podem ser usados para acionar a execução de um método.
   - **Interfaces:** Definem um contrato que as classes devem seguir.

3. **Quando Usar Classes em ABAP:**
   - **Reutilização de Código:** Classes permitem encapsular funcionalidades em unidades independentes, facilitando a reutilização do código em diferentes partes do sistema.
   - **Organização Estruturada:** Classes ajudam na organização do código, dividindo a lógica em módulos autocontidos.
   - **Manutenção Facilitada:** A OOP, em geral, facilita a manutenção do código, pois alterações em uma classe geralmente não afetam outras partes do sistema.

4. **Exemplo Prático:**
   - Suponha que você esteja desenvolvendo um sistema de gestão de funcionários. Pode-se criar uma classe `Employee` com atributos como `Name`, `EmployeeID`, e métodos como `calculateSalary`, `updateDetails`, etc.
   - Os objetos instanciados dessa classe representariam funcionários individuais no sistema.

5. **Herança e Polimorfismo:**
   - Em ABAP, você pode usar herança para criar uma nova classe com base em uma existente, herdando seus atributos e métodos.
   - O polimorfismo permite que objetos de diferentes classes sejam tratados de maneira uniforme.

6. **Interfaces:**
   - Interfaces definem contratos que as classes devem implementar, promovendo um design mais flexível e adaptável.

Em resumo, classes em ABAP, como em outras linguagens orientadas a objetos, proporcionam uma abordagem estruturada para modelagem e implementação de sistemas complexos. Elas são especialmente úteis em contextos onde a reutilização de código, a manutenção facilitada e uma organização modular são prioridades.	

Exemplo simples de uma classe em ABAP para ilustrar alguns conceitos básicos de programação orientada a objetos. Neste exemplo, vou criar uma classe chamada `Person` com alguns atributos e métodos.

```ABAP
CLASS Person DEFINITION.
  PUBLIC SECTION.
    DATA: Name TYPE STRING,
          Age TYPE I.

    METHODS: Constructor IMPORTING p_Name TYPE STRING p_Age TYPE I,
             DisplayInfo,
             SetAge IMPORTING p_Age TYPE I,
             GetAge RETURNING VALUE(r_Age) TYPE I.
ENDCLASS.

CLASS Person IMPLEMENTATION.
  METHOD Constructor.
    Name = p_Name.
    Age = p_Age.
  ENDMETHOD.

  METHOD DisplayInfo.
    WRITE: / 'Name:', Name,
           / 'Age:', Age.
  ENDMETHOD.

  METHOD SetAge.
    Age = p_Age.
  ENDMETHOD.

  METHOD GetAge.
    r_Age = Age.
  ENDMETHOD.
ENDCLASS.
```

Aqui está uma breve explicação do que cada parte do código faz:

- **DEFINITION Section:**
  - Na seção `PUBLIC`, são definidos os atributos (`Name` e `Age`) e os métodos (`Constructor`, `DisplayInfo`, `SetAge`, `GetAge`) da classe.

- **IMPLEMENTATION Section:**
  - Na seção `IMPLEMENTATION`, os métodos são implementados. O método `Constructor` é usado para inicializar os atributos durante a criação do objeto. O método `DisplayInfo` exibe as informações da pessoa. Os métodos `SetAge` e `GetAge` manipulam a idade da pessoa.

Agora, você pode usar esta classe da seguinte maneira:

```ABAP
DATA(larry) = NEW Person( 'Larry', 30 ).

larry->DisplayInfo( ).

larry->SetAge( 31 ).

DATA(age) = larry->GetAge( ).

WRITE: / 'New Age:', age.

```

Neste exemplo, criamos um objeto `Person` chamado `larry`, exibimos suas informações iniciais, alteramos a idade e exibimos a nova idade. Este é um exemplo muito simples, mas ilustra a estrutura básica de uma classe em ABAP.
