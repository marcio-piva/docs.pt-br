---
title: Como implementar PriorityBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9753462908928eaf177e100a16186826bf4828ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="110e4-102">Como implementar PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="110e4-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="110e4-103"><xref:System.Windows.Data.PriorityBinding>em [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funciona especificando uma lista de associações.</span><span class="sxs-lookup"><span data-stu-id="110e4-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="110e4-104">A lista de associações é ordenada da prioridade mais alta para a prioridade mais baixa.</span><span class="sxs-lookup"><span data-stu-id="110e4-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="110e4-105">Se a associação de maior prioridade retornar um valor com êxito quando ele é processado, nunca haverá a necessidade de processar as outras associações na lista.</span><span class="sxs-lookup"><span data-stu-id="110e4-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="110e4-106">Pode ser o caso de a associação de maior prioridade levar muito tempo para ser avaliada, a próxima prioridade mais alta que retorna um valor com sucesso será usada até que uma associação de uma prioridade mais alta retorne um valor com êxito.</span><span class="sxs-lookup"><span data-stu-id="110e4-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="110e4-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="110e4-107">Example</span></span>  
 <span data-ttu-id="110e4-108">Para demonstrar como <xref:System.Windows.Data.PriorityBinding> funciona, o `AsyncDataSource` objeto foi criado com as seguintes três propriedades: `FastDP`, `SlowerDP`, e `SlowestDP`.</span><span class="sxs-lookup"><span data-stu-id="110e4-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="110e4-109">O acessador get de `FastDP` retorna o valor do membro de dados `_fastDP`.</span><span class="sxs-lookup"><span data-stu-id="110e4-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="110e4-110">O acessador get da `SlowerDP` aguarda três segundos antes de retornar o valor do membro de dados `_slowerDP`.</span><span class="sxs-lookup"><span data-stu-id="110e4-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="110e4-111">O acessador get da `SlowestDP` aguarda cinco segundos antes de retornar o valor do membro de dados `_slowestDP`.</span><span class="sxs-lookup"><span data-stu-id="110e4-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="110e4-112">Este exemplo tem fins apenas demonstrativos.</span><span class="sxs-lookup"><span data-stu-id="110e4-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="110e4-113">As diretrizes de [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] recomendam não definir propriedades que são ordens de magnitude mais lentas do que seria um conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="110e4-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="110e4-114">Para obter mais informações, consulte [NIB: escolhendo entre propriedades e métodos](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af).</span><span class="sxs-lookup"><span data-stu-id="110e4-114">For more information, see [NIB: Choosing Between Properties and Methods](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af).</span></span>  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="110e4-115">O <xref:System.Windows.Controls.TextBlock.Text%2A> propriedade associa o acima `AsyncDS` usando <xref:System.Windows.Data.PriorityBinding>:</span><span class="sxs-lookup"><span data-stu-id="110e4-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="110e4-116">Quando o mecanismo de associação processa o <xref:System.Windows.Data.Binding> objetos, ele começa com a primeira <xref:System.Windows.Data.Binding>, que é associado a `SlowestDP` propriedade.</span><span class="sxs-lookup"><span data-stu-id="110e4-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="110e4-117">Quando isso <xref:System.Windows.Data.Binding> é processado, ele não retorna um valor com êxito porque ele está em suspensão por 5 segundos, até o próximo <xref:System.Windows.Data.Binding> elemento é processado.</span><span class="sxs-lookup"><span data-stu-id="110e4-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="110e4-118">A próxima <xref:System.Windows.Data.Binding> não retorna um valor com sucesso porque está dormindo por 3 segundos.</span><span class="sxs-lookup"><span data-stu-id="110e4-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="110e4-119">O mecanismo de associação, em seguida, move para o próximo <xref:System.Windows.Data.Binding> elemento, que é associado a `FastDP` propriedade.</span><span class="sxs-lookup"><span data-stu-id="110e4-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="110e4-120">Isso <xref:System.Windows.Data.Binding> retorna o valor "Fast Value".</span><span class="sxs-lookup"><span data-stu-id="110e4-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="110e4-121">O <xref:System.Windows.Controls.TextBlock> agora mostra o valor "Fast Value".</span><span class="sxs-lookup"><span data-stu-id="110e4-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="110e4-122">Depois de 3 segundos, a propriedade `SlowerDP` retorna o valor “Valor mais Lento”.</span><span class="sxs-lookup"><span data-stu-id="110e4-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="110e4-123">O <xref:System.Windows.Controls.TextBlock> , em seguida, exibe o valor "mais lento".</span><span class="sxs-lookup"><span data-stu-id="110e4-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="110e4-124">Depois de 5 segundos, a propriedade `SlowestDP` retorna o valor “Valor mais Lento”.</span><span class="sxs-lookup"><span data-stu-id="110e4-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="110e4-125">Essa associação tem a maior prioridade porque é listada primeiro.</span><span class="sxs-lookup"><span data-stu-id="110e4-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="110e4-126">O <xref:System.Windows.Controls.TextBlock> agora exibe o valor "mais lento".</span><span class="sxs-lookup"><span data-stu-id="110e4-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="110e4-127">Consulte <xref:System.Windows.Data.PriorityBinding> para obter informações sobre o que é considerado um valor de retorno com sucesso de uma associação.</span><span class="sxs-lookup"><span data-stu-id="110e4-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="110e4-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="110e4-128">See Also</span></span>  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="110e4-129">Visão geral da vinculação de dados</span><span class="sxs-lookup"><span data-stu-id="110e4-129">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="110e4-130">Tópicos explicativos</span><span class="sxs-lookup"><span data-stu-id="110e4-130">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)