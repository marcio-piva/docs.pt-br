---
title: Genéricos e atributos – Guia de Programação em C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 35244ce33902760c2a0d3d8bda3181097f7ca38e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245175"
---
# <a name="generics-and-attributes-c-programming-guide"></a>Genéricos e atributos (Guia de Programação em C#)
Atributos podem ser aplicados a tipos genéricos da mesma forma que a tipos não genéricos. Para obter mais informações sobre a aplicação de atributos, consulte [Atributos](../../../csharp/programming-guide/concepts/attributes/index.md).  
  
 Atributos personalizados são permitidos somente para referenciar tipos genéricos abertos, que são tipos genéricos para os quais nenhum argumento de tipo é fornecido e tipos genéricos construídos fechados, que fornecem argumentos para todos os parâmetros de tipo.  
  
 Os exemplos a seguir usam esse atributo personalizado:  
  
 [!code-csharp[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 Um atributo pode referenciar um tipo genérico aberto:  
  
 [!code-csharp[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 Especifica vários parâmetros de tipo usando a quantidade apropriada de vírgulas. Neste exemplo, `GenericClass2` tem dois parâmetros de tipo:  
  
 [!code-csharp[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 Um atributo pode referenciar um tipo genérico construído fechado:  
  
 [!code-csharp[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 Um atributo que referencia um parâmetro de tipo genérico causará um erro em tempo de compilação:  
  
 [!code-csharp[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 Um tipo genérico não pode herdar de <xref:System.Attribute>:  
  
 [!code-csharp[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 Para obter informações sobre um tipo genérico ou um parâmetro de tipo em tempo de execução, é possível usar os métodos do <xref:System.Reflection>. Para obter mais informações, consulte [Genéricos e Reflexão](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
## <a name="see-also"></a>Consulte também

- [Guia de Programação em C#](../../../csharp/programming-guide/index.md)  
- [Genéricos](../../../csharp/programming-guide/generics/index.md)  
- [Atributos](../../../../docs/standard/attributes/index.md)
