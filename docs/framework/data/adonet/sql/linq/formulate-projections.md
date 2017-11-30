---
title: "Formule projeções"
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
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8afd48c6ce7c6313e82a7b74c2271f52833d1f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="formulate-projections"></a><span data-ttu-id="e8cec-102">Formule projeções</span><span class="sxs-lookup"><span data-stu-id="e8cec-102">Formulate Projections</span></span>
<span data-ttu-id="e8cec-103">Os exemplos a seguir mostram como a declaração de `select` em C# e a declaração de `Select` em [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] podem ser combinadas com outros recursos para formar projeções de consulta.</span><span class="sxs-lookup"><span data-stu-id="e8cec-103">The following examples show how the `select` statement in C# and `Select` statement in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8cec-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e8cec-104">Example</span></span>  
 <span data-ttu-id="e8cec-105">O exemplo a seguir usa o `Select` cláusula [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula em c#) para retornar uma sequência de nomes de contato para `Customers`.</span><span class="sxs-lookup"><span data-stu-id="e8cec-105">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="e8cec-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e8cec-106">Example</span></span>  
 <span data-ttu-id="e8cec-107">O exemplo a seguir usa o `Select` cláusula [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula em c#) e *tipos anônimos* para retornar uma sequência de nomes de contatos e números de telefone `Customers`.</span><span class="sxs-lookup"><span data-stu-id="e8cec-107">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="e8cec-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e8cec-108">Example</span></span>  
 <span data-ttu-id="e8cec-109">O exemplo a seguir usa o `Select` cláusula [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula em c#) e *tipos anônimos* para retornar uma sequência de nomes e números de telefone para os funcionários.</span><span class="sxs-lookup"><span data-stu-id="e8cec-109">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="e8cec-110">O `FirstName` e `LastName` campos são combinados em um único campo (`Name`) e o `HomePhone` campo é renomeado para `Phone` na sequência resultante.</span><span class="sxs-lookup"><span data-stu-id="e8cec-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="e8cec-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e8cec-111">Example</span></span>  
 <span data-ttu-id="e8cec-112">O exemplo a seguir usa o `Select` cláusula [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula em c#) e *tipos anônimos* para retornar uma sequência de todos os `ProductID`s e um valor calculado chamado `HalfPrice`.</span><span class="sxs-lookup"><span data-stu-id="e8cec-112">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="e8cec-113">Esse valor é definido como `UnitPrice` dividido por 2.</span><span class="sxs-lookup"><span data-stu-id="e8cec-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="e8cec-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e8cec-114">Example</span></span>  
 <span data-ttu-id="e8cec-115">O exemplo a seguir usa o `Select` cláusula [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula em c#) e um *instrução condicional* para retornar uma sequência de nome do produto e a disponibilidade do produto.</span><span class="sxs-lookup"><span data-stu-id="e8cec-115">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="e8cec-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e8cec-116">Example</span></span>  
 <span data-ttu-id="e8cec-117">O exemplo a seguir usa uma [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` cláusula (`select` cláusula em c#) e um *conhecido tipo* (nome) para retornar uma sequência de nomes de funcionários.</span><span class="sxs-lookup"><span data-stu-id="e8cec-117">The following example uses a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="e8cec-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e8cec-118">Example</span></span>  
 <span data-ttu-id="e8cec-119">O exemplo a seguir usa `Select` e `Where` na [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` e `where` em c#) para retornar um *filtrados sequência* de nomes de contato para clientes em Londres.</span><span class="sxs-lookup"><span data-stu-id="e8cec-119">The following example uses `Select` and `Where` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="e8cec-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e8cec-120">Example</span></span>  
 <span data-ttu-id="e8cec-121">O exemplo a seguir usa uma `Select` cláusula [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula em c#) e *tipos anônimos* para retornar um *em forma de subconjunto* dos dados sobre clientes.</span><span class="sxs-lookup"><span data-stu-id="e8cec-121">The following example uses a `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="e8cec-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e8cec-122">Example</span></span>  
 <span data-ttu-id="e8cec-123">O exemplo a seguir usa consultas aninhadas para retornar os resultados seguintes:</span><span class="sxs-lookup"><span data-stu-id="e8cec-123">The following example uses nested queries to return the following results:</span></span>  
  
-   <span data-ttu-id="e8cec-124">Uma sequência de todos os pedidos e seu `OrderID`correspondente S.</span><span class="sxs-lookup"><span data-stu-id="e8cec-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
-   <span data-ttu-id="e8cec-125">Um subsequence dos itens na ordem para que há desconto.</span><span class="sxs-lookup"><span data-stu-id="e8cec-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
-   <span data-ttu-id="e8cec-126">A quantidade de caixa salva se os custos de enviar não são incluídos.</span><span class="sxs-lookup"><span data-stu-id="e8cec-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="e8cec-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e8cec-127">See Also</span></span>  
 [<span data-ttu-id="e8cec-128">Exemplos de consulta</span><span class="sxs-lookup"><span data-stu-id="e8cec-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)