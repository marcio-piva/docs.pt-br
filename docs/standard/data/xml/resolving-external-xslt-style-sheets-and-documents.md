---
title: Resolvendo folhas de estilos XSLT e documentos externos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 920cfe3b-d525-4bb2-abf6-9431651f9cf9
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a5e84935f9fff1f993a677d408287cd775269f03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="resolving-external-xslt-style-sheets-and-documents"></a><span data-ttu-id="a3f62-102">Resolvendo folhas de estilos XSLT e documentos externos</span><span class="sxs-lookup"><span data-stu-id="a3f62-102">Resolving External XSLT Style Sheets and Documents</span></span>
<span data-ttu-id="a3f62-103">Há várias vezes durante uma transformação quando você precise resolver recursos externos.</span><span class="sxs-lookup"><span data-stu-id="a3f62-103">There are several times during a transformation when you may need to resolve external resources.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3f62-104">A classe <xref:System.Xml.Xsl.XslTransform> está obsoleta no [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3f62-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="a3f62-105">Você pode executar a linguagem XSL Transformations (XSLT) usando a classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="a3f62-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
 <span data-ttu-id="a3f62-106">Há várias vezes durante uma transformação quando você precise resolver recursos externos:</span><span class="sxs-lookup"><span data-stu-id="a3f62-106">There are several times during a transformation when you may need to resolve external resources:</span></span>  
  
-   <span data-ttu-id="a3f62-107">Durante <xref:System.Xml.Xsl.XslTransform.Load%2A> para localizar uma folha de estilos externa.</span><span class="sxs-lookup"><span data-stu-id="a3f62-107">During the <xref:System.Xml.Xsl.XslTransform.Load%2A> to locate an external style sheet.</span></span>  
  
-   <span data-ttu-id="a3f62-108">Durante <xref:System.Xml.Xsl.XslTransform.Load%2A> para resolver alguns elementos de `<xsl:include>` ou de `<xsl:import>` localizados na folha de estilos.</span><span class="sxs-lookup"><span data-stu-id="a3f62-108">During <xref:System.Xml.Xsl.XslTransform.Load%2A> to resolve any `<xsl:include>` or `<xsl:import>` elements found in the style sheet.</span></span>  
  
-   <span data-ttu-id="a3f62-109">Durante <xref:System.Xml.Xsl.XslTransform.Transform%2A> para resolver algumas funções de `document()` .</span><span class="sxs-lookup"><span data-stu-id="a3f62-109">During <xref:System.Xml.Xsl.XslTransform.Transform%2A> to resolve any `document()` functions.</span></span>  
  
## <a name="using-the-xmlresolver-class"></a><span data-ttu-id="a3f62-110">Usando a classe de XmlResolver</span><span class="sxs-lookup"><span data-stu-id="a3f62-110">Using the XmlResolver Class</span></span>  
 <span data-ttu-id="a3f62-111">Se a autenticação for necessária para acessar um recurso de rede, use os métodos de <xref:System.Xml.Xsl.XslTransform.Load%2A> que têm um parâmetro de <xref:System.Xml.XmlResolver> para passar o objeto de <xref:System.Xml.XmlResolver> , que tem as propriedades credenciais necessárias definidas.</span><span class="sxs-lookup"><span data-stu-id="a3f62-111">If authentication is required to access a network resource, use the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods that have an <xref:System.Xml.XmlResolver> parameter to pass the <xref:System.Xml.XmlResolver> object, which has the necessary credential properties set.</span></span>  
  
 <span data-ttu-id="a3f62-112">Se você tiver <xref:System.Xml.XmlResolver> personalizado que você deseja usar, ou se você precisar especificar credenciais diferentes, a tabela a seguir lista a tarefa necessária, como quando o recurso externo precisar a resolução.</span><span class="sxs-lookup"><span data-stu-id="a3f62-112">If you have a custom <xref:System.Xml.XmlResolver> that you want to use, or if you need to specify different credentials, the following table lists the task required, depending on when the external resource needs resolution.</span></span>  
  
