---
title: Rastreamento de dados no ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a71b28a1653b72d212455e99f8aa0101bb74e7a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="data-tracing-in-adonet"></a><span data-ttu-id="e7ee7-102">Rastreamento de dados no ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e7ee7-102">Data Tracing in ADO.NET</span></span>
<span data-ttu-id="e7ee7-103">Funcionalidade de rastreamento de dados interna que é compatível com os provedores de dados .NET para recursos do ADO.NET [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], Oracle, OLE DB e ODBC, bem como o ADO.NET <xref:System.Data.DataSet>e o [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] protocolos de rede.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-103">ADO.NET features built-in data tracing functionality that is supported by the .NET data providers for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], Oracle, OLE DB and ODBC, as well as the ADO.NET <xref:System.Data.DataSet>, and the [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] network protocols.</span></span>  
  
 <span data-ttu-id="e7ee7-104">Rastreamento de dados chamadas de API de acesso podem ajudar a diagnosticar os problemas a seguir:</span><span class="sxs-lookup"><span data-stu-id="e7ee7-104">Tracing data access API calls can help diagnose the following problems:</span></span>  
  
-   <span data-ttu-id="e7ee7-105">Incompatibilidade de esquema entre cliente e o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-105">Schema mismatch between client program and the database.</span></span>  
  
-   <span data-ttu-id="e7ee7-106">Indisponibilidade do banco de dados ou problemas de biblioteca de rede.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-106">Database unavailability or network library problems.</span></span>  
  
-   <span data-ttu-id="e7ee7-107">SQL incorreto se hard codificado ou gerado por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-107">Incorrect SQL whether hard coded or generated by an application.</span></span>  
  
-   <span data-ttu-id="e7ee7-108">Lógica de programação incorretova.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-108">Incorrect programming logic.</span></span>  
  
