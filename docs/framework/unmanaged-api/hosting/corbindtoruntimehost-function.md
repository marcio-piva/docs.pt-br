---
title: "Função CorBindToRuntimeHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntimeHost
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CorBindToRuntimeHost
helpviewer_keywords: CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type: apiref
caps.latest.revision: "28"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eff6fdf0294e3b1cc9830e58bc8103a64102d5b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="99cc1-102">Função CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="99cc1-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="99cc1-103">Permite que os hosts carregar uma versão especificada do common language runtime (CLR) em um processo.</span><span class="sxs-lookup"><span data-stu-id="99cc1-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="99cc1-104">Essa função foi preterida no [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99cc1-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99cc1-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="99cc1-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,   
    [in] LPCWSTR       pwszBuildFlavor,   
    [in] LPCWSTR       pwszHostConfigFile,   
    [in] VOID*         pReserved,   
    [in] DWORD         startupFlags,   
    [in] REFCLSID      rclsid,   
    [in] REFIID        riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99cc1-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="99cc1-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="99cc1-107">[in] Uma cadeia de caracteres que descreve a versão do CLR que você deseja carregar.</span><span class="sxs-lookup"><span data-stu-id="99cc1-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="99cc1-108">Um número de versão do .NET Framework consiste em quatro partes separadas por pontos: *Revision*.</span><span class="sxs-lookup"><span data-stu-id="99cc1-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="99cc1-109">A cadeia de caracteres passada como `pwszVersion` deve começar com o caractere "v" seguido as primeiras três partes do número de versão (por exemplo, "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="99cc1-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="99cc1-110">Algumas versões do CLR são instalados com uma declaração de política que especifica a compatibilidade com versões anteriores do CLR.</span><span class="sxs-lookup"><span data-stu-id="99cc1-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="99cc1-111">Por padrão, a correção de inicialização avalia `pwszVersion` em declarações de política e carrega a versão mais recente do tempo de execução que é compatível com a versão que está sendo solicitada.</span><span class="sxs-lookup"><span data-stu-id="99cc1-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="99cc1-112">Um host pode forçar a correção para ignorar a avaliação de política e carregar a versão exata especificada no `pwszVersion` passando um valor de STARTUP_LOADER_SAFEMODE para o `startupFlags` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="99cc1-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="99cc1-113">Se `pwszVersion` é `null,` o método não carregar qualquer versão do CLR.</span><span class="sxs-lookup"><span data-stu-id="99cc1-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="99cc1-114">Em vez disso, ele retorna CLR_E_SHIM_RUNTIMELOAD, que indica que ele não pôde carregar o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="99cc1-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="99cc1-115">[in] Uma cadeia de caracteres que especifica se a carga do servidor ou a compilação de estação de trabalho do CLR.</span><span class="sxs-lookup"><span data-stu-id="99cc1-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="99cc1-116">Os valores válidos são `svr` e `wks`.</span><span class="sxs-lookup"><span data-stu-id="99cc1-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="99cc1-117">A compilação do servidor é otimizada para tirar proveito de vários processadores para coletas de lixo e a compilação de estação de trabalho é otimizada para aplicativos de cliente em execução em um computador com processador único.</span><span class="sxs-lookup"><span data-stu-id="99cc1-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="99cc1-118">Se `pwszBuildFlavor` for definido como null, a compilação de estação de trabalho está carregada.</span><span class="sxs-lookup"><span data-stu-id="99cc1-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="99cc1-119">Quando em execução em um computador com processador único, a compilação de estação de trabalho é sempre carregada, mesmo se `pwszBuildFlavor` é definido como `svr`.</span><span class="sxs-lookup"><span data-stu-id="99cc1-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="99cc1-120">No entanto, se `pwszBuildFlavor` é definido como `svr` e coleta de lixo simultânea for especificada (consulte a descrição do `startupFlags` parâmetro), a compilação do servidor é carregada.</span><span class="sxs-lookup"><span data-stu-id="99cc1-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99cc1-121">Não há suporte para a coleta de lixo simultânea em aplicativos em execução o WOW64 x86 emulador em sistemas de 64 bits que implementam a arquitetura Intel Itanium (anteriormente chamado de IA-64).</span><span class="sxs-lookup"><span data-stu-id="99cc1-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="99cc1-122">Para obter mais informações sobre como usar o WOW64 em sistemas de 64 bits do Windows, consulte [aplicativos em execução de 32 bits](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span><span class="sxs-lookup"><span data-stu-id="99cc1-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="99cc1-123">[in] O nome de um arquivo de configuração de host que especifica a versão do CLR para carregar.</span><span class="sxs-lookup"><span data-stu-id="99cc1-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="99cc1-124">Se o nome do arquivo não incluir um caminho totalmente qualificado, o arquivo deve para estar no mesmo diretório que o executável que está fazendo a chamada.</span><span class="sxs-lookup"><span data-stu-id="99cc1-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="99cc1-125">[in] Reservado para extensibilidade futura.</span><span class="sxs-lookup"><span data-stu-id="99cc1-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="99cc1-126">[in] Um conjunto de sinalizadores que controla o comportamento de coleta de lixo simultânea e código de domínio neutro de `pwszVersion` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="99cc1-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="99cc1-127">O padrão é o único domínio se nenhum sinalizador for definido.</span><span class="sxs-lookup"><span data-stu-id="99cc1-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="99cc1-128">Para obter uma lista de valores com suporte, consulte o [enumeração STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="99cc1-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="99cc1-129">[in] O `CLSID` da coclass que implemente tanto o [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) ou o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="99cc1-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="99cc1-130">Valores com suporte são CLSID_CorRuntimeHost ou CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="99cc1-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="99cc1-131">[in] O `IID` da interface que você está solicitando.</span><span class="sxs-lookup"><span data-stu-id="99cc1-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="99cc1-132">Valores com suporte são IID_ICorRuntimeHost ou IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="99cc1-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="99cc1-133">[out] Um ponteiro de interface para a versão do tempo de execução que foi carregada.</span><span class="sxs-lookup"><span data-stu-id="99cc1-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99cc1-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99cc1-134">Requirements</span></span>  
 <span data-ttu-id="99cc1-135">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99cc1-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99cc1-136">**Cabeçalho:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="99cc1-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="99cc1-137">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99cc1-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99cc1-138">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99cc1-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99cc1-139">Consulte também</span><span class="sxs-lookup"><span data-stu-id="99cc1-139">See Also</span></span>  
 [<span data-ttu-id="99cc1-140">Função CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="99cc1-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="99cc1-141">Função CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="99cc1-141">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="99cc1-142">Função CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="99cc1-142">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="99cc1-143">Função CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="99cc1-143">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="99cc1-144">Interface ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="99cc1-144">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="99cc1-145">Funções de hospedagem CLR reprovadas</span><span class="sxs-lookup"><span data-stu-id="99cc1-145">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)