---
title: Campos – Guia de Programação em C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- fields [C#]
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
ms.openlocfilehash: af5a342b83608d6a149879de8dec80a1e1746b76
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242692"
---
# <a name="fields-c-programming-guide"></a>Campos (Guia de Programação em C#)
Um *campo* é uma variável de qualquer tipo que é declarada diretamente em uma [classe](../../../csharp/language-reference/keywords/class.md) ou [struct](../../../csharp/language-reference/keywords/struct.md). Os campos são *membros* do tipo que os contém.  
  
 Uma classe ou um struct podem ter campos de instância, campos estáticos ou ambos. Os campos de instância são específicos a uma instância de um tipo. Se você tem uma classe T, com um campo de instância F, você pode criar dois objetos do tipo T e modificar o valor de F em cada objeto sem afetar o valor no outro objeto. Por outro lado, um campo estático pertence à própria classe e é compartilhado entre todas as instâncias dessa classe. As alterações feitas na instância A serão imediatamente visíveis para as instâncias B e C se elas acessarem o campo.  
  
 Em geral, você só deve usar campos para variáveis que têm acessibilidade particular ou protegida. Os dados que a classe expõe para o código de cliente devem ser fornecidos por meio de [métodos](../../../csharp/programming-guide/classes-and-structs/methods.md), [propriedades](../../../csharp/programming-guide/classes-and-structs/properties.md) e [indexadores](../../../csharp/programming-guide/indexers/index.md). Usando esses constructos para acesso indireto aos campos internos, você pode proteger contra valores de entrada inválidos. Um campo particular que armazena os dados expostos por uma propriedade pública é chamado de *repositório de backup* ou de *campo de suporte*.  
  
 Os campos normalmente armazenam os dados que devem estar acessíveis a mais de um método de classe e devem ser armazenados por mais tempo que o tempo de vida de qualquer método único. Por exemplo, uma classe que representa uma data do calendário pode ter três campos de inteiros: um para o mês, um para o dia e outro para o ano. As variáveis que não são usadas fora do escopo de um método único devem ser declaradas como *variáveis locais* dentro do próprio corpo do método.  
  
 Os campos são declarados no bloco de classe, especificando o nível de acesso do campo, seguido pelo tipo do campo e pelo nome do campo. Por exemplo:  
  
 [!code-csharp[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_1.cs)]  
  
 Para acessar um campo em um objeto, adicione um ponto após o nome do objeto, seguido pelo nome do campo, como em `objectname.fieldname`. Por exemplo:  
  
 [!code-csharp[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_2.cs)]  
  
 Um campo pode receber um valor inicial, usando o operador de atribuição quando o campo é declarado. Para atribuir automaticamente o campo `day` ao `"Monday"`, por exemplo, você poderia declarar `day` como no exemplo a seguir:  
  
 [!code-csharp[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_3.cs)]  
  
 Os campos são inicializados imediatamente antes do construtor para a instância do objeto ser chamado. Se o construtor atribuir o valor de um campo, ele substituirá qualquer valor fornecido durante a declaração do campo. Para obter mais informações, veja [Usando construtores](../../../csharp/programming-guide/classes-and-structs/using-constructors.md).  
  
> [!NOTE]
>  Um inicializador de campo não pode fazer referência a outros campos de instância.  
  
 Os campos podem ser marcados como [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) ou [private protected](../../../csharp/language-reference/keywords/private-protected.md). Esses modificadores de acesso definem como os usuários da classe podem acessar os campos. Para obter mais informações, consulte [Modificadores de Acesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Opcionalmente, um campo pode ser declarado [static](../../../csharp/language-reference/keywords/static.md). Isso torna o campo disponível para chamadores a qualquer momento, mesmo se não existir nenhuma instância da classe. Para obter mais informações, consulte [Classes estáticas e membros de classes estáticas](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Um campo pode ser declarado [readonly](../../../csharp/language-reference/keywords/readonly.md). Um valor só pode ser atribuído a um campo somente leitura durante a inicialização ou em um construtor. Um campo `static readonly` é muito semelhante a uma constante, exceto que o compilador C# não tem acesso ao valor de um campo somente leitura estático em tempo de compilação, mas somente em tempo de execução. Para obter mais informações, consulte [Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md).  
  
## <a name="c-language-specification"></a>Especificação da Linguagem C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Guia de Programação em C#](../../../csharp/programming-guide/index.md)  
- [Classes e Structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Usando construtores](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
- [Herança](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
- [Modificadores de acesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [Classes e membros de classes abstract e sealed](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
