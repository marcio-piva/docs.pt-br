---
title: Não compatível com CLS &lt;membername&gt; não é permitido em uma interface compatível com CLS
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: c837065d2d448fc2523cfbd18efac962445f8bf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627688"
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>Não compatível com CLS &lt;membername&gt; não é permitido em uma interface compatível com CLS
Uma propriedade, procedimento ou evento em uma interface é marcado como `<CLSCompliant(True)>` quando a própria interface é marcada como `<CLSCompliant(False)>` ou não está marcado.  
  
 Para uma interface para estar em conformidade com o [independência de linguagem e componentes independentes de linguagem](../../../standard/language-independence-and-language-independent-components.md) (CLS), todos os seus membros devem estar em conformidade.  
  
 Quando você aplica a <xref:System.CLSCompliantAttribute> a um elemento de programação, você definir o atributo `isCompliant` parâmetro a `True` ou `False` para indicar a compatibilidade ou incompatibilidade. Não há nenhum padrão para esse parâmetro, e você deve fornecer um valor.  
  
 Se você não se aplicam a <xref:System.CLSCompliantAttribute> a um elemento, ele é considerado incompatível.  
  
 Por padrão, esta mensagem é um aviso. Para obter informações sobre como ocultar avisos ou tratar avisos como erros, consulte [Configurando avisos no Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID do erro:** BC40033  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
-   Se você exige conformidade com CLS e tem controle sobre o código-fonte de interface, marque a interface como `<CLSCompliant(True)>` se todos os seus membros estão em conformidade.  
  
-   Se você exige conformidade com CLS e não tem controle sobre o código de origem da interface, ou se ele não se qualifica para estar em conformidade, defina este membro dentro de uma interface diferente.  
  
-   Se você precisar que esse membro permaneça em sua interface atual, remova os <xref:System.CLSCompliantAttribute> de sua definição ou marque-a como `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Consulte também
- [Instrução Interface](../../../visual-basic/language-reference/statements/interface-statement.md)

