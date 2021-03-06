---
title: 'Como: Retornar um valor de um procedimento (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 38b0673f5725077eec9253021eec4216e66504a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54615231"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Como: Retornar um valor de um procedimento (Visual Basic)
Um `Function` procedimento retorna um valor para o código de chamada seja executando uma `Return` instrução ou encontrando uma `Exit Function` ou `End Function` instrução.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Para retornar um valor usando a instrução Return  
  
1.  Coloque um `Return` instrução no ponto em que as tarefas do procedimento é concluída.  
  
2.  Siga o `Return` palavra-chave com uma expressão que produz o valor que você deseja retornar ao código de chamada.  
  
3.  Você pode ter mais de um demonstrativo `Return` no mesmo procedimento.  
  
     O seguinte `Function` procedimento calcula o lado mais longo, ou hipotenusa de um triângulo e o retorna ao código de chamada.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     O exemplo a seguir mostra uma chamada típica para `hypotenuse`, que armazena o valor retornado.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Para retornar um valor usando Exit Function ou End Function  
  
1.  Em pelo menos um lugar a `Function` procedimento, atribua um valor ao nome do procedimento.  
  
2.  Quando você executa um `Exit Function` ou `End Function` instrução, o Visual Basic retorna o valor mais recentemente atribuído ao nome do procedimento.  
  
3.  Você pode ter mais de um demonstrativo `Exit Function` no mesmo procedimento e mesclar os demonstrativos `Return` e `Exit Function` no mesmo procedimento.  
  
4.  Você pode ter apenas um `End Function` instrução em um `Function` procedimento.  
  
     Para obter mais informações e um exemplo, consulte "Valor de retorno" em [instrução Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Consulte também
- [Procedimentos](./index.md)
- [Subprocedimentos](./sub-procedures.md)
- [Procedimentos de Propriedade](./property-procedures.md)
- [Procedimentos de Operador](./operator-procedures.md)
- [Parâmetros e Argumentos de Procedimento](./procedure-parameters-and-arguments.md)
- [Instrução Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Instrução Return](../../../../visual-basic/language-reference/statements/return-statement.md)
- [Como: Criar um procedimento que retorna um valor](./how-to-create-a-procedure-that-returns-a-value.md)
- [Como: Chamar um procedimento que retorna um valor](./how-to-call-a-procedure-that-returns-a-value.md)