|<span data-ttu-id="a3f62-113">Processo requer que a resolução</span><span class="sxs-lookup"><span data-stu-id="a3f62-113">What process requires resolution</span></span>|<span data-ttu-id="a3f62-114">Tarefa necessária</span><span class="sxs-lookup"><span data-stu-id="a3f62-114">Task required</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="a3f62-115">Durante <xref:System.Xml.Xsl.XslTransform.Load%2A> para localizar a folha de estilos.</span><span class="sxs-lookup"><span data-stu-id="a3f62-115">During <xref:System.Xml.Xsl.XslTransform.Load%2A> to locate the style sheet.</span></span>|<span data-ttu-id="a3f62-116">Especificar o método sobrecarregado de <xref:System.Xml.Xsl.XslTransform.Load%2A> que aceita, como um parâmetro, <xref:System.Xml.XmlResolver> se a folha de estilos é um recurso que requer credenciais.</span><span class="sxs-lookup"><span data-stu-id="a3f62-116">Specify the overloaded <xref:System.Xml.Xsl.XslTransform.Load%2A> method that takes, as a parameter, an <xref:System.Xml.XmlResolver> if the style sheet is on a resource that requires credentials.</span></span>|  
|<span data-ttu-id="a3f62-117">Durante <xref:System.Xml.Xsl.XslTransform.Load%2A> para resolver `<xsl:include>` ou `<xsl:import>`.</span><span class="sxs-lookup"><span data-stu-id="a3f62-117">During <xref:System.Xml.Xsl.XslTransform.Load%2A> to resolve `<xsl:include>` or `<xsl:import>`.</span></span>|<span data-ttu-id="a3f62-118">Especificar o método sobrecarregado de <xref:System.Xml.Xsl.XslTransform.Load%2A> que aceita, como um parâmetro, <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="a3f62-118">Specify the overloaded <xref:System.Xml.Xsl.XslTransform.Load%2A> method that takes, as a parameter, an <xref:System.Xml.XmlResolver>.</span></span> <span data-ttu-id="a3f62-119"><xref:System.Xml.XmlResolver> é usado para carregar as folhas de estilos referenciadas pelas declarações de `import` ou de `include` .</span><span class="sxs-lookup"><span data-stu-id="a3f62-119">The <xref:System.Xml.XmlResolver> is used to load the style sheets referenced by the `import` or `include` statements.</span></span> <span data-ttu-id="a3f62-120">Se você passar em `null`, os recursos externos não são resolvidos.</span><span class="sxs-lookup"><span data-stu-id="a3f62-120">If you pass in `null`, the external resources are not resolved.</span></span>|  
|<span data-ttu-id="a3f62-121">Durante uma transformação resolver qualquer `document()` funciona.</span><span class="sxs-lookup"><span data-stu-id="a3f62-121">During a transformation to resolve any `document()` functions.</span></span>|<span data-ttu-id="a3f62-122">Especifique o <xref:System.Xml.XmlResolver> durante a transformação usando o <xref:System.Xml.Xsl.XslTransform.Transform%2A> método que utiliza um <xref:System.Xml.XmlResolver> argumento.</span><span class="sxs-lookup"><span data-stu-id="a3f62-122">Specify the <xref:System.Xml.XmlResolver> during the transformation by using the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method that takes an <xref:System.Xml.XmlResolver> argument.</span></span>|  
  
 <span data-ttu-id="a3f62-123">O `document()` função recupera outros recursos do XML de uma folha de estilo, além para os dados iniciais do XML fornecidos pelo fluxo de entrada.</span><span class="sxs-lookup"><span data-stu-id="a3f62-123">The `document()` function retrieves other XML resources from a style sheet, in addition to the initial XML data provided by the input stream.</span></span> <span data-ttu-id="a3f62-124">Já que essa função permite a inclusão de dados XML que podem ser encontrados em outro lugar, <xref:System.Xml.XmlResolver> com um valor de `null` fornecido para o método de <xref:System.Xml.Xsl.XslTransform.Transform%2A> impede que a função de `document()` executar.</span><span class="sxs-lookup"><span data-stu-id="a3f62-124">Since this function allows the inclusion of XML data that can be located elsewhere, an <xref:System.Xml.XmlResolver> with a `null` value supplied to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method prevents the `document()` function from executing.</span></span> <span data-ttu-id="a3f62-125">Se você desejar usar a função de `document()` , use o método de <xref:System.Xml.Xsl.XslTransform.Transform%2A> que leva <xref:System.Xml.XmlResolver> como um parâmetro, além de ter o conjunto de permissões apropriado.</span><span class="sxs-lookup"><span data-stu-id="a3f62-125">If you want to use the `document()` function, use the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method that takes an <xref:System.Xml.XmlResolver> as a parameter, in addition to having the appropriate permission set.</span></span>  
  
 <span data-ttu-id="a3f62-126">Para obter mais informações sobre o método de <xref:System.Xml.Xsl.XslTransform.Load%2A> e o uso de <xref:System.Xml.XmlResolver>, consulte <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a3f62-126">For more information on the <xref:System.Xml.Xsl.XslTransform.Load%2A> method and its use of the <xref:System.Xml.XmlResolver>, see <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a3f62-127">Quando o método de <xref:System.Xml.Xsl.XslTransform.Transform%2A> é chamado, as permissões são calculadas com a evidência fornecida em tempo de carregamento, e esse conjunto de permissões é atribuído ao processo inteiro de transformação.</span><span class="sxs-lookup"><span data-stu-id="a3f62-127">When the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is called, permissions are calculated against the evidence provided at load time, and that permission set is assigned to the entire transformation process.</span></span> <span data-ttu-id="a3f62-128">Se a função de `document()` tentar iniciar uma ação que requer permissões não encontradas no dataset, uma exceção é lançada.</span><span class="sxs-lookup"><span data-stu-id="a3f62-128">If the `document()` function attempts to initiate an action that requires permissions not found in the set, an exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f62-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a3f62-129">See Also</span></span>  
 [<span data-ttu-id="a3f62-130">Transformações XSLT com a classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="a3f62-130">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [<span data-ttu-id="a3f62-131">Classe XslTransform implementa do processador XSLT</span><span class="sxs-lookup"><span data-stu-id="a3f62-131">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [<span data-ttu-id="a3f62-132">Saída de um XslTransform</span><span class="sxs-lookup"><span data-stu-id="a3f62-132">Outputs from an XslTransform</span></span>](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md)  
 [<span data-ttu-id="a3f62-133">Transformações XSLT sobre diferentes armazena</span><span class="sxs-lookup"><span data-stu-id="a3f62-133">XSLT Transformations Over Different Stores</span></span>](../../../../docs/standard/data/xml/xslt-transformations-over-different-stores.md)  
 [<span data-ttu-id="a3f62-134">XsltArgumentList para parâmetros de folha de estilos e objetos de extensão</span><span class="sxs-lookup"><span data-stu-id="a3f62-134">XsltArgumentList for Style Sheet Parameters and Extension Objects</span></span>](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)  
 [<span data-ttu-id="a3f62-135">XSLT folha de estilos de script usando \<msxsl: script ></span><span class="sxs-lookup"><span data-stu-id="a3f62-135">XSLT Stylesheet Scripting Using \<msxsl:script></span></span>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md)  
 [<span data-ttu-id="a3f62-136">Suporte para a função msxsl</span><span class="sxs-lookup"><span data-stu-id="a3f62-136">Support for the msxsl:node-set() Function</span></span>](../../../../docs/standard/data/xml/support-for-the-msxsl-node-set-function.md)  
 [<span data-ttu-id="a3f62-137">XPathNavigator nas transformações</span><span class="sxs-lookup"><span data-stu-id="a3f62-137">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [<span data-ttu-id="a3f62-138">XPathNodeIterator nas transformações</span><span class="sxs-lookup"><span data-stu-id="a3f62-138">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [<span data-ttu-id="a3f62-139">Entrada XPathDocument inseriu a XslTransform</span><span class="sxs-lookup"><span data-stu-id="a3f62-139">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [<span data-ttu-id="a3f62-140">Entrada de XmlDataDocument inseriu a XslTransform</span><span class="sxs-lookup"><span data-stu-id="a3f62-140">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)  
 [<span data-ttu-id="a3f62-141">Entrada de XmlDocument inseriu a XslTransform</span><span class="sxs-lookup"><span data-stu-id="a3f62-141">XmlDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)