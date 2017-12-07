---
title: Criando novos atributos para elementos no DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6970ffc38e900c9b47c58c8ae4b81b9551f5589b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="5551a-102">Criando novos atributos para elementos no DOM</span><span class="sxs-lookup"><span data-stu-id="5551a-102">Creating New Attributes for Elements in the DOM</span></span>
<span data-ttu-id="5551a-103">Criar novos atributos é diferente de criar outros tipos de nó, porque os atributos não são nós, mas são propriedades de um nó de elemento e estão contidos em um **XmlAttributeCollection** associada ao elemento.</span><span class="sxs-lookup"><span data-stu-id="5551a-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="5551a-104">Há várias maneiras de criar um atributo e anexá-lo a um elemento:</span><span class="sxs-lookup"><span data-stu-id="5551a-104">There are multiple ways to create an attribute and attach it to an element:</span></span>  
  
-   <span data-ttu-id="5551a-105">Obter o nó de elemento e use **SetAttribute** para adicionar um atributo à coleção de atributos desse elemento.</span><span class="sxs-lookup"><span data-stu-id="5551a-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>  
  
-   <span data-ttu-id="5551a-106">Criar um **XmlAttribute** nó usando o **CreateAttribute** método, obter o nó de elemento, em seguida, usar **SetAttributeNode** para adicionar o nó para a coleção de atributos que elemento.</span><span class="sxs-lookup"><span data-stu-id="5551a-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>  
  
 <span data-ttu-id="5551a-107">O exemplo a seguir mostra como adicionar um atributo a um elemento usando o **SetAttribute** método.</span><span class="sxs-lookup"><span data-stu-id="5551a-107">The following example shows how to add an attribute to an element using the **SetAttribute** method.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  public static void Main()  
  {  
    XmlDocument doc = new XmlDocument();  
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 <span data-ttu-id="5551a-108">O exemplo a seguir mostra um novo atributo que está sendo criado usando o **CreateAttribute** método.</span><span class="sxs-lookup"><span data-stu-id="5551a-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="5551a-109">Mostra o atributo adicionado à coleção de atributos, em seguida, o **catálogo** elemento usando o **SetAttributeNode** método.</span><span class="sxs-lookup"><span data-stu-id="5551a-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>  
  
 <span data-ttu-id="5551a-110">Com o seguinte XML:</span><span class="sxs-lookup"><span data-stu-id="5551a-110">Given the following XML:</span></span>  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="5551a-111">crie um novo atributo e atribua um valor a ele:</span><span class="sxs-lookup"><span data-stu-id="5551a-111">create a new attribute and give it a value:</span></span>  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 <span data-ttu-id="5551a-112">e anexe-o ao elemento:</span><span class="sxs-lookup"><span data-stu-id="5551a-112">and attach it to the element:</span></span>  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 <span data-ttu-id="5551a-113">**Saída**</span><span class="sxs-lookup"><span data-stu-id="5551a-113">**Output**</span></span>  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="5551a-114">O exemplo de código completo pode ser encontrado em <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="5551a-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>  
  
 <span data-ttu-id="5551a-115">Você também pode criar um **XmlAttribute** nó e use o **InsertBefore** ou **InsertAfter** métodos para colocá-lo na posição apropriada na coleção.</span><span class="sxs-lookup"><span data-stu-id="5551a-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="5551a-116">Se um atributo com o mesmo nome já está presente na coleção de atributos, existente **XmlAttribute** nó for removido da coleção e o novo **XmlAttribute** nó é inserido.</span><span class="sxs-lookup"><span data-stu-id="5551a-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="5551a-117">Isso executa da mesma forma que o **SetAttribute** método.</span><span class="sxs-lookup"><span data-stu-id="5551a-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="5551a-118">Esses métodos tomar, como um parâmetro, um nó existente como um ponto de referência para fazer o **InsertBefore** e **InsertAfter**.</span><span class="sxs-lookup"><span data-stu-id="5551a-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="5551a-119">Se você não fornecer um nó de referência que indica onde inserir o novo nó, o padrão para o **InsertAfter** método é inserir o novo nó no início da coleção.</span><span class="sxs-lookup"><span data-stu-id="5551a-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="5551a-120">A posição padrão para o **InsertBefore**, se nenhum nó de referência for fornecido, o final da coleção.</span><span class="sxs-lookup"><span data-stu-id="5551a-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>  
  
 <span data-ttu-id="5551a-121">Se você tiver criado um **XmlNamedNodeMap** de atributos, você pode adicionar um atributo por nome usando o <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="5551a-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span></span> <span data-ttu-id="5551a-122">Para obter mais informações, consulte [coleções de nó em NamedNodeMaps e em NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span><span class="sxs-lookup"><span data-stu-id="5551a-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span></span>  
  
## <a name="default-attributes"></a><span data-ttu-id="5551a-123">Atributos padrão</span><span class="sxs-lookup"><span data-stu-id="5551a-123">Default Attributes</span></span>  
 <span data-ttu-id="5551a-124">Se você criar um elemento que está declarado para ter um atributo padrão, um novo atributo padrão com seu valor padrão será criado pelo DOM (Document Object Model) XML e anexado ao elemento.</span><span class="sxs-lookup"><span data-stu-id="5551a-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="5551a-125">Os nós filhos do atributo padrão também são criados neste momento.</span><span class="sxs-lookup"><span data-stu-id="5551a-125">The child nodes of the default attribute are also created at this time.</span></span>  
  
## <a name="attribute-child-nodes"></a><span data-ttu-id="5551a-126">Nós filhos do atributo</span><span class="sxs-lookup"><span data-stu-id="5551a-126">Attribute Child Nodes</span></span>  
 <span data-ttu-id="5551a-127">O valor de um nó de atributo se torna os seus nós filhos.</span><span class="sxs-lookup"><span data-stu-id="5551a-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="5551a-128">Há apenas dois tipos de nós filho válido: **XmlText** nós, e **XmlEntityReference** nós.</span><span class="sxs-lookup"><span data-stu-id="5551a-128">There are only two types of valid child nodes: **XmlText** nodes, and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="5551a-129">Esses são nós filho no sentido de que os métodos como **FirstChild** e **LastChild** processá-los como nós filho.</span><span class="sxs-lookup"><span data-stu-id="5551a-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="5551a-130">Essa distinção de um atributo que possui nós filhos é importante ao tentar remover atributos ou nós filhos do atributo.</span><span class="sxs-lookup"><span data-stu-id="5551a-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="5551a-131">Para obter mais informações, consulte [remover atributos de um nó de elemento no DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="5551a-131">For more information, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5551a-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5551a-132">See Also</span></span>  
 [<span data-ttu-id="5551a-133">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="5551a-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)