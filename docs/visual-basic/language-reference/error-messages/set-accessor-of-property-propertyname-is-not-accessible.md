---
title: '&#39;Defina&#39; acessador de propriedade &#39; &lt;propertyname&gt; &#39; não está acessível'
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: a543506b06742f3ee9101edbac962e761ddd531d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606563"
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39;Defina&#39; acessador de propriedade &#39; &lt;propertyname&gt; &#39; não está acessível
Uma declaração tenta armazenar o valor de uma propriedade quando ela não tem acesso para a propriedade `Set` procedimento.  
  
 Se o [instrução Set](../../../visual-basic/language-reference/statements/set-statement.md) está marcada com um acesso mais restritivo nível que seus [instrução Property](../../../visual-basic/language-reference/statements/property-statement.md), uma tentativa para definir o valor da propriedade pode falhar nos seguintes casos:  
  
-   O `Set` declaração está marcada [privada](../../../visual-basic/language-reference/modifiers/private.md) e o código de chamada está fora da classe ou estrutura na qual a propriedade é definida.  
  
-   O `Set` declaração está marcada [protegido](../../../visual-basic/language-reference/modifiers/protected.md) e o código de chamada é não na classe ou estrutura na qual a propriedade é definida, nem em uma classe derivada.  
  
-   O `Set` declaração está marcada [amigo](../../../visual-basic/language-reference/modifiers/friend.md) e o código de chamada não está no mesmo assembly no qual a propriedade é definida.  
  
 **ID do erro:** BC31102  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
-   Se você tiver o controle do código-fonte definindo a propriedade, considere a possibilidade de declarar o `Set` procedimento com o mesmo nível de acesso que a própria propriedade.  
  
-   Se você não tem controle do código-fonte definindo a propriedade, você deve restringir o `Set` procedimento de nível de acesso mais do que a própria propriedade, tente mover a instrução que define o valor da propriedade para uma região de código que tem um melhor acesso para o propriedade.  
  
## <a name="see-also"></a>Consulte também
- [Procedimentos de Propriedade](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Como: Declarar uma propriedade com níveis de acesso mistos](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
