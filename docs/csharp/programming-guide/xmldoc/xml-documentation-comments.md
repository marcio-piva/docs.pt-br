---
title: Comentários de documentação XML – Guia de Programação em C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: d4d8d20146efda516566d576a9d80d99f12fa944
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415293"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>Comentários de documentação XML (Guia de Programação em C#)
No Visual C#, você pode criar documentação para seu código ao incluir elementos XML nos campos de comentários especiais (indicados por barras triplas) no código-fonte logo antes do bloco de código ao qual os comentários se referem, por exemplo:  
  
```csharp  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 Ao compilar com a opção [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md), o compilador pesquisará todas as marcas XML no código-fonte e criará um arquivo de documentação XML. Para criar a documentação final com base no arquivo gerado pelo compilador, você pode criar uma ferramenta personalizada ou usar uma ferramenta como o [Sandcastle](https://github.com/EWSoftware/SHFB) ou o [DocFX](https://dotnet.github.io/docfx/).  
  
 Para consultar elementos XML (por exemplo, sua função processa elementos XML específicos que você deseja descrever em um comentário da documentação XML), você pode usar o mecanismo de citação padrão (`<` e `>`).  Para consultar identificadores genéricos em elementos de referência de código (`cref`), você pode usar os caracteres de escape (por exemplo, `cref="List&lt;T&gt;"`) ou chaves (`cref="List{T}"`).  Como um caso especial, o compilador analisa as chaves como colchetes angulares para tornar o comentário da documentação menos incômodo para o autor ao fazer referência a identificadores genéricos.  
  
> [!NOTE]
>  Os comentários da documentação XML não são metadados; eles não estão incluídos no assembly compilado e, portanto, não são acessíveis através de reflexão.  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Marcas recomendadas para comentários de documentação](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [Processando o Arquivo XML](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [Delimitadores para marcas de documentação](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [Como: usar as funcionalidades da documentação XML](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a>Seções relacionadas  
 Para obter mais informações, consulte:  
  
-   [/doc (comentários da documentação de processos)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a>Especificação da Linguagem C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Guia de Programação em C#](../../../csharp/programming-guide/index.md)
