---
title: Determinando o tipo de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 5980549dd063b2c7d5c60ebd4e9762284c072009
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586612"
---
# <a name="determining-object-type-visual-basic"></a>Determinando o tipo de objeto (Visual Basic)
Variáveis de objeto genérico (ou seja, as variáveis que você declare como `Object`) pode conter objetos de qualquer classe. Ao usar as variáveis do tipo `Object`, talvez você precise executar ações diferentes com base na classe do objeto; por exemplo, alguns objetos podem não dar suporte a uma determinada propriedade ou método. O Visual Basic fornece dois meios para determinar qual tipo de objeto é armazenado em uma variável de objeto: o `TypeName` função e o `TypeOf...Is` operador.  
  
## <a name="typename-and-typeofis"></a>TypeName e TypeOf... É  
 O `TypeName` função retorna uma cadeia de caracteres e é a melhor opção quando você precisa armazenar ou exibir o nome de classe de um objeto, conforme mostrado no seguinte fragmento de código:  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 O `TypeOf...Is` operador é a melhor opção para testar o tipo de um objeto, porque ele é muito mais rápido que uma comparação de cadeia de caracteres equivalente usando `TypeName`. O fragmento de código a seguir usa `TypeOf...Is` dentro de um `If...Then...Else` instrução:  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 Uma palavra de advertência aqui é devida. O `TypeOf...Is` operador retorna `True` se um objeto é de um tipo específico, ou é derivado de um tipo específico. Quase tudo o que fazer com o Visual Basic envolve a objetos, que incluem alguns elementos que não são considerados normalmente objetos, como cadeias de caracteres e inteiros. Esses objetos são derivados e herdam os métodos de <xref:System.Object>. Quando passado um `Integer` e avaliados com `Object`, o `TypeOf...Is` operador retorna `True`. O exemplo a seguir relata que o parâmetro `InParam` for tanto um `Object` e um `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 O exemplo a seguir usa ambos `TypeOf...Is` e `TypeName` para determinar o tipo de objeto passado para ele no `Ctrl` argumento. O `TestObject` chamadas de procedimento `ShowType` com três tipos diferentes de controles.  
  
#### <a name="to-run-the-example"></a>Para executar o exemplo  
  
1.  Criar um novo projeto de aplicativo do Windows e adicione uma <xref:System.Windows.Forms.Button> controle, um <xref:System.Windows.Forms.CheckBox> controle e um <xref:System.Windows.Forms.RadioButton> controle ao formulário.  
  
2.  Com o botão no formulário, chame o `TestObject` procedimento.  
  
3.  Adicione o seguinte código ao seu formulário:  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a>Consulte também
- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Chamando uma Propriedade ou um Método Usando o Nome de uma Cadeia de Caracteres](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [Tipo de Dados Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Instrução If...Then...Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Tipo de Dados String](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Tipo de Dados Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
