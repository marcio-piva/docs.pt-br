---
title: Removendo conteúdo do nó em DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 737766586ee920a87c25dd42896bdfb14ae69d98
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44205212"
---
# <a name="removing-node-content-in-the-dom"></a>Removendo conteúdo do nó em DOM
Para os tipos de nós que herdam de <xref:System.Xml.XmlCharacterData>, que são <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, e os tipos de nós de <xref:System.Xml.XmlSignificantWhitespace> , você pode remover os caracteres usando o método de <xref:System.Xml.XmlCharacterData.DeleteData%2A> , que remove um intervalo de caracteres de nó. Se você deseja remover completamente o conteúdo, você remover o nó que contém o conteúdo. Se você desejar manter o nó, mas o conteúdo está incorreto, então modificar o conteúdo. Para saber mais sobre como alterar o conteúdo de um nó, confira [Modificando nós, conteúdo e valores em um documento XML](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).  
  
## <a name="see-also"></a>Consulte também

- [DOM (Modelo de Objeto do Documento) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
