---
title: Coclass CorpubPublish
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a0d796b9c507665ff3ba67153df4691f078e5c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543835"
---
# <a name="corpubpublish-coclass"></a>Coclass CorpubPublish
Fornece interfaces para a publicação de informações sobre domínios de aplicativos e processos.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>Interfaces  
  
|Interface|Descrição|  
|---------------|-----------------|  
|[Interface ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|Fornece métodos para a publicação de informações sobre processos e os domínios de aplicativo em um desses processos.|  
|[Interface ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|Representa e fornece informações sobre um domínio de aplicativo em um processo.|  
|[Interface ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|Fornece métodos que percorrem uma coleção de domínios de aplicativo que existem atualmente dentro de um processo.|  
|[Interface ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|Representa um processo que está em execução em um computador.|  
|[Interface ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|Fornece métodos que percorrem uma coleção de processos em execução em um computador.|  
  
## <a name="remarks"></a>Comentários  
 Um cenário típico de publicação envolve um desenvolvedor que deseja depurar código gerenciado que está em execução em um computador em um domínio do aplicativo. O ambiente de hospedagem pode estar executando mais de um domínio de aplicativo dentro de um processo. O desenvolvedor gostaria de usar uma interface gráfica do usuário ou outros meios para listar todos os processos que estão em execução no computador e escolher um processo específico. A listagem deve incluir todos os domínios de aplicativo dentro de processos que estão executando o código gerenciado. O desenvolvedor pode, em seguida, identificar o domínio de aplicativo específico e anexar um depurador ao domínio.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorPub.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também
- [Depuração](../../../../docs/framework/unmanaged-api/debugging/index.md)
