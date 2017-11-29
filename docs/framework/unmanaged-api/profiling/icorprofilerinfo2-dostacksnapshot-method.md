---
title: "Método ICorProfilerInfo2::DoStackSnapshot"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.DoStackSnapshot
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type: apiref
caps.latest.revision: "25"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6a210fc0c1984ee9bc77114ba30c3287ae43b169
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="51974-102">Método ICorProfilerInfo2::DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="51974-102">ICorProfilerInfo2::DoStackSnapshot Method</span></span>
<span data-ttu-id="51974-103">Explica os quadros gerenciados na pilha do thread especificado e envia informações para o criador de perfil por meio de um retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="51974-103">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51974-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="51974-104">Syntax</span></span>  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51974-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="51974-105">Parameters</span></span>  
 `thread`  
 <span data-ttu-id="51974-106">[in] A ID do thread de destino.</span><span class="sxs-lookup"><span data-stu-id="51974-106">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="51974-107">Passando null no `thread` gera um instantâneo do thread atual.</span><span class="sxs-lookup"><span data-stu-id="51974-107">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="51974-108">Se um `ThreadID` de um thread diferente for passado, o common language runtime (CLR) suspende esse thread, executa o instantâneo e continua.</span><span class="sxs-lookup"><span data-stu-id="51974-108">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="51974-109">[in] Um ponteiro para a implementação de [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) método, que é chamado pelo CLR para fornecer o criador de perfil com informações sobre cada quadro gerenciado e cada execução de quadros não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="51974-109">[in] A pointer to the implementation of the [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="51974-110">O `StackSnapshotCallback` método é implementado pelo gerador de criador de perfil.</span><span class="sxs-lookup"><span data-stu-id="51974-110">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="51974-111">[in] Um valor de [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeração, que especifica a quantidade de dados a serem passados para cada quadro por `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="51974-111">[in] A value of the [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="51974-112">[in] Um ponteiro para os dados do cliente, que são passados diretamente para o `StackSnapshotCallback` função de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="51974-112">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="51974-113">[in] Um ponteiro para um Win32 `CONTEXT` estrutura, que é usada para propagar a movimentação da pilha.</span><span class="sxs-lookup"><span data-stu-id="51974-113">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="51974-114">O Win32 `CONTEXT` estrutura contém valores dos registros de CPU e representa o estado da CPU em um momento específico.</span><span class="sxs-lookup"><span data-stu-id="51974-114">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="51974-115">A semente ajuda CLR determinar onde começar a movimentação da pilha, se a parte superior da pilha de código não gerenciado auxiliar; Caso contrário, a semente é ignorada.</span><span class="sxs-lookup"><span data-stu-id="51974-115">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="51974-116">Uma semente deve ser fornecida para um exame assíncrona.</span><span class="sxs-lookup"><span data-stu-id="51974-116">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="51974-117">Se você estiver fazendo uma movimentação assíncrona, nenhuma semente é necessário.</span><span class="sxs-lookup"><span data-stu-id="51974-117">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="51974-118">O `context` parâmetro é válido somente se o sinalizador COR_PRF_SNAPSHOT_CONTEXT foi passado a `infoFlags` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="51974-118">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="51974-119">[in] O tamanho do `CONTEXT` estrutura, que é referenciada pelo `context` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="51974-119">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51974-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="51974-120">Remarks</span></span>  
 <span data-ttu-id="51974-121">Passar nulo para `thread` gera um instantâneo do thread atual.</span><span class="sxs-lookup"><span data-stu-id="51974-121">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="51974-122">Instantâneos podem ser criados de outros threads somente se o thread de destino está suspensa no momento.</span><span class="sxs-lookup"><span data-stu-id="51974-122">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="51974-123">Quando deseja que o criador de perfil percorrer a pilha, ele chama `DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="51974-123">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="51974-124">Antes do CLR retorna daquela chamada, ele chama o `StackSnapshotCallback` várias vezes, uma vez para cada gerenciados quadro (ou execução de quadros não gerenciados) na pilha.</span><span class="sxs-lookup"><span data-stu-id="51974-124">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="51974-125">Quando são encontrados quadros não gerenciados, você mesmo deve orientá-lo.</span><span class="sxs-lookup"><span data-stu-id="51974-125">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="51974-126">A ordem na qual a pilha está sendo movimentada é o inverso de como os quadros foram inseridos na pilha: folha (enviado pelo último) primeiro, principal (primeira enviado) quadro última.</span><span class="sxs-lookup"><span data-stu-id="51974-126">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="51974-127">Para obter mais informações sobre como programar o criador de perfil para movimentar pilhas gerenciadas, consulte [movimentação de pilhas do criador de perfil do .NET Framework 2.0: Noções básicas e além](http://go.microsoft.com/fwlink/?LinkId=73638).</span><span class="sxs-lookup"><span data-stu-id="51974-127">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](http://go.microsoft.com/fwlink/?LinkId=73638).</span></span>  
  
 <span data-ttu-id="51974-128">Um exame da pilha pode ser síncronas ou assíncronas, conforme explicado nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="51974-128">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="51974-129">Movimentação de pilha síncrona</span><span class="sxs-lookup"><span data-stu-id="51974-129">Synchronous Stack Walk</span></span>  
 <span data-ttu-id="51974-130">Um exame da pilha síncronas envolve a movimentação de pilha do thread atual em resposta a um retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="51974-130">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="51974-131">Ele não requer a propagação ou suspender.</span><span class="sxs-lookup"><span data-stu-id="51974-131">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="51974-132">Fazer um síncrono chamar quando, em resposta ao chamar um o criador de perfil CLR [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (ou [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) métodos, chame `DoStackSnapshot` para percorrer a pilha da thread atual.</span><span class="sxs-lookup"><span data-stu-id="51974-132">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (or [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="51974-133">Isso é útil quando você deseja ver a pilha de aparência em uma notificação, como [: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="51974-133">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="51974-134">Você acabou de chamar `DoStackSnapshot` no seu `ICorProfilerCallback` método, passando null no `context` e `thread` parâmetros.</span><span class="sxs-lookup"><span data-stu-id="51974-134">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="51974-135">Movimentação de pilha assíncrona</span><span class="sxs-lookup"><span data-stu-id="51974-135">Asynchronous Stack Walk</span></span>  
 <span data-ttu-id="51974-136">Um exame da pilha assíncrona envolve a movimentação de pilha de um thread diferente ou movimentação de pilha do thread atual, não em resposta a um retorno de chamada, mas por captura o ponteiro de instrução do thread atual.</span><span class="sxs-lookup"><span data-stu-id="51974-136">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="51974-137">Um exame assíncrona requer uma semente, se a parte superior da pilha de código não gerenciado que não faz parte de uma plataforma de invocação (PInvoke) ou chamada de COM, mas o código auxiliar no próprio CLR.</span><span class="sxs-lookup"><span data-stu-id="51974-137">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="51974-138">Por exemplo, o código que faz just-in-time (JIT) compilar ou coleta de lixo é código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="51974-138">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="51974-139">Obter uma semente suspendendo diretamente o thread de destino e percorrer sua pilha por conta própria, até encontrar o primeiro quadro gerenciado.</span><span class="sxs-lookup"><span data-stu-id="51974-139">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="51974-140">Depois que o thread de destino está suspenso, obter o contexto de registro atual do thread de destino.</span><span class="sxs-lookup"><span data-stu-id="51974-140">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="51974-141">Em seguida, determine se o contexto de registro aponta para código não gerenciado chamando [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) — se ela retorna um `FunctionID` é igual a zero, o quadro de código não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="51974-141">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="51974-142">Agora, movimentar a pilha até atingir o primeiro quadro gerenciado e, em seguida, calcular o contexto de semente com base no contexto do registro para o quadro.</span><span class="sxs-lookup"><span data-stu-id="51974-142">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="51974-143">Chamar `DoStackSnapshot` com o contexto de semente para começar a movimentação da pilha assíncrona.</span><span class="sxs-lookup"><span data-stu-id="51974-143">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="51974-144">Se você não fornecer uma semente, `DoStackSnapshot` pode ignorar quadros gerenciados na parte superior da pilha e, consequentemente, você terá um exame da pilha incompleta.</span><span class="sxs-lookup"><span data-stu-id="51974-144">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="51974-145">Se você fornecer uma semente, ela deve apontar para o gerador de imagem nativa ou compilação JIT (Ngen.exe)-gerado código; Caso contrário, `DoStackSnapshot` retorna o código de falha, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span><span class="sxs-lookup"><span data-stu-id="51974-145">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="51974-146">Movimentações de pilha assíncronas facilmente podem causar deadlocks ou violações de acesso, a menos que você siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="51974-146">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
-   <span data-ttu-id="51974-147">Quando você suspende diretamente threads, lembre-se de que apenas um thread que nunca executou código gerenciado pode suspender outro thread.</span><span class="sxs-lookup"><span data-stu-id="51974-147">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
-   <span data-ttu-id="51974-148">Sempre bloquear seu [: ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) retorno de chamada até que essa movimentação de pilha seja concluída.</span><span class="sxs-lookup"><span data-stu-id="51974-148">Always block in your [ICorProfilerCallback::ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
-   <span data-ttu-id="51974-149">Não manter um bloqueio enquanto o criador de perfil chama uma função CLR que podem disparar uma coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="51974-149">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="51974-150">Ou seja, não manter um bloqueio se o thread que pode fazer uma chamada que dispara uma coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="51974-150">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="51974-151">Também há um risco de deadlock se você chamar `DoStackSnapshot` por um thread que criou o criador de perfil para que você pode percorrer a pilha de um segmento separado de destino.</span><span class="sxs-lookup"><span data-stu-id="51974-151">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="51974-152">Na primeira vez que o thread que você criou insere certos `ICorProfilerInfo*` métodos (incluindo `DoStackSnapshot`), o CLR irá realizar inicialização por thread, CLR específicas nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="51974-152">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="51974-153">Se o criador de perfil suspendeu o thread de destino cuja pilha que você está tentando percorrer e se esse thread de destino aconteceu possua um bloqueio necessárias para executar essa inicialização por thread, ocorrerá um deadlock.</span><span class="sxs-lookup"><span data-stu-id="51974-153">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="51974-154">Para evitar esse deadlock, fazer uma chamada inicial em `DoStackSnapshot` partir do thread criado pelo criador de perfil para percorrer um separado thread de destino, mas não suspender o thread de destino pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="51974-154">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="51974-155">Essa chamada inicial garante que a inicialização por thread poderá ser concluído sem bloqueio.</span><span class="sxs-lookup"><span data-stu-id="51974-155">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="51974-156">Se `DoStackSnapshot` for bem-sucedida e relatórios de pelo menos um quadro, após esse ponto, é seguro para esse thread criado pelo criador de perfil suspender qualquer thread de destino e a chamada `DoStackSnapshot` para percorrer a pilha do thread de destino.</span><span class="sxs-lookup"><span data-stu-id="51974-156">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51974-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51974-157">Requirements</span></span>  
 <span data-ttu-id="51974-158">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51974-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51974-159">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51974-159">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51974-160">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51974-160">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51974-161">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51974-161">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51974-162">Consulte também</span><span class="sxs-lookup"><span data-stu-id="51974-162">See Also</span></span>  
 [<span data-ttu-id="51974-163">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="51974-163">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="51974-164">Interface ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="51974-164">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)