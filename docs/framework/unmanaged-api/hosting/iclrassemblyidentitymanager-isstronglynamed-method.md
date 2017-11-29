---
title: "Método ICLRAssemblyIdentityManager::IsStronglyNamed"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.IsStronglyNamed
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d0cb0bcaf5d19ec088511e64baffff9031911b32
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="e8bb8-102">Método ICLRAssemblyIdentityManager::IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="e8bb8-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="e8bb8-103">Obtém um valor que indica se o assembly especificado tem um nome forte.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8bb8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e8bb8-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8bb8-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e8bb8-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="e8bb8-106">[in] Os dados de identidade de assembly canônico opaco do assembly a ser avaliada.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="e8bb8-107">[out] `true`, se o assembly referenciado pelo `pwzAssemblyIdentity` parâmetro é fortemente nomeado; caso contrário, `false`.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8bb8-108">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="e8bb8-108">Return Value</span></span>  
  
|<span data-ttu-id="e8bb8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e8bb8-109">HRESULT</span></span>|<span data-ttu-id="e8bb8-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8bb8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e8bb8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8bb8-111">S_OK</span></span>|<span data-ttu-id="e8bb8-112">O método é retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="e8bb8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e8bb8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e8bb8-114">O common language runtime (CLR) não foi carregado em um processo ou o CLR está em um estado em que ele não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e8bb8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e8bb8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e8bb8-116">A chamada foi atingido.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-116">The call timed out.</span></span>|  
|<span data-ttu-id="e8bb8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8bb8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e8bb8-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e8bb8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e8bb8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e8bb8-120">Um evento foi cancelado durante um thread bloqueado ou fibra estava aguardando nele.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e8bb8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e8bb8-121">E_FAIL</span></span>|<span data-ttu-id="e8bb8-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e8bb8-123">Se um método retornará E_FAIL, o CLR não será mais utilizável dentro do processo.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e8bb8-124">As chamadas subsequentes para hospedagem métodos retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e8bb8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8bb8-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8bb8-125">Requirements</span></span>  
 <span data-ttu-id="e8bb8-126">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8bb8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8bb8-127">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e8bb8-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8bb8-128">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="e8bb8-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8bb8-129">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8bb8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8bb8-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e8bb8-130">See Also</span></span>  
 [<span data-ttu-id="e8bb8-131">Interface ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="e8bb8-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)