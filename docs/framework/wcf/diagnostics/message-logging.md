---
title: Registro em log de mensagens
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bce0682-75ef-4d65-a659-b328fba4a8b5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a771cbc22febf966fec2cf608a9b59204fc6e51a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="message-logging"></a><span data-ttu-id="d5a4b-102">Registro em log de mensagens</span><span class="sxs-lookup"><span data-stu-id="d5a4b-102">Message Logging</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="d5a4b-103">fornece a capacidade de registrar em log mensagens de entrada e saídas para consumo offline.</span><span class="sxs-lookup"><span data-stu-id="d5a4b-103"> provides the capability to log incoming and outgoing messages for offline consumption.</span></span> <span data-ttu-id="d5a4b-104">Log de mensagens permite que você veja quais a mensagem e é de corpo de mensagem semelhante.</span><span class="sxs-lookup"><span data-stu-id="d5a4b-104">Message logging enables you to see what the message and message body looks like.</span></span> <span data-ttu-id="d5a4b-105">Esse tipo de log é particularmente útil para que você saiba o que foram passados argumentos e como o ponto de extremidade de recebimento viu os argumentos expressos como XML.</span><span class="sxs-lookup"><span data-stu-id="d5a4b-105">This type of logging is particularly helpful in letting you know what arguments were passed in and how the receiving endpoint saw the arguments expressed as XML.</span></span> <span data-ttu-id="d5a4b-106">Além disso, o registro a mensagem conforme ela foi recebida permite diagnosticar mensagens malformadas, bem como para ver como a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="d5a4b-106">In addition, logging the message as it was received allows you to diagnose malformed messages as well as to see how the message arrived.</span></span> <span data-ttu-id="d5a4b-107">Você também pode examinar a segurança tokens utilizados, partes criptografado e assinado e partes permanecem intactas.</span><span class="sxs-lookup"><span data-stu-id="d5a4b-107">You can also examine the security tokens used, parts encrypted and signed, and parts left intact.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5a4b-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d5a4b-108">In This Section</span></span>  
 [<span data-ttu-id="d5a4b-109">Visão geral do fluxo de mensagem</span><span class="sxs-lookup"><span data-stu-id="d5a4b-109">Message Flow Overview</span></span>](../../../../docs/framework/wcf/diagnostics/message-flow-overview.md)  
  
 <span data-ttu-id="d5a4b-110">Este tópico descreve como as mensagens de log de eventos correspondem aos eventos do cliente e de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5a4b-110">This topic describes how event log messages correspond to client and service events.</span></span>  
  
 [<span data-ttu-id="d5a4b-111">Configurando o log de mensagem</span><span class="sxs-lookup"><span data-stu-id="d5a4b-111">Configuring Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
  
 <span data-ttu-id="d5a4b-112">Este tópico descreve como você pode configurar o log de mensagens para diferentes cenários.</span><span class="sxs-lookup"><span data-stu-id="d5a4b-112">This topic describes how you can configure message logging for different scenarios.</span></span>  
  
 [<span data-ttu-id="d5a4b-113">Visualizando Logs de mensagem</span><span class="sxs-lookup"><span data-stu-id="d5a4b-113">Viewing Message Logs</span></span>](../../../../docs/framework/wcf/diagnostics/viewing-message-logs.md)  
  
 <span data-ttu-id="d5a4b-114">Este tópico descreve como você pode exibir os logs de mensagem.</span><span class="sxs-lookup"><span data-stu-id="d5a4b-114">This topic describes how you can view message logs.</span></span>  
  
 [<span data-ttu-id="d5a4b-115">Questões de segurança para o log de mensagem</span><span class="sxs-lookup"><span data-stu-id="d5a4b-115">Security Concerns for Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/security-concerns-for-message-logging.md)  
  
 <span data-ttu-id="d5a4b-116">Este tópico descreve como você pode proteger dados confidenciais de serem expostas em logs de mensagem, bem como os eventos gerados pelo log de mensagens.</span><span class="sxs-lookup"><span data-stu-id="d5a4b-116">This topic describes how you can protect sensitive data from being exposed in message logs, as well as events generated by message logging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a4b-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d5a4b-117">See Also</span></span>  
 <span data-ttu-id="d5a4b-118">[Administration and Diagnostics](../../../../docs/framework/wcf/diagnostics/index.md) (Administração e diagnósticos)</span><span class="sxs-lookup"><span data-stu-id="d5a4b-118">[Administration and Diagnostics](../../../../docs/framework/wcf/diagnostics/index.md)</span></span>