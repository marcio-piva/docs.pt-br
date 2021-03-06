---
title: Copiar o valor do &#39;ByRef&#39; parâmetro &#39; &lt;parametername&gt; &#39; para o argumento correspondente é restrita do tipo &#39; &lt;typename1&gt; &#39; &#39; &lt;typename2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: ec733ecd605d0a9db840ea3f0c3e0e3b5b698054
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506260"
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a>Copiar o valor do &#39;ByRef&#39; parâmetro &#39; &lt;parametername&gt; &#39; para o argumento correspondente é restrita do tipo &#39; &lt;typename1&gt; &#39; &#39; &lt;typename2&gt;&#39;
Um procedimento é chamado com um argumento que é ampliado para o tipo de parâmetro correspondente, e a conversão de parâmetro para o argumento é restritiva.  
  
 Quando você define uma classe ou estrutura, você pode definir um ou mais operadores de conversão para converter esse tipo de classe ou estrutura para outros tipos. Você também pode definir operadores de conversão reversa para converter esses tipos de volta para sua classe ou tipo de estrutura. Quando você usa o tipo de classe ou estrutura em uma chamada de procedimento, o Visual Basic pode usar esses operadores de conversão para converter o tipo de um argumento para o tipo de seu parâmetro correspondente.  
  
 Se você passar o argumento [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic, às vezes, copia o valor do argumento para uma variável local no procedimento em vez de passar uma referência. Nesse caso, quando o procedimento retorna, Visual Basic deve, em seguida, copie o valor da variável local volta para o argumento no código de chamada.  
  
 Se um `ByRef` o valor do argumento é copiado para o procedimento e o argumento e o parâmetro são do mesmo tipo, nenhuma conversão é necessária. Mas se os tipos forem diferentes, o Visual Basic deve converter em ambas as direções. Se um dos tipos é o tipo de classe ou estrutura, o Visual Basic deve convertê-lo tanto para o outro tipo. Se uma dessas conversões está ampliando, a conversão reversa pode estar restringindo.  
  
 **ID do erro:** BC32053  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
-   Se possível, use um argumento de chamada do mesmo tipo como o parâmetro de procedimento, portanto, o Visual Basic não precisa fazer nenhuma conversão.  
  
-   Se você precisar chamar o procedimento com um argumento de tipo diferente do tipo de parâmetro, mas não precisa retornar um valor para o argumento de chamada, defina o parâmetro para ser [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) em vez de `ByRef`.  
  
-   Se você precisar retornar um valor para o argumento de chamada, defina o operador de conversão inversa como [Widening](../../../visual-basic/language-reference/modifiers/widening.md), se possível.  
  
## <a name="see-also"></a>Consulte também
- [Procedimentos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Parâmetros e Argumentos de Procedimento](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Passando Argumentos por Valor e por Referência](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Procedimentos de Operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Instrução Operator](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Como: Definir um operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Como: Definir um operador de conversão](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Conversões de tipo no Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversões de Widening e Narrowing](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
