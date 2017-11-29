---
title: "Método ICorDebugManagedCallback2::FunctionRemapComplete"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.FunctionRemapComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cee712c2ff8acf56049ca9e288fad21e4608da3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="cb8ec-102">Método ICorDebugManagedCallback2::FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="cb8ec-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="cb8ec-103">Notifica o depurador que a execução de código alternou para uma nova versão de uma função editada.</span><span class="sxs-lookup"><span data-stu-id="cb8ec-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb8ec-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cb8ec-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb8ec-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cb8ec-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="cb8ec-106">[in] Um ponteiro para um objeto ICorDebugAppDomain que representa o domínio de aplicativo que contém a função editada.</span><span class="sxs-lookup"><span data-stu-id="cb8ec-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="cb8ec-107">[in] Um ponteiro para um objeto ICorDebugThread que representa o thread em que o ponto de interrupção remapear foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="cb8ec-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="cb8ec-108">[in] Um ponteiro para um objeto ICorDebugFunction que representa a versão da função atualmente em execução no thread.</span><span class="sxs-lookup"><span data-stu-id="cb8ec-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb8ec-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="cb8ec-109">Remarks</span></span>  
 <span data-ttu-id="cb8ec-110">Esse retorno de chamada de depurador uma oportunidade para recriar a qualquer steppers que existia anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cb8ec-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb8ec-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb8ec-111">Requirements</span></span>  
 <span data-ttu-id="cb8ec-112">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb8ec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb8ec-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb8ec-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb8ec-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb8ec-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb8ec-115">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb8ec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb8ec-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cb8ec-116">See Also</span></span>  
 [<span data-ttu-id="cb8ec-117">Interface ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="cb8ec-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="cb8ec-118">Interface ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="cb8ec-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)