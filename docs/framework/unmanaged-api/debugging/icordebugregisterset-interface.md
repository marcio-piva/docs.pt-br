---
title: Interface ICorDebugRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8db70faf418bc89a4543845890f65e4859d507e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592595"
---
# <a name="icordebugregisterset-interface"></a>Interface ICorDebugRegisterSet
Representa o conjunto de registros disponíveis no computador que está executando código.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|Obtém o valor de cada registro (no computador que está executando código) que é especificado pela máscara de bits.|  
|[Método GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|Obtém um pouco máscara que indica que registra nisso `ICorDebugRegisterSet` estão disponíveis no momento.|  
|[Método GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|Obtém o contexto do thread atual.|  
|[Método SetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|Não implementado para o .NET Framework versão 2.0.|  
|[Método SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|Não implementado para o .NET Framework 2.0.|  
  
## <a name="remarks"></a>Comentários  
 O `ICorDebugRegisterSet` interface dá suporte a registros de 32 bits apenas. Use o [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface em plataformas como IA-64 que exigem registros adicionais.  
  
> [!NOTE]
>  Essa interface não dá suporte a ser chamada remotamente, entre computadores ou entre processos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também
- [Depurando interfaces](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Interface ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
