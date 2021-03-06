---
title: Operador &gt;&gt;= – referência do C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 02a9559a5c4086eeed09094c15c3620366ffad8c
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333676"
---
# <a name="gtgt-operator-c-reference"></a>Operador &gt;&gt;= (referência do C#)

O operador de atribuição de deslocamento para a direita.

## <a name="remarks"></a>Comentários

Uma expressão da forma

```csharp
x >>= y
```

é avaliada como

```csharp
x = x >> y
```

exceto que `x` é avaliado apenas uma vez. O [operador >>](right-shift-operator.md) desloca `x` para a direita em um valor especificado pelo `y`.

O operador >>= não pode ser sobrecarregado diretamente, mas tipos definidos pelo usuário podem sobrecarregar o [operador >>](right-shift-operator.md) (consulte [operador](../keywords/operator.md)).

## <a name="example"></a>Exemplo

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a>Consulte também

- [Referência de C#](../index.md)
- [Guia de Programação em C#](../../programming-guide/index.md)
- [Operadores do C#](index.md)