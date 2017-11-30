---
title: "Método ICorDebugProcess2::GetVersion"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetVersion
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 nterface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84db785d47f97fe058b8a66070bcf4757fa11517
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="db70a-102">Método ICorDebugProcess2::GetVersion</span><span class="sxs-lookup"><span data-stu-id="db70a-102">ICorDebugProcess2::GetVersion Method</span></span>
<span data-ttu-id="db70a-103">Obtém o número de versão do common language runtime (CLR) que está em execução neste processo.</span><span class="sxs-lookup"><span data-stu-id="db70a-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db70a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="db70a-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] COR_VERSION     *version  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db70a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="db70a-105">Parameters</span></span>  
 `version`  
 <span data-ttu-id="db70a-106">[out] Um ponteiro para uma estrutura COR_VERSION que armazena o número de versão do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="db70a-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db70a-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="db70a-107">Remarks</span></span>  
 <span data-ttu-id="db70a-108">O `GetVersion` método retorna um código de erro se nenhum tempo de execução foi carregado no processo.</span><span class="sxs-lookup"><span data-stu-id="db70a-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db70a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db70a-109">Requirements</span></span>  
 <span data-ttu-id="db70a-110">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db70a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db70a-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db70a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db70a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db70a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db70a-113">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db70a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>