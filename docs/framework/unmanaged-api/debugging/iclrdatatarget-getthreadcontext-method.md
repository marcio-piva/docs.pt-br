---
title: "Método ICLRDataTarget::GetThreadContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480b65b279dbc0359b078f3f1d543f63a0bfd0f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="55b65-102">Método ICLRDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="55b65-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="55b65-103">Obtém o contexto de execução atual de determinado thread no processo de destino.</span><span class="sxs-lookup"><span data-stu-id="55b65-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="55b65-104">Este método é chamado pelos serviços de acesso de dados de tempo de execução linguagem comuns.</span><span class="sxs-lookup"><span data-stu-id="55b65-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55b65-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="55b65-105">Syntax</span></span>  
  
```  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55b65-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="55b65-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="55b65-107">[in] O identificador de sistema operacional de um thread no processo de destino.</span><span class="sxs-lookup"><span data-stu-id="55b65-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="55b65-108">[in] Sinalizadores que especificam quais partes do contexto para retornar.</span><span class="sxs-lookup"><span data-stu-id="55b65-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="55b65-109">A implementação irá retornar pelo menos essas partes do contexto.</span><span class="sxs-lookup"><span data-stu-id="55b65-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="55b65-110">[in] O tamanho do contexto.</span><span class="sxs-lookup"><span data-stu-id="55b65-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="55b65-111">[out] Ponteiro para um buffer no qual colocar o contexto.</span><span class="sxs-lookup"><span data-stu-id="55b65-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="55b65-112">Os dados de `context` buffer deve estar no formato de Win32 `CONTEXT` estrutura.</span><span class="sxs-lookup"><span data-stu-id="55b65-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="55b65-113">O contexto Especifica dados de registro específicos de processador, portanto a definição de Win32 `CONTEXT` estrutura depende da arquitetura do processador.</span><span class="sxs-lookup"><span data-stu-id="55b65-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="55b65-114">Consulte o arquivo de cabeçalho Winnt. H para a definição do Win32 `CONTEXT` estrutura.</span><span class="sxs-lookup"><span data-stu-id="55b65-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55b65-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="55b65-115">Remarks</span></span>  
 <span data-ttu-id="55b65-116">Este método é implementado pelo autor do aplicativo de depuração.</span><span class="sxs-lookup"><span data-stu-id="55b65-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55b65-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55b65-117">Requirements</span></span>  
 <span data-ttu-id="55b65-118">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55b65-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55b65-119">**Cabeçalho:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="55b65-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="55b65-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55b65-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55b65-121">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55b65-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55b65-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="55b65-122">See Also</span></span>  
 [<span data-ttu-id="55b65-123">Interface ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="55b65-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)