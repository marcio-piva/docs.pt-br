---
title: XPathDocument inseriu a XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09f0301724e483def3bea9dfdf75a088ac09bb55
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085365"
---
# <a name="xpathdocument-input-to-xsltransform"></a>XPathDocument inseriu a XslTransform
<xref:System.Xml.XPath.XPathDocument> é um cache somente leitura, para processar documentos com <xref:System.Xml.Xsl.XslTransform>. Estruturalmente é semelhante ao modelo de objeto (DOM) de documento, mas altamente é otimizado para o idioma extensível de folha de estilos para transformações (XSLT) e processar o modelo de dados de idioma do caminho de XML (XPath) usando as funções de otimização XPath em <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
>  A classe <xref:System.Xml.Xsl.XslTransform> está obsoleta no [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Você pode executar a linguagem XSL Transformations (XSLT) usando a classe <xref:System.Xml.Xsl.XslCompiledTransform>. Confira [Usar a classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [Migrar da classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para saber mais.  
  
 O exemplo de código a seguir cria <xref:System.Xml.XPath.XPathDocument> como entrada uma transformação.  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a>Consulte também

- [A classe XslTransform implementa o processador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
