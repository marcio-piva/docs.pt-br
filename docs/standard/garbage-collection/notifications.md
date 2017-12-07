---
title: "Notificações sobre a coleta de lixo"
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
- cpp
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a><span data-ttu-id="68b31-102">Notificações sobre a coleta de lixo</span><span class="sxs-lookup"><span data-stu-id="68b31-102">Garbage Collection Notifications</span></span>
<span data-ttu-id="68b31-103">Há situações em que uma coleta de lixo completa (ou seja, uma coleção de geração 2) o common language runtime pode afetar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="68b31-103">There are situations in which a full garbage collection (that is, a generation 2 collection) by the common language runtime may adversely affect performance.</span></span> <span data-ttu-id="68b31-104">Isso pode ser um problema particularmente com servidores que processam grandes volumes de pedidos; Nesse caso, uma coleta de lixo longa pode causar um tempo limite da solicitação. Para impedir que uma coleção completa de segundo que ocorrem durante um período crítico, você pode ser notificado de que uma coleta de lixo completa está se aproximando e, em seguida, execute a ação para redirecionar a carga de trabalho para outra instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="68b31-104">This can be an issue particularly with servers that process large volumes of requests; in this case, a long garbage collection can cause a request time-out. To prevent a full collection from occurring during a critical period, you can be notified that a full garbage collection is approaching and then take action to redirect the workload to another server instance.</span></span> <span data-ttu-id="68b31-105">Você pode também induzir uma coleção por conta própria, desde que a instância do servidor atual não é necessário processar solicitações.</span><span class="sxs-lookup"><span data-stu-id="68b31-105">You can also induce a collection yourself, provided that the current server instance does not need to process requests.</span></span>  
  
 <span data-ttu-id="68b31-106">O <xref:System.GC.RegisterForFullGCNotification%2A> método registra uma notificação ser gerado quando o tempo de execução detecta que está se aproximando de uma coleta de lixo completa.</span><span class="sxs-lookup"><span data-stu-id="68b31-106">The <xref:System.GC.RegisterForFullGCNotification%2A> method registers for a notification to be raised when the runtime senses that a full garbage collection is approaching.</span></span> <span data-ttu-id="68b31-107">Há duas partes para esta notificação: quando a coleta de lixo completa está se aproximando e quando a coleta de lixo completa foi concluída.</span><span class="sxs-lookup"><span data-stu-id="68b31-107">There are two parts to this notification: when the full garbage collection is approaching and when the full garbage collection has completed.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="68b31-108">Coletas de lixo de bloqueio somente geram notificações.</span><span class="sxs-lookup"><span data-stu-id="68b31-108">Only blocking garbage collections raise notifications.</span></span> <span data-ttu-id="68b31-109">Quando o [ \<gcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) elemento de configuração estiver habilitado, coletas de lixo em segundo plano não vai disparar notificações.</span><span class="sxs-lookup"><span data-stu-id="68b31-109">When the [\<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration element is enabled, background garbage collections will not raise notifications.</span></span>  
  
 <span data-ttu-id="68b31-110">Para determinar quando uma notificação foi ativada, use o <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="68b31-110">To determine when a notification has been raised, use the <xref:System.GC.WaitForFullGCApproach%2A> and <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span> <span data-ttu-id="68b31-111">Normalmente, você pode usar esses métodos em um `while` loop continuamente obter um <xref:System.GCNotificationStatus> enumeração que mostra o status da notificação.</span><span class="sxs-lookup"><span data-stu-id="68b31-111">Typically, you use these methods in a `while` loop to continually obtain a <xref:System.GCNotificationStatus> enumeration that shows the status of the notification.</span></span> <span data-ttu-id="68b31-112">Se esse valor for <xref:System.GCNotificationStatus.Succeeded>, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="68b31-112">If that value is <xref:System.GCNotificationStatus.Succeeded>, you can do the following:</span></span>  
  
-   <span data-ttu-id="68b31-113">Em resposta a uma notificação obtida com o <xref:System.GC.WaitForFullGCApproach%2A> método, você pode redirecionar a carga de trabalho e possivelmente induzir uma coleção por conta própria.</span><span class="sxs-lookup"><span data-stu-id="68b31-113">In response to a notification obtained with the <xref:System.GC.WaitForFullGCApproach%2A> method, you can redirect the workload and possibly induce a collection yourself.</span></span>  
  
-   <span data-ttu-id="68b31-114">Em resposta a uma notificação obtida com o <xref:System.GC.WaitForFullGCComplete%2A> método, você pode tornar disponíveis para processar solicitações novamente a instância do servidor atual.</span><span class="sxs-lookup"><span data-stu-id="68b31-114">In response to a notification obtained with the <xref:System.GC.WaitForFullGCComplete%2A> method, you can make the current server instance available to process requests again.</span></span> <span data-ttu-id="68b31-115">Você também pode coletar informações.</span><span class="sxs-lookup"><span data-stu-id="68b31-115">You can also gather information.</span></span> <span data-ttu-id="68b31-116">Por exemplo, você pode usar o <xref:System.GC.CollectionCount%2A> método para registrar o número de coleções.</span><span class="sxs-lookup"><span data-stu-id="68b31-116">For example, you can use the <xref:System.GC.CollectionCount%2A> method to record the number of collections.</span></span>  
  
 <span data-ttu-id="68b31-117">O <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> métodos são projetados para trabalhar juntos.</span><span class="sxs-lookup"><span data-stu-id="68b31-117">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods are designed to work together.</span></span> <span data-ttu-id="68b31-118">Usando um sem o outro pode produzir resultados indeterminados.</span><span class="sxs-lookup"><span data-stu-id="68b31-118">Using one without the other can produce indeterminate results.</span></span>  
  
## <a name="full-garbage-collection"></a><span data-ttu-id="68b31-119">Coleta de lixo completa</span><span class="sxs-lookup"><span data-stu-id="68b31-119">Full Garbage Collection</span></span>  
 <span data-ttu-id="68b31-120">O tempo de execução faz com que uma coleta de lixo completa quando qualquer uma das seguintes situações for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="68b31-120">The runtime causes a full garbage collection when any of the following scenarios are true:</span></span>  
  
-   <span data-ttu-id="68b31-121">Memória insuficiente foi promovida na geração 2 para fazer com que a próxima coleta de geração 2.</span><span class="sxs-lookup"><span data-stu-id="68b31-121">Enough memory has been promoted into generation 2 to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="68b31-122">Memória insuficiente foi promovida para o heap de objeto grande para fazer com que a próxima coleta de geração 2.</span><span class="sxs-lookup"><span data-stu-id="68b31-122">Enough memory has been promoted into the large object heap to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="68b31-123">Uma coleção de geração 1 é escalada para uma coleção de geração 2 devido a outros fatores.</span><span class="sxs-lookup"><span data-stu-id="68b31-123">A collection of generation 1 is escalated to a collection of generation 2 due to other factors.</span></span>  
  
 <span data-ttu-id="68b31-124">Os limites que você especificar o <xref:System.GC.RegisterForFullGCNotification%2A> método aplicar para os primeiros dois cenários.</span><span class="sxs-lookup"><span data-stu-id="68b31-124">The thresholds you specify in the <xref:System.GC.RegisterForFullGCNotification%2A> method apply to the first two scenarios.</span></span> <span data-ttu-id="68b31-125">No entanto, o primeiro cenário você não sempre receberão a notificação ao tempo proporcional para os valores de limite especificados por dois motivos:</span><span class="sxs-lookup"><span data-stu-id="68b31-125">However, in the first scenario you will not always receive the notification at the time proportional to the threshold values you specify for two reasons:</span></span>  
  
-   <span data-ttu-id="68b31-126">O tempo de execução não verifica cada alocação de objeto pequeno (por motivos de desempenho).</span><span class="sxs-lookup"><span data-stu-id="68b31-126">The runtime does not check each small object allocation (for performance reasons).</span></span>  
  
-   <span data-ttu-id="68b31-127">Somente geração 1 coleções promovem memória em geração 2.</span><span class="sxs-lookup"><span data-stu-id="68b31-127">Only generation 1 collections promote memory into generation 2.</span></span>  
  
 <span data-ttu-id="68b31-128">O terceiro cenário também contribui para a incerteza de quando você recebe a notificação.</span><span class="sxs-lookup"><span data-stu-id="68b31-128">The third scenario also contributes to the uncertainty of when you will receive the notification.</span></span> <span data-ttu-id="68b31-129">Embora isso não é uma garantia, ele mostrará como uma maneira útil para reduzir os efeitos de uma coleta de lixo completa inoportunos redirecionar as solicitações durante esse tempo ou induzindo coleção por conta própria quando pode ser acomodada melhor.</span><span class="sxs-lookup"><span data-stu-id="68b31-129">Although this is not a guarantee, it does prove to be a useful way to mitigate the effects of an inopportune full garbage collection by redirecting the requests during this time or inducing the collection yourself when it can be better accommodated.</span></span>  
  
## <a name="notification-threshold-parameters"></a><span data-ttu-id="68b31-130">Parâmetros de limite de notificação</span><span class="sxs-lookup"><span data-stu-id="68b31-130">Notification Threshold Parameters</span></span>  
 <span data-ttu-id="68b31-131">O <xref:System.GC.RegisterForFullGCNotification%2A> método tem dois parâmetros para especificar os valores de limite de objetos da geração 2 e o heap de objeto grande.</span><span class="sxs-lookup"><span data-stu-id="68b31-131">The <xref:System.GC.RegisterForFullGCNotification%2A> method has two parameters to specify the threshold values of the generation 2 objects and the large object heap.</span></span> <span data-ttu-id="68b31-132">Quando esses valores forem atendidas, uma notificação de coleta de lixo deve ser gerada.</span><span class="sxs-lookup"><span data-stu-id="68b31-132">When those values are met, a garbage collection notification should be raised.</span></span> <span data-ttu-id="68b31-133">A tabela a seguir descreve esses parâmetros.</span><span class="sxs-lookup"><span data-stu-id="68b31-133">The following table describes these parameters.</span></span>  
  
|<span data-ttu-id="68b31-134">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="68b31-134">Parameter</span></span>|<span data-ttu-id="68b31-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="68b31-135">Description</span></span>|  
|---------------|-----------------|  
|`maxGenerationThreshold`|<span data-ttu-id="68b31-136">Um número entre 1 e 99 que especifica quando a notificação deve ser gerada com base nos objetos promovidos na geração 2.</span><span class="sxs-lookup"><span data-stu-id="68b31-136">A number between 1 and 99 that specifies when the notification should be raised based on the objects promoted in generation 2.</span></span>|  
|`largeObjectHeapThreshold`|<span data-ttu-id="68b31-137">Um número entre 1 e 99 que especifica quando a notificação deve ser gerada com base nos objetos que são alocados no heap de objeto grande.</span><span class="sxs-lookup"><span data-stu-id="68b31-137">A number between 1 and 99 that specifies when the notification should be raised based on the objects that are allocated in the large object heap.</span></span>|  
  
 <span data-ttu-id="68b31-138">Se você especificar um valor que é muito alto, há uma alta probabilidade de que você receberá uma notificação, mas pode ser muito um período de espera antes que o tempo de execução faz com que uma coleção.</span><span class="sxs-lookup"><span data-stu-id="68b31-138">If you specify a value that is too high, there is a high probability that you will receive a notification, but it could be too long a period to wait before the runtime causes a collection.</span></span> <span data-ttu-id="68b31-139">Se você mesmo induzir uma coleção, você pode recuperar mais objetos que seriam recuperados se o tempo de execução faz com que a coleção.</span><span class="sxs-lookup"><span data-stu-id="68b31-139">If you induce a collection yourself, you may reclaim more objects than would be reclaimed if the runtime causes the collection.</span></span>  
  
 <span data-ttu-id="68b31-140">Se você especificar um valor muito baixo, o tempo de execução pode causar a coleção antes de você ter tido tempo suficiente para ser notificado.</span><span class="sxs-lookup"><span data-stu-id="68b31-140">If you specify a value that is too low, the runtime may cause the collection before you have had sufficient time to be notified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68b31-141">Exemplo</span><span class="sxs-lookup"><span data-stu-id="68b31-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="68b31-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="68b31-142">Description</span></span>  
 <span data-ttu-id="68b31-143">No exemplo a seguir, um grupo de servidores de serviço as solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="68b31-143">In the following example, a group of servers service incoming Web requests.</span></span> <span data-ttu-id="68b31-144">Para simular a carga de trabalho de processamento de solicitações, matrizes de bytes são adicionados a um <xref:System.Collections.Generic.List%601> coleção.</span><span class="sxs-lookup"><span data-stu-id="68b31-144">To simulate the workload of processing requests, byte arrays are added to a <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="68b31-145">Cada servidor registra uma notificação de coleta de lixo e, em seguida, inicia um thread no `WaitForFullGCProc` método de usuário para monitorar continuamente o <xref:System.GCNotificationStatus> enumeração que é retornada pelo <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="68b31-145">Each server registers for a garbage collection notification and then starts a thread on the `WaitForFullGCProc` user method to continuously monitor the <xref:System.GCNotificationStatus> enumeration that is returned by the <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span>  
  
 <span data-ttu-id="68b31-146">O <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> métodos chamam seus respectivos métodos de usuário de manipulação de eventos quando uma notificação é gerada:</span><span class="sxs-lookup"><span data-stu-id="68b31-146">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods call their respective event-handling user methods when a notification is raised:</span></span>  
  
-   `OnFullGCApproachNotify`  
  
     <span data-ttu-id="68b31-147">Este método chama o `RedirectRequests` método de usuário, que instrui o servidor de enfileiramento de mensagens de solicitação para suspender a enviar solicitações ao servidor.</span><span class="sxs-lookup"><span data-stu-id="68b31-147">This method calls the `RedirectRequests` user method, which instructs the request queuing server to suspend sending requests to the server.</span></span> <span data-ttu-id="68b31-148">Isso é simulado, definindo a variável de nível de classe `bAllocate` para `false` para que nenhum outro objeto é alocado.</span><span class="sxs-lookup"><span data-stu-id="68b31-148">This is simulated by setting the class-level variable `bAllocate` to `false` so that no more objects are allocated.</span></span>  
  
     <span data-ttu-id="68b31-149">Em seguida, o `FinishExistingRequests` usuário método é chamado para concluir o processamento das solicitações pendentes do servidor.</span><span class="sxs-lookup"><span data-stu-id="68b31-149">Next, the `FinishExistingRequests` user method is called to finish processing the pending server requests.</span></span> <span data-ttu-id="68b31-150">Isso é simulado desmarcando a <xref:System.Collections.Generic.List%601> coleção.</span><span class="sxs-lookup"><span data-stu-id="68b31-150">This is simulated by clearing the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
     <span data-ttu-id="68b31-151">Por fim, uma coleta de lixo seja induzida porque a carga de trabalho é claro.</span><span class="sxs-lookup"><span data-stu-id="68b31-151">Finally, a garbage collection is induced because the workload is light.</span></span>  
  
-   `OnFullGCCompleteNotify`  
  
     <span data-ttu-id="68b31-152">Este método chama o método de usuário `AcceptRequests` para retomar a aceitar solicitações porque o servidor não está mais suscetível a coleta de lixo completa.</span><span class="sxs-lookup"><span data-stu-id="68b31-152">This method calls the user method `AcceptRequests` to resume accepting requests because the server is no longer susceptible to a full garbage collection.</span></span> <span data-ttu-id="68b31-153">Essa ação é simulada, definindo o `bAllocate` variável para `true` para que objetos podem continuar sendo adicionado ao <xref:System.Collections.Generic.List%601> coleção.</span><span class="sxs-lookup"><span data-stu-id="68b31-153">This action is simulated by setting the `bAllocate` variable to `true` so that objects can resume being added to the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
 <span data-ttu-id="68b31-154">O código a seguir contém o `Main` método do exemplo.</span><span class="sxs-lookup"><span data-stu-id="68b31-154">The following code contains the `Main` method of the example.</span></span>  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 <span data-ttu-id="68b31-155">O código a seguir contém o `WaitForFullGCProc` método de usuário, que contém um contínua ao loop para verificar se há notificações de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="68b31-155">The following code contains the `WaitForFullGCProc` user method, that contains a continuous while loop to check for garbage collection notifications.</span></span>  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 <span data-ttu-id="68b31-156">O código a seguir contém o `OnFullGCApproachNotify` método conforme chamado a partir de</span><span class="sxs-lookup"><span data-stu-id="68b31-156">The following code contains the `OnFullGCApproachNotify` method as called from the</span></span>  
  
 <span data-ttu-id="68b31-157">Método `WaitForFullGCProc`.</span><span class="sxs-lookup"><span data-stu-id="68b31-157">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 <span data-ttu-id="68b31-158">O código a seguir contém o `OnFullGCApproachComplete` método conforme chamado a partir de</span><span class="sxs-lookup"><span data-stu-id="68b31-158">The following code contains the `OnFullGCApproachComplete` method as called from the</span></span>  
  
 <span data-ttu-id="68b31-159">Método `WaitForFullGCProc`.</span><span class="sxs-lookup"><span data-stu-id="68b31-159">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 <span data-ttu-id="68b31-160">O código a seguir contém os métodos de usuário que são chamados do `OnFullGCApproachNotify` e `OnFullGCCompleteNotify` métodos.</span><span class="sxs-lookup"><span data-stu-id="68b31-160">The following code contains the user methods that are called from the `OnFullGCApproachNotify` and `OnFullGCCompleteNotify` methods.</span></span> <span data-ttu-id="68b31-161">Os métodos de usuário redirecionam as solicitações, concluir as solicitações existentes e, em seguida, continuar solicitações após a coleta de lixo completa.</span><span class="sxs-lookup"><span data-stu-id="68b31-161">The user methods redirect requests, finish existing requests, and then resume requests after a full garbage collection has occurred.</span></span>  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 <span data-ttu-id="68b31-162">O exemplo de código inteira é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="68b31-162">The entire code sample is as follows:</span></span>  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="68b31-163">Consulte também</span><span class="sxs-lookup"><span data-stu-id="68b31-163">See Also</span></span>  
 [<span data-ttu-id="68b31-164">Coleta de lixo</span><span class="sxs-lookup"><span data-stu-id="68b31-164">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)