-   <span data-ttu-id="e7ee7-109">Problemas resultantes da interação entre os vários componentes do ADO.NET ou entre seus próprios componentes e ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-109">Issues resulting from the interaction between multiple ADO.NET components or between ADO.NET and your own components.</span></span>  
  
 <span data-ttu-id="e7ee7-110">Para dar suporte a tecnologias de rastreamento diferente, o rastreamento é extensível, para que um desenvolvedor pode rastrear um problema em qualquer nível da pilha do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-110">To support different trace technologies, tracing is extensible, so a developer can trace a problem at any level of the application stack.</span></span> <span data-ttu-id="e7ee7-111">Embora o rastreamento não é um recurso somente ADO.NET, provedores Microsoft aproveitar generalizada de rastreamento e instrumentação APIs.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-111">Although tracing is not an ADO.NET-only feature, Microsoft providers take advantage of generalized tracing and instrumentation APIs.</span></span>  
  
 <span data-ttu-id="e7ee7-112">Para obter mais informações sobre a configuração e configurando o rastreamento gerenciado no ADO.NET, consulte [acesso aos dados de rastreamento](http://msdn.microsoft.com/library/hh880086.aspx).</span><span class="sxs-lookup"><span data-stu-id="e7ee7-112">For more information about setting and configuring managed tracing in ADO.NET, see [Tracing Data Access](http://msdn.microsoft.com/library/hh880086.aspx).</span></span>  
  
## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a><span data-ttu-id="e7ee7-113">Acessar informações de diagnóstico no Log de eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="e7ee7-113">Accessing Diagnostic Information in the Extended Events Log</span></span>  
 <span data-ttu-id="e7ee7-114">No [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provedor de dados para [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], rastreamento de acesso a dados ([rastreamento de acesso a dados](http://msdn.microsoft.com/library/hh880086.aspx)) foi atualizado para facilitar para correlacionar eventos do cliente com informações de diagnóstico, tais como falhas de conexão, de anéis de conectividade de buffer e aplicativo desempenho informações do servidor no log de eventos estendidos.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-114">In the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], data access tracing ([Data Access Tracing](http://msdn.microsoft.com/library/hh880086.aspx)) has been updated to make it easier to easier to correlate client events with diagnostic information, such as connection failures, from the server's connectivity ring buffer and application performance information in the extended events log.</span></span> <span data-ttu-id="e7ee7-115">Para obter informações sobre como ler o log de eventos estendidos, consulte [exibir dados de sessão de evento](http://msdn.microsoft.com/library/hh710068\(SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="e7ee7-115">For information about reading the extended events log, see [View Event Session Data](http://msdn.microsoft.com/library/hh710068\(SQL.110\).aspx).</span></span>  
  
 <span data-ttu-id="e7ee7-116">Para operações de conexão ADO.NET enviará um cliente ID de conexão.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-116">For connection operations, ADO.NET will send a client connection ID.</span></span> <span data-ttu-id="e7ee7-117">Se a conexão falhar, você pode acessar o buffer de anéis de conectividade ([solução de problemas de conectividade no SQL Server 2008 com o Buffer de anéis de conectividade](http://go.microsoft.com/fwlink/?LinkId=207752)) e localize o `ClientConnectionID` campo e obter informações de diagnóstico o Falha na conexão.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-117">If the connection fails, you can access the connectivity ring buffer ([Connectivity troubleshooting in SQL Server 2008 with the Connectivity Ring Buffer](http://go.microsoft.com/fwlink/?LinkId=207752)) and find the `ClientConnectionID` field and get diagnostic information about the connection failure.</span></span> <span data-ttu-id="e7ee7-118">As IDs de conexão de cliente são registradas no buffer de anéis se ocorrer um erro.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-118">Client connection IDs are logged in the ring buffer only if an error occurs.</span></span> <span data-ttu-id="e7ee7-119">(Se uma conexão falhar antes de enviar o pacote anterior ao logon, uma ID de conexão do cliente não será gerada.) A ID de conexão do cliente é um GUID de 16 bytes.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-119">(If a connection fails before sending the prelogin packet, a client connection ID will not be generated.) The client connection ID is a 16-byte GUID.</span></span> <span data-ttu-id="e7ee7-120">Você também pode encontrar a conexão de cliente ID na saída de destino de eventos estendidos, se o `client_connection_id` ação for adicionada aos eventos em uma sessão de eventos estendidos.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-120">You can also find the client connection ID in the extended events target output, if the `client_connection_id` action is added to events in an extended events session.</span></span> <span data-ttu-id="e7ee7-121">Você pode habilitar o rastreamento de acesso de dados e execute novamente o comando de conexão e observar o `ClientConnectionID` campo no rastreamento de acesso a dados, se você precisar de mais assistência de diagnóstico de driver do cliente.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-121">You can enable data access tracing and rerun the connection command and observe the `ClientConnectionID` field in the data access trace, if you need further client driver diagnostic assistance.</span></span>  
  
 <span data-ttu-id="e7ee7-122">Você pode obter o cliente ID de conexão programaticamente, usando o `SqlConnection.ClientConnectionID` propriedade.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-122">You can get the client connection ID programmatically by using the `SqlConnection.ClientConnectionID` property.</span></span>  
  
 <span data-ttu-id="e7ee7-123">O `ClientConnectionID` está disponível para um <xref:System.Data.SqlClient.SqlConnection> objeto que estabelece com êxito uma conexão.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-123">The `ClientConnectionID` is available for a <xref:System.Data.SqlClient.SqlConnection> object that successfully establishes  a connection.</span></span> <span data-ttu-id="e7ee7-124">Se uma tentativa de conexão falhar, `ClientConnectionID` podem estar disponíveis por meio de `SqlException.ToString`.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-124">If a connection attempt fails, `ClientConnectionID` may be available via `SqlException.ToString`.</span></span>  
  
 <span data-ttu-id="e7ee7-125">ADO.NET também envia uma ID de atividade específica do thread.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-125">ADO.NET also sends a thread-specific activity ID.</span></span> <span data-ttu-id="e7ee7-126">A ID de atividade é capturada em sessões de eventos estendidas se as sessões são iniciadas com a opção de TRACK_CAUSAILITY habilitada.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-126">The activity ID is captured in the extended events sessions if the sessions are started with the TRACK_CAUSAILITY option enabled.</span></span> <span data-ttu-id="e7ee7-127">Para problemas de desempenho com uma conexão ativa, você pode obter a ID de atividade de rastreamento de acesso de dados do cliente (`ActivityID` campo) e, em seguida, localize a ID de atividade na saída de eventos estendidos.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-127">For performance issues with an active connection, you can get the activity ID from the client's data access trace (`ActivityID` field) and then locate the activity ID in the extended events output.</span></span> <span data-ttu-id="e7ee7-128">A ID de atividade nos eventos estendidos é um GUID de 16 bytes (não o mesmo GUID para a ID de conexão do cliente) anexado com um número de sequência de quatro bytes.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-128">The activity ID in extended events is a 16-byte GUID (not the same as the GUID for the client connection ID) appended with a four-byte sequence number.</span></span> <span data-ttu-id="e7ee7-129">O número de sequência representa a ordem de uma solicitação dentro de um thread e indica a ordenação relativa de lote e as instruções RPC para o thread.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-129">The sequence number represents the order of a request within a thread and indicates the relative ordering of batch and RPC statements for the thread.</span></span> <span data-ttu-id="e7ee7-130">O `ActivityID` é enviado atualmente opcionalmente para instruções SQL em lotes e solicitações do RPC quando o rastreamento de acesso de dados está habilitado e o 18º bit na palavra de configuração de rastreamento de acesso a dados está desativado.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-130">The `ActivityID` is currently optionally sent for SQL batch statements and RPC requests when data access tracing is enabled on and the 18th bit in the data access tracing configuration word is turned ON.</span></span>  
  
 <span data-ttu-id="e7ee7-131">A seguir está um exemplo que usa [!INCLUDE[tsql](../../../../includes/tsql-md.md)] para iniciar uma sessão de eventos estendidos que será armazenada em um buffer de anel e registrará a ID de atividade enviada de um cliente em operações em lote e RPC.</span><span class="sxs-lookup"><span data-stu-id="e7ee7-131">The following is a sample that uses [!INCLUDE[tsql](../../../../includes/tsql-md.md)] to start an extended events session that will be stored in a ring buffer and will record the activity ID sent from a client on RPC and batch operations.</span></span>  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7ee7-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e7ee7-132">See Also</span></span>  
 [<span data-ttu-id="e7ee7-133">Rastreamento de rede no .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e7ee7-133">Network Tracing in the .NET Framework</span></span>](../../../../docs/framework/network-programming/network-tracing.md)  
 [<span data-ttu-id="e7ee7-134">Rastreando e instrumentando aplicativos</span><span class="sxs-lookup"><span data-stu-id="e7ee7-134">Tracing and Instrumenting Applications</span></span>](../../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 <span data-ttu-id="e7ee7-135">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="e7ee7-135">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>