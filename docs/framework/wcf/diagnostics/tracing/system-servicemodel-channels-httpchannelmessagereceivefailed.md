---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: 22730ef8a0c0b4706f9e267fef251014a70a58fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720165"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a>System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
Falha ao receber uma mensagem por um canal HTTP.  
  
## <a name="description"></a>Descrição  
 Este rastreamento pode ser emitido como um aviso ou erro. Em ambos os casos, o rastreamento será emitido quando um ouvinte compatível não for encontrado para uma solicitação HTTP de entrada e a solicitação HTTP é descartada. Isso pode acontecer porque o verbo HTTP da solicitação não foi reconhecido por qualquer ouvinte HTTP, ou porque nenhum ouvinte estava escutando no endereço a solicitação foi direcionada para. O rastreamento é emitido como um aviso no caso de auto-hospedado e como um erro quando o serviço está hospedado no IIS.  
  
## <a name="see-also"></a>Consulte também
- [Rastreamento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Usando o rastreamento para solucionar problemas do seu aplicativo](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnósticos](../../../../../docs/framework/wcf/diagnostics/index.md)
