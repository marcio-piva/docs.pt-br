---
title: Como agrupar, classificar e filtrar dados no controle DataGrid
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
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3c8afacfafbe14794bf17a4e9a4df7c175a3668
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="617ae-102">Como agrupar, classificar e filtrar dados no controle DataGrid</span><span class="sxs-lookup"><span data-stu-id="617ae-102">How to: Group, Sort, and Filter Data in the DataGrid Control</span></span>
<span data-ttu-id="617ae-103">Geralmente é útil exibir dados em um <xref:System.Windows.Controls.DataGrid> de diferentes maneiras por agrupamento, classificação e filtragem dos dados.</span><span class="sxs-lookup"><span data-stu-id="617ae-103">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="617ae-104">Para agrupar, classificar e filtrar os dados em um <xref:System.Windows.Controls.DataGrid>, você associa um <xref:System.Windows.Data.CollectionView> que dá suporte a essas funções.</span><span class="sxs-lookup"><span data-stu-id="617ae-104">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="617ae-105">Em seguida, você pode trabalhar com os dados de <xref:System.Windows.Data.CollectionView> sem afetar os dados de origem subjacentes.</span><span class="sxs-lookup"><span data-stu-id="617ae-105">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="617ae-106">As alterações no modo de exibição de coleção são refletidas no <xref:System.Windows.Controls.DataGrid> interface do usuário (IU).</span><span class="sxs-lookup"><span data-stu-id="617ae-106">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>  
  
 <span data-ttu-id="617ae-107">O <xref:System.Windows.Data.CollectionView> classe fornece agrupando e classificando funcionalidade para uma fonte de dados que implementa o <xref:System.Collections.IEnumerable> interface.</span><span class="sxs-lookup"><span data-stu-id="617ae-107">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="617ae-108">O <xref:System.Windows.Data.CollectionViewSource> classe permite que você defina as propriedades de um <xref:System.Windows.Data.CollectionView> do XAML.</span><span class="sxs-lookup"><span data-stu-id="617ae-108">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>  
  
 <span data-ttu-id="617ae-109">Neste exemplo, uma coleção de `Task` objetos está associado a um <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="617ae-109">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="617ae-110">O <xref:System.Windows.Data.CollectionViewSource> é usado como o <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para o <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="617ae-110">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="617ae-111">Agrupamento, classificação e filtragem são executadas no <xref:System.Windows.Data.CollectionViewSource> e são exibidos no <xref:System.Windows.Controls.DataGrid> interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="617ae-111">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="617ae-112">![Dados agrupados em uma grade de dados](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span><span class="sxs-lookup"><span data-stu-id="617ae-112">![Grouped data in a DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span></span>  
<span data-ttu-id="617ae-113">Dados Agrupados em um DataGrid</span><span class="sxs-lookup"><span data-stu-id="617ae-113">Grouped Data in a DataGrid</span></span>  
  
## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="617ae-114">Usando um CollectionViewSource como ItemsSource</span><span class="sxs-lookup"><span data-stu-id="617ae-114">Using a CollectionViewSource as an ItemsSource</span></span>  
 <span data-ttu-id="617ae-115">Para o grupo, classificar e filtrar dados em um <xref:System.Windows.Controls.DataGrid> controle, você associa o <xref:System.Windows.Controls.DataGrid> para um <xref:System.Windows.Data.CollectionView> que dá suporte a essas funções.</span><span class="sxs-lookup"><span data-stu-id="617ae-115">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="617ae-116">Neste exemplo, o <xref:System.Windows.Controls.DataGrid> está associado a um <xref:System.Windows.Data.CollectionViewSource> que fornece essas funções para um <xref:System.Collections.Generic.List%601> de `Task` objetos.</span><span class="sxs-lookup"><span data-stu-id="617ae-116">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>  
  
#### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="617ae-117">Para associar um DataGrid a um CollectionViewSource</span><span class="sxs-lookup"><span data-stu-id="617ae-117">To bind a DataGrid to a CollectionViewSource</span></span>  
  
1.  <span data-ttu-id="617ae-118">Criar uma coleção de dados que implementa o <xref:System.Collections.IEnumerable> interface.</span><span class="sxs-lookup"><span data-stu-id="617ae-118">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
     <span data-ttu-id="617ae-119">Se você usar <xref:System.Collections.Generic.List%601> para criar sua coleção, você deve criar uma nova classe que herda de <xref:System.Collections.Generic.List%601> em vez de instanciar uma instância de <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="617ae-119">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="617ae-120">Isso permite associar dados à coleção em XAML.</span><span class="sxs-lookup"><span data-stu-id="617ae-120">This enables you to data bind to the collection in XAML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="617ae-121">Os objetos na coleção devem implementar a <xref:System.ComponentModel.INotifyPropertyChanged> interface alterado e o <xref:System.ComponentModel.IEditableObject> interface para que o <xref:System.Windows.Controls.DataGrid> responder corretamente a alterações de propriedade e edições.</span><span class="sxs-lookup"><span data-stu-id="617ae-121">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="617ae-122">Para obter mais informações, consulte [Implementar notificação de alteração da propriedade](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="617ae-122">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  <span data-ttu-id="617ae-123">No XAML, crie uma instância da classe de coleção e defina a [Diretiva x:Key](../../../../docs/framework/xaml-services/x-key-directive.md).</span><span class="sxs-lookup"><span data-stu-id="617ae-123">In XAML, create an instance of the collection class and set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md).</span></span>  
  
3.  <span data-ttu-id="617ae-124">No XAML, crie uma instância do <xref:System.Windows.Data.CollectionViewSource> classe, defina o [diretiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md)e defina a instância de sua classe de coleção como o <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span><span class="sxs-lookup"><span data-stu-id="617ae-124">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  <span data-ttu-id="617ae-125">Criar uma instância do <xref:System.Windows.Controls.DataGrid> de classe e defina o <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propriedade para o <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="617ae-125">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  <span data-ttu-id="617ae-126">Para acessar o <xref:System.Windows.Data.CollectionViewSource> do seu código, use o <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> método para obter uma referência para o <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="617ae-126">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="617ae-127">Agrupando itens em um DataGrid</span><span class="sxs-lookup"><span data-stu-id="617ae-127">Grouping items in a DataGrid</span></span>  
 <span data-ttu-id="617ae-128">Para especificar como os itens são agrupados em um <xref:System.Windows.Controls.DataGrid>, você usa o <xref:System.Windows.Data.PropertyGroupDescription> tipo para agrupar os itens na exibição da fonte.</span><span class="sxs-lookup"><span data-stu-id="617ae-128">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>  
  
#### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="617ae-129">Para agrupar itens em um DataGrid usando XAML</span><span class="sxs-lookup"><span data-stu-id="617ae-129">To group items in a DataGrid using XAML</span></span>  
  
1.  <span data-ttu-id="617ae-130">Criar um <xref:System.Windows.Data.PropertyGroupDescription> que especifica a propriedade para agrupar por.</span><span class="sxs-lookup"><span data-stu-id="617ae-130">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="617ae-131">Você pode especificar a propriedade no XAML ou no código.</span><span class="sxs-lookup"><span data-stu-id="617ae-131">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="617ae-132">Em XAML, definir o <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> para o nome da propriedade para agrupar por.</span><span class="sxs-lookup"><span data-stu-id="617ae-132">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>  
  
    2.  <span data-ttu-id="617ae-133">No código, passe o nome da propriedade segundo a qual o agrupamento será feito ao construtor.</span><span class="sxs-lookup"><span data-stu-id="617ae-133">In code, pass the name of the property to group by to the constructor.</span></span>  
  
2.  <span data-ttu-id="617ae-134">Adicionar o <xref:System.Windows.Data.PropertyGroupDescription> para o <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> coleção.</span><span class="sxs-lookup"><span data-stu-id="617ae-134">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="617ae-135">Adicione instâncias adicionais do <xref:System.Windows.Data.PropertyGroupDescription> para o <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> coleção para adicionar mais níveis de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="617ae-135">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  <span data-ttu-id="617ae-136">Para remover um grupo, remova o <xref:System.Windows.Data.PropertyGroupDescription> do <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> coleção.</span><span class="sxs-lookup"><span data-stu-id="617ae-136">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
5.  <span data-ttu-id="617ae-137">Para remover todos os grupos, chame o <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> método o <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> coleção.</span><span class="sxs-lookup"><span data-stu-id="617ae-137">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 <span data-ttu-id="617ae-138">Quando os itens são agrupados no <xref:System.Windows.Controls.DataGrid>, você pode definir um <xref:System.Windows.Controls.GroupStyle> que especifica a aparência de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="617ae-138">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="617ae-139">Aplicar o <xref:System.Windows.Controls.GroupStyle> ao ser adicionado a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> coleção da grade de dados.</span><span class="sxs-lookup"><span data-stu-id="617ae-139">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="617ae-140">Se tiver vários níveis de agrupamento, você poderá aplicar estilos diferentes a cada nível de grupo.</span><span class="sxs-lookup"><span data-stu-id="617ae-140">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="617ae-141">Os estilos são aplicados na ordem em que são definidos.</span><span class="sxs-lookup"><span data-stu-id="617ae-141">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="617ae-142">Por exemplo, se você definir dois estilos, o primeiro será aplicado a grupos de linhas de nível superior.</span><span class="sxs-lookup"><span data-stu-id="617ae-142">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="617ae-143">O segundo estilo será aplicado a todos os grupos de linhas no segundo nível e abaixo.</span><span class="sxs-lookup"><span data-stu-id="617ae-143">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="617ae-144">O <xref:System.Windows.FrameworkElement.DataContext%2A> do <xref:System.Windows.Controls.GroupStyle> é o <xref:System.Windows.Data.CollectionViewGroup> que representa o grupo.</span><span class="sxs-lookup"><span data-stu-id="617ae-144">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>  
  
#### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="617ae-145">Para alterar a aparência dos cabeçalhos de grupos de linhas</span><span class="sxs-lookup"><span data-stu-id="617ae-145">To change the appearance of row group headers</span></span>  
  
1.  <span data-ttu-id="617ae-146">Criar um <xref:System.Windows.Controls.GroupStyle> que define a aparência do grupo de linhas.</span><span class="sxs-lookup"><span data-stu-id="617ae-146">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>  
  
2.  <span data-ttu-id="617ae-147">Coloque o <xref:System.Windows.Controls.GroupStyle> dentro de `<DataGrid.GroupStyle>` marcas.</span><span class="sxs-lookup"><span data-stu-id="617ae-147">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="617ae-148">Classificando itens em um DataGrid</span><span class="sxs-lookup"><span data-stu-id="617ae-148">Sorting items in a DataGrid</span></span>  
 <span data-ttu-id="617ae-149">Para especificar como os itens são classificados em uma <xref:System.Windows.Controls.DataGrid>, você usa o <xref:System.ComponentModel.SortDescription> tipo para classificar os itens na exibição da fonte.</span><span class="sxs-lookup"><span data-stu-id="617ae-149">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>  
  
#### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="617ae-150">Para classificar itens em um DataGrid</span><span class="sxs-lookup"><span data-stu-id="617ae-150">To sort items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="617ae-151">Criar um <xref:System.ComponentModel.SortDescription> que especifica a propriedade classificar por.</span><span class="sxs-lookup"><span data-stu-id="617ae-151">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="617ae-152">Você pode especificar a propriedade no XAML ou no código.</span><span class="sxs-lookup"><span data-stu-id="617ae-152">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="617ae-153">Em XAML, definir o <xref:System.ComponentModel.SortDescription.PropertyName%2A> para o nome da propriedade de classificação.</span><span class="sxs-lookup"><span data-stu-id="617ae-153">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>  
  
    2.  <span data-ttu-id="617ae-154">No código, passe o nome da propriedade de classificação e o <xref:System.ComponentModel.ListSortDirection> para o construtor.</span><span class="sxs-lookup"><span data-stu-id="617ae-154">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>  
  
2.  <span data-ttu-id="617ae-155">Adicionar o <xref:System.ComponentModel.SortDescription> para o <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> coleção.</span><span class="sxs-lookup"><span data-stu-id="617ae-155">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="617ae-156">Adicione instâncias adicionais do <xref:System.ComponentModel.SortDescription> para o <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> coleção para classificar por propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="617ae-156">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="617ae-157">Filtrando itens em um DataGrid</span><span class="sxs-lookup"><span data-stu-id="617ae-157">Filtering items in a DataGrid</span></span>  
 <span data-ttu-id="617ae-158">Para filtrar itens em uma <xref:System.Windows.Controls.DataGrid> usando um <xref:System.Windows.Data.CollectionViewSource>, forneça a lógica de filtragem no manipulador para o <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="617ae-158">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
#### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="617ae-159">Para filtrar itens em um DataGrid</span><span class="sxs-lookup"><span data-stu-id="617ae-159">To filter items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="617ae-160">Adicionar um manipulador para o <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="617ae-160">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
2.  <span data-ttu-id="617ae-161">No <xref:System.Windows.Data.CollectionViewSource.Filter> manipulador de eventos, definir a lógica de filtragem.</span><span class="sxs-lookup"><span data-stu-id="617ae-161">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>  
  
     <span data-ttu-id="617ae-162">O filtro será aplicado sempre que a exibição for atualizada.</span><span class="sxs-lookup"><span data-stu-id="617ae-162">The filter will be applied every time the view is refreshed.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 <span data-ttu-id="617ae-163">Como alternativa, você pode filtrar itens em uma <xref:System.Windows.Controls.DataGrid> criando um método que fornece a lógica de filtragem e configuração de <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> propriedade para aplicar o filtro.</span><span class="sxs-lookup"><span data-stu-id="617ae-163">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="617ae-164">Para ver um exemplo desse método, consulte [Filtrar dados em uma exibição](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="617ae-164">To see an example of this method, see [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="617ae-165">Exemplo</span><span class="sxs-lookup"><span data-stu-id="617ae-165">Example</span></span>  
 <span data-ttu-id="617ae-166">O exemplo a seguir demonstra o agrupamento, classificação e filtragem `Task` dados em um <xref:System.Windows.Data.CollectionViewSource> e exibindo agrupados, classificados e filtrados `Task` dados em um <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="617ae-166">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="617ae-167">O <xref:System.Windows.Data.CollectionViewSource> é usado como o <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para o <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="617ae-167">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="617ae-168">Agrupamento, classificação e filtragem são executadas no <xref:System.Windows.Data.CollectionViewSource> e são exibidos no <xref:System.Windows.Controls.DataGrid> interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="617ae-168">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="617ae-169">Para testar este exemplo, você precisará ajustar o nome de DGGroupSortFilterExample para corresponder ao nome do seu projeto.</span><span class="sxs-lookup"><span data-stu-id="617ae-169">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="617ae-170">Se você estiver usando o Visual Basic, você precisará alterar o nome da classe para <xref:System.Windows.Window> à seguinte.</span><span class="sxs-lookup"><span data-stu-id="617ae-170">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xaml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="617ae-171">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="617ae-171">Compiling the Code</span></span>  
  
-  
  
## <a name="robust-programming"></a><span data-ttu-id="617ae-172">Programação robusta</span><span class="sxs-lookup"><span data-stu-id="617ae-172">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="617ae-173">Segurança do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="617ae-173">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="617ae-174">Consulte também</span><span class="sxs-lookup"><span data-stu-id="617ae-174">See Also</span></span>  
 [<span data-ttu-id="617ae-175">Visão geral da vinculação de dados</span><span class="sxs-lookup"><span data-stu-id="617ae-175">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="617ae-176">Criar e associar a um ObservableCollection</span><span class="sxs-lookup"><span data-stu-id="617ae-176">Create and Bind to an ObservableCollection</span></span>](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)  
 [<span data-ttu-id="617ae-177">Filtrar dados em uma exibição</span><span class="sxs-lookup"><span data-stu-id="617ae-177">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="617ae-178">Classificar dados em uma exibição</span><span class="sxs-lookup"><span data-stu-id="617ae-178">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="617ae-179">Classificar e agrupar dados usando uma exibição em XAML</span><span class="sxs-lookup"><span data-stu-id="617ae-179">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)