---
title: Adicionando um DataTable a um DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f70292794866530de5b7abf7dac1edd09d300c94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="adding-a-datatable-to-a-dataset"></a><span data-ttu-id="af804-102">Adicionando um DataTable a um DataSet</span><span class="sxs-lookup"><span data-stu-id="af804-102">Adding a DataTable to a DataSet</span></span>
<span data-ttu-id="af804-103">O ADO.NET permite que você crie objetos <xref:System.Data.DataTable> e adicione-os a um <xref:System.Data.DataSet> existente.</span><span class="sxs-lookup"><span data-stu-id="af804-103">ADO.NET enables you to create <xref:System.Data.DataTable> objects and add them to an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="af804-104">Você pode definir informações de restrição para um <xref:System.Data.DataTable> usando as propriedades <xref:System.Data.DataTable.PrimaryKey%2A> e <xref:System.Data.DataColumn.Unique%2A>.</span><span class="sxs-lookup"><span data-stu-id="af804-104">You can set constraint information for a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.PrimaryKey%2A> and <xref:System.Data.DataColumn.Unique%2A> properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af804-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="af804-105">Example</span></span>  
 <span data-ttu-id="af804-106">O exemplo a seguir constrói um <xref:System.Data.DataSet>, adiciona um novo objeto <xref:System.Data.DataTable> ao <xref:System.Data.DataSet> e adiciona três objetos <xref:System.Data.DataColumn> à tabela.</span><span class="sxs-lookup"><span data-stu-id="af804-106">The following example constructs a <xref:System.Data.DataSet>, adds a new <xref:System.Data.DataTable> object to the <xref:System.Data.DataSet>, and then adds three <xref:System.Data.DataColumn> objects to the table.</span></span> <span data-ttu-id="af804-107">Finalmente, o código define uma coluna como a coluna de chave primária.</span><span class="sxs-lookup"><span data-stu-id="af804-107">Finally, the code sets one column as the primary key column.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a><span data-ttu-id="af804-108">Diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="af804-108">Case Sensitivity</span></span>  
 <span data-ttu-id="af804-109">Duas ou mais tabelas ou relacionamentos com o mesmo nome, mas maiúsculas e minúsculas diferentes, podem existir em um <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="af804-109">Two or more tables or relations with the same name, but different casing, can exist in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="af804-110">Nesses casos, as referências por nome a tabelas e relações diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="af804-110">In such cases, references by name to tables and relations are case sensitive.</span></span> <span data-ttu-id="af804-111">Por exemplo, se o <xref:System.Data.DataSet> **conjunto de dados** contém tabelas **Table1** e **table1**, você deve fazer referência a **Table1** por nome **dataSet.Tables["Table1"]**, e **table1** como **dataSet.Tables["table1"]**.</span><span class="sxs-lookup"><span data-stu-id="af804-111">For example, if the <xref:System.Data.DataSet> **dataSet** contains tables **Table1** and **table1**, you would reference **Table1** by name as **dataSet.Tables["Table1"]**, and **table1** as **dataSet.Tables["table1"]**.</span></span> <span data-ttu-id="af804-112">Tentativa de fazer referência a uma das tabelas como **dataSet.Tables["TABLE1"]** poderia gerar uma exceção.</span><span class="sxs-lookup"><span data-stu-id="af804-112">Attempting to reference either of the tables as **dataSet.Tables["TABLE1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="af804-113">O comportamento de maiúsculas e minúsculas não se aplica se apenas uma tabela ou relacionamento tiver um nome específico.</span><span class="sxs-lookup"><span data-stu-id="af804-113">The case-sensitivity behavior does not apply if only one table or relation has a particular name.</span></span> <span data-ttu-id="af804-114">Por exemplo, se o <xref:System.Data.DataSet> tem apenas **Table1**, você pode fazer referência a ele usando **dataSet.Tables["TABLE1"]**.</span><span class="sxs-lookup"><span data-stu-id="af804-114">For example, if the <xref:System.Data.DataSet> has only **Table1**, you can reference it using **dataSet.Tables["TABLE1"]**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af804-115">A propriedade <xref:System.Data.DataSet.CaseSensitive%2A> da <xref:System.Data.DataSet> não afeta esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="af804-115">The <xref:System.Data.DataSet.CaseSensitive%2A> property of the <xref:System.Data.DataSet> does not affect this behavior.</span></span> <span data-ttu-id="af804-116">A propriedade <xref:System.Data.DataSet.CaseSensitive%2A> aplica-se aos dados no <xref:System.Data.DataSet> e afeta a classificação, a procura, a filtragem, a imposição de restrições, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="af804-116">The <xref:System.Data.DataSet.CaseSensitive%2A> property applies to the data in the <xref:System.Data.DataSet> and affects sorting, searching, filtering, enforcing constraints, and so on.</span></span>  
  
## <a name="namespace-support"></a><span data-ttu-id="af804-117">Suporte a namespace</span><span class="sxs-lookup"><span data-stu-id="af804-117">Namespace Support</span></span>  
 <span data-ttu-id="af804-118">Nas versões do ADO.NET anteriores a 2.0, as duas tabelas não podiam ter o mesmo nome, mesmo se estivessem em namespaces diferentes.</span><span class="sxs-lookup"><span data-stu-id="af804-118">In versions of ADO.NET earlier than 2.0, two tables could not have the same name, even if they were in different namespaces.</span></span> <span data-ttu-id="af804-119">Essa limitação foi removida no ADO.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="af804-119">This limitation was removed in ADO.NET 2.0.</span></span> <span data-ttu-id="af804-120">Um <xref:System.Data.DataSet> pode conter duas tabelas que têm o mesmo valor de propriedade <xref:System.Data.DataTable.TableName%2A>, mas valores de propriedades <xref:System.Data.DataTable.Namespace%2A> diferentes.</span><span class="sxs-lookup"><span data-stu-id="af804-120">A <xref:System.Data.DataSet> can contain two tables that have the same <xref:System.Data.DataTable.TableName%2A> property value but different <xref:System.Data.DataTable.Namespace%2A> property values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af804-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="af804-121">See Also</span></span>  
 <span data-ttu-id="af804-122">[DataSets, DataTables, and DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md) (DataSets, DataTables e DataViews)</span><span class="sxs-lookup"><span data-stu-id="af804-122">[DataSets, DataTables, and DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)</span></span>  
 <span data-ttu-id="af804-123">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="af804-123">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>