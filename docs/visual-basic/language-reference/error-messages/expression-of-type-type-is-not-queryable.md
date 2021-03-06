---
title: Expressão do tipo &lt;tipo&gt; não é passível de consulta
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: ce0831e0770e5733759c072b8d7c6f20b56f771b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521485"
---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a>Expressão do tipo &lt;tipo&gt; não é passível de consulta
Expressão do tipo \<tipo > não é passível de consulta. Certifique-se de que não está faltando uma importação de namespace e/ou referência de assembly para o provedor LINQ.  
  
 Tipos que podem ser consultados são definidos na <xref:System.Linq>, <xref:System.Data.Linq>, e <xref:System.Xml.Linq> namespaces. Você deve importar um ou mais desses namespaces para executar consultas LINQ.  
  
 O <xref:System.Linq> namespace permite que você consulta objetos, como coleções e matrizes usando LINQ.  
  
 O <xref:System.Data.Linq> namespace permite que você consultar conjuntos de dados ADO.NET e bancos de dados do SQL Server usando LINQ.  
  
 O <xref:System.Xml.Linq> namespace permite que você consulta XML usando LINQ e para utilizar os recursos XML no Visual Basic.  
  
 **ID do erro:** BC36593  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
1.  Adicionar um `Import` instrução para o <xref:System.Linq>, <xref:System.Data.Linq>, ou <xref:System.Xml.Linq> namespace ao seu arquivo de código. Você também pode importar namespaces para o seu projeto usando o **referências** página do Designer de projeto (**My Project**).  
  
2.  Certifique-se de que o tipo que você tenha identificado como a origem da sua consulta é um tipo passível de consulta. Ou seja, um tipo que implementa <xref:System.Collections.Generic.IEnumerable%601> ou <xref:System.Linq.IQueryable%601>.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [Introdução ao LINQ no Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Referências e a Instrução Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Instrução Imports (Tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Página Referências, Designer de Projeto (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
