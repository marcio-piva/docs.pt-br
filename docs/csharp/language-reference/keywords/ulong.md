---
title: Palavra-chave ulong – Referência de C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: 97db22612e900658746f40cd117ff941135027a1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235014"
---
# <a name="ulong-c-reference"></a>ulong (Referência de C#)

A palavra-chave `ulong` indica um tipo integral que armazena valores de acordo com o tamanho e o intervalo mostrados na tabela a seguir.

|Tipo|Intervalo|Tamanho|Tipo .NET|
|----------|-----------|----------|-------------------------|
|`ulong`|0 a 18.446.744.073.709.551.615|Inteiro de 64 bits sem sinal|<xref:System.UInt64?displayProperty=nameWithType>|

## <a name="literals"></a>Literais

Você pode declarar e inicializar uma variável `ulong` atribuindo a ela um literal decimal, um literal hexadecimal ou (começando com o C# 7.0) um literal binário.  Se o literal inteiro estiver fora do intervalo de `ulong` (ou seja, se for menor que <xref:System.UInt64.MinValue?displayProperty=nameWithType> ou maior que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), ocorrerá um erro de compilação.

No exemplo a seguir, inteiros iguais a 7.934.076.125 representados como literais decimais, hexadecimais e binários são atribuídos a valores `ulong`.

[!code-csharp[ulong](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]

> [!NOTE]
> Use o prefixo `0x` ou `0X` para indicar um literal hexadecimal e o prefixo `0b` ou `0B` para indicar um literal binário. Literais decimais não têm nenhum prefixo.

Começando com o C# 7.0, alguns recursos foram adicionados para melhorar a legibilidade:

- O C# 7.0 permite o uso do caractere de sublinhado, `_`, como um separador de dígito.
- O C# 7.2 permite que `_` seja usado como separador de dígito de um literal binário ou hexadecimal, após o prefixo. Um literal decimal não pode ter um sublinhado à esquerda.

Alguns exemplos são mostrados abaixo.

[!code-csharp[long](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

Literais inteiros também podem incluir um sufixo que indica o tipo. O sufixo `UL` ou `ul` identifica inequivocamente um literal numérico como um valor `ulong`. O sufixo `L` denota um `ulong` se o valor literal excede <xref:System.Int64.MaxValue?displayProperty=nameWithType>. E o sufixo `U` ou `u` denota um `ulong` se o valor literal excede <xref:System.UInt32.MaxValue?displayProperty=nameWithType>. O exemplo a seguir usa o sufixo `ul` para indicar um inteiro longo:

[!code-csharp[ulsuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

Se um literal inteiro não tiver sufixo, seu tipo será o primeiro dos tipos a seguir em que seu valor pode ser representado:

1. [int](int.md)
2. [uint](uint.md)
3. [long](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a>Resolução de sobrecarga do compilador

Um uso comum do sufixo é a chamada de métodos sobrecarregados. Considere, por exemplo, os seguintes métodos sobrecarregados que usam os parâmetros `ulong` e [int](int.md):

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ulong l) {}
```

Usar o sufixo com o parâmetro `ulong` garante que o tipo correto seja chamado, por exemplo:

```csharp
SampleMethod(5);    // Calling the method with the int parameter
SampleMethod(5UL);  // Calling the method with the ulong parameter
```

## <a name="conversions"></a>Conversões

Há uma conversão implícita predefinida de `ulong` para [float](float.md), [double](double.md) ou [decimal](decimal.md).

Não há nenhuma conversão implícita de `ulong` em qualquer tipo integral. Por exemplo, a instrução a seguir produzirá um erro de compilação sem uma conversão explícita:

```csharp
long long1 = 8UL;   // Error: no implicit conversion from ulong
```

Há uma conversão implícita predefinida de [byte](byte.md), [ushort](ushort.md), [uint](uint.md) ou [char](char.md) em `ulong`.

Além disso, não há conversão implícita de tipos de ponto flutuante em `ulong`. Por exemplo, a instrução a seguir gerará um erro de compilador, a menos que uma conversão explícita seja usada:

```csharp
// Error -- no implicit conversion from double:
ulong x = 3.0;
// OK -- explicit conversion:
ulong y = (ulong)3.0;
```

Para obter informações sobre expressões aritméticas com tipos de ponto flutuante mistos e tipos integrais, consulte [float](float.md) e [double](double.md).

Para obter mais informações sobre as regras de conversão numérica implícita, consulte a [Tabela de conversões numéricas implícitas](implicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>Especificação da linguagem C#

Para obter mais informações, veja [Tipos integrais](~/_csharplang/spec/types.md#integral-types) na [Especificação da Linguagem C#](../language-specification/index.md). A especificação da linguagem é a fonte definitiva para a sintaxe e o uso de C#.

## <a name="see-also"></a>Consulte também

- <xref:System.UInt64>
- [Referência de C#](../index.md)
- [Guia de Programação em C#](../../programming-guide/index.md)
- [Palavras-chave do C#](index.md)
- [Tabela de tipos integrais](integral-types-table.md)
- [Tabela de tipos internos](built-in-types-table.md)
- [Tabela de conversões numéricas implícitas](implicit-numeric-conversions-table.md)
- [Tabela de conversões numéricas explícitas](explicit-numeric-conversions-table.md)
