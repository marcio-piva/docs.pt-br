---
title: Como alterar o alinhamento horizontal de uma coluna em um ListView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3ed163de9a5b01a3ddab8ef42d21f38d35f48519
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="904eb-102">Como alterar o alinhamento horizontal de uma coluna em um ListView</span><span class="sxs-lookup"><span data-stu-id="904eb-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="904eb-103">Por padrão, o conteúdo de cada coluna em um <xref:System.Windows.Controls.ListViewItem> alinhado à esquerda.</span><span class="sxs-lookup"><span data-stu-id="904eb-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="904eb-104">Você pode alterar o alinhamento de cada coluna, fornecendo um <xref:System.Windows.DataTemplate> e configuração o <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propriedade no elemento dentro do <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="904eb-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="904eb-105">Este tópico mostra como um <xref:System.Windows.Controls.ListView> alinha seu conteúdo por padrão e como alterar o alinhamento de uma coluna em um <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="904eb-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="904eb-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="904eb-106">Example</span></span>  
 <span data-ttu-id="904eb-107">No exemplo a seguir, os dados nas colunas `Title` e `ISBN` são alinhados à esquerda.</span><span class="sxs-lookup"><span data-stu-id="904eb-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="904eb-108">Para alterar o alinhamento do `ISBN` coluna, você precisa especificar que o <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> propriedade de cada <xref:System.Windows.Controls.ListViewItem> é <xref:System.Windows.HorizontalAlignment.Stretch>, de modo que os elementos em cada <xref:System.Windows.Controls.ListViewItem> pode abranger ou ser posicionado ao longo de toda a largura de cada coluna.</span><span class="sxs-lookup"><span data-stu-id="904eb-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="904eb-109">Porque o <xref:System.Windows.Controls.ListView> está associado a uma fonte de dados, você precisa criar um estilo que define o <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="904eb-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="904eb-110">Em seguida, você precisa usar um <xref:System.Windows.DataTemplate> para exibir o conteúdo em vez de usar o <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="904eb-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="904eb-111">Para exibir o `ISBN` de cada modelo, o <xref:System.Windows.DataTemplate> pode conter apenas um <xref:System.Windows.Controls.TextBlock> com seus <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propriedade definida como <xref:System.Windows.HorizontalAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="904eb-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="904eb-112">O exemplo a seguir define o estilo e <xref:System.Windows.DataTemplate> necessário tornar o `ISBN` coluna alinhado à direita e as alterações a <xref:System.Windows.Controls.GridViewColumn> a referência a <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="904eb-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="904eb-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="904eb-113">See Also</span></span>  
 [<span data-ttu-id="904eb-114">Visão geral da vinculação de dados</span><span class="sxs-lookup"><span data-stu-id="904eb-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="904eb-115">Visão geral de modelagem dos dados</span><span class="sxs-lookup"><span data-stu-id="904eb-115">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="904eb-116">Associar dados XML usando um XMLDataProvider e consultas XPath</span><span class="sxs-lookup"><span data-stu-id="904eb-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="904eb-117">Visão geral de ListView</span><span class="sxs-lookup"><span data-stu-id="904eb-117">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)