---
title: "Gerenciamento suspenso da instância"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 02c3d6b3a522dd4337dcdf22f884f63cdddd4aa4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="suspended-instance-management"></a><span data-ttu-id="05f5d-102">Gerenciamento suspenso da instância</span><span class="sxs-lookup"><span data-stu-id="05f5d-102">Suspended Instance Management</span></span>
<span data-ttu-id="05f5d-103">Este exemplo demonstra como gerenciar as instâncias de fluxo de trabalho que foram suspensas.</span><span class="sxs-lookup"><span data-stu-id="05f5d-103">This sample demonstrates how to manage workflow instances that have been suspended.</span></span>  <span data-ttu-id="05f5d-104">A ação padrão para <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> é `AbandonAndSuspend`.</span><span class="sxs-lookup"><span data-stu-id="05f5d-104">The default action for <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is `AbandonAndSuspend`.</span></span> <span data-ttu-id="05f5d-105">Isso significa que por padrão, as exceções não tratadas lançadas de uma instância de fluxo de trabalho hospedada em <xref:System.ServiceModel.WorkflowServiceHost> causarão a instância a ser descartado de memória (abandonada) e de bens/versão armazenado de instância a ser marcada como suspendida.</span><span class="sxs-lookup"><span data-stu-id="05f5d-105">This means that by default, unhandled exceptions thrown from a workflow instance hosted in the <xref:System.ServiceModel.WorkflowServiceHost> will cause the instance to be disposed from memory (abandoned) and the durable/persisted version of the instance to be marked as suspended.</span></span> <span data-ttu-id="05f5d-106">Uma instância suspendida de fluxo de trabalho não poderá executar até que estado unsuspended.</span><span class="sxs-lookup"><span data-stu-id="05f5d-106">A suspended workflow instance will not be able to run until it has been unsuspended.</span></span>  
  
 <span data-ttu-id="05f5d-107">O exemplo mostra como um utilitário de linha de comando pode ser implementado para consultar instâncias suspensas, e como conceder ao usuário a opção continuar ou finalizar a instância.</span><span class="sxs-lookup"><span data-stu-id="05f5d-107">The sample shows how a command-line utility can be implemented to query for suspended instances, and how to give the user the option to resume or terminate the instance.</span></span> <span data-ttu-id="05f5d-108">Nesse exemplo, um serviço de fluxo de trabalho intencionalmente lança uma exceção, fazendo com que fique suspenso.</span><span class="sxs-lookup"><span data-stu-id="05f5d-108">In this sample, a workflow service intentionally throws an exception, causing it to become suspended.</span></span> <span data-ttu-id="05f5d-109">O utilitário de linha de comando pode então ser usado para consultar a instância e posteriormente para continuar ou finalizar a instância.</span><span class="sxs-lookup"><span data-stu-id="05f5d-109">The command-line utility can then be used to query for the instance and subsequently resume or terminate the instance.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="05f5d-110">Demonstra</span><span class="sxs-lookup"><span data-stu-id="05f5d-110">Demonstrates</span></span>  
 <span data-ttu-id="05f5d-111"><xref:System.ServiceModel.WorkflowServiceHost> com <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> e <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> em [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05f5d-111"><xref:System.ServiceModel.WorkflowServiceHost> with <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> and <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="05f5d-112">Discussão</span><span class="sxs-lookup"><span data-stu-id="05f5d-112">Discussion</span></span>  
 <span data-ttu-id="05f5d-113">O utilitário de linha de comando implementado nesse exemplo é específico da implementação da instância do SQL que envia em [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05f5d-113">The command-line utility implemented in this sample is specific to the SQL instance store implementation that ships in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="05f5d-114">Se você tiver uma implementação personalizada de armazenamento de instância, então você pode adaptar este utilitário substituindo as implementações de `WorkflowInstanceCommand` no exemplo com as implementações que são específicas para seu armazenamento de instância.</span><span class="sxs-lookup"><span data-stu-id="05f5d-114">If you have a custom implementation of the instance store, then you can adapt this utility by replacing the `WorkflowInstanceCommand` implementations in the sample with implementations that are specific to your instance store.</span></span>  
  
 <span data-ttu-id="05f5d-115">Os comandos SQL fornecidos de blocos de implementação no armazenamento da instância do SQL diretamente listar suspenderam instâncias, e depende em <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> adicionado a <xref:System.ServiceModel.WorkflowServiceHost> para continuar ou finalizar as instâncias.</span><span class="sxs-lookup"><span data-stu-id="05f5d-115">The provided implementation runs SQL commands against the SQL instance store directly to list suspended instances, and it relies on a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> added to the <xref:System.ServiceModel.WorkflowServiceHost> in order to resume or terminate the instances.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="05f5d-116">Para configurar, compilar, e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="05f5d-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="05f5d-117">Esse exemplo requer que os seguintes componentes do Windows estão ativados:</span><span class="sxs-lookup"><span data-stu-id="05f5d-117">This sample requires that the following Windows components are enabled:</span></span>  
  
    1.  <span data-ttu-id="05f5d-118">Servidor das filas de mensagens da Microsoft (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="05f5d-118">Microsoft Message Queues (MSMQ) Server</span></span>  
  
    2.  <span data-ttu-id="05f5d-119">SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="05f5d-119">SQL Server Express</span></span>  
  
2.  <span data-ttu-id="05f5d-120">Configurar o base de dados SQL Server.</span><span class="sxs-lookup"><span data-stu-id="05f5d-120">Set up the SQL Server database.</span></span>  
  
    1.  <span data-ttu-id="05f5d-121">De um [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] prompt de comando, execute "setup.cmd" do diretório de exemplo SuspendedInstanceManagement, que faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="05f5d-121">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, run "setup.cmd" from the SuspendedInstanceManagement sample directory, which does the following:</span></span>  
  
        1.  <span data-ttu-id="05f5d-122">Cria um base de dados de persistência usando o SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="05f5d-122">Creates a persistence database using SQL Server Express.</span></span> <span data-ttu-id="05f5d-123">Se o base de dados de persistência já existir, então é solto e re-criada</span><span class="sxs-lookup"><span data-stu-id="05f5d-123">If the persistence database already exists, then it is dropped and re-created</span></span>  
  
        2.  <span data-ttu-id="05f5d-124">Configura de base de dados para persistência.</span><span class="sxs-lookup"><span data-stu-id="05f5d-124">Sets up the database for persistence.</span></span>  
  
        3.  <span data-ttu-id="05f5d-125">Adiciona o IIS APPPOOL \ AUTORIDADE de DefaultAppPool e NT \ serviço de rede para a função de InstanceStoreUsers que foi definida para configurar o base de dados para persistência.</span><span class="sxs-lookup"><span data-stu-id="05f5d-125">Adds IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service to the InstanceStoreUsers role that was defined when setting up the database for persistence.</span></span>  
  
3.  <span data-ttu-id="05f5d-126">Configurar a fila de serviço.</span><span class="sxs-lookup"><span data-stu-id="05f5d-126">Set up the service queue.</span></span>  
  
    1.  <span data-ttu-id="05f5d-127">Em [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], com o botão direito do **SampleWorkflowApp** do projeto e clique em **definir como projeto de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="05f5d-127">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], right-click the **SampleWorkflowApp** project and click **Set as Startup Project**.</span></span>  
  
    2.  <span data-ttu-id="05f5d-128">Compilar e executar o SampleWorkflowApp pressionando **F5**.</span><span class="sxs-lookup"><span data-stu-id="05f5d-128">Compile and run the SampleWorkflowApp by pressing **F5**.</span></span> <span data-ttu-id="05f5d-129">Isso criará a fila necessário.</span><span class="sxs-lookup"><span data-stu-id="05f5d-129">This will create the required queue.</span></span>  
  
    3.  <span data-ttu-id="05f5d-130">Pressione **Enter** para interromper o SampleWorkflowApp.</span><span class="sxs-lookup"><span data-stu-id="05f5d-130">Press **Enter** to stop the SampleWorkflowApp.</span></span>  
  
    4.  <span data-ttu-id="05f5d-131">Abra o console de Gerenciamento do Computador executando Compmgmt.msc de um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="05f5d-131">Open the Computer Management console by running Compmgmt.msc from a command prompt.</span></span>  
  
    5.  <span data-ttu-id="05f5d-132">Expanda **serviços e aplicativos**, **enfileiramento**, **filas particulares**.</span><span class="sxs-lookup"><span data-stu-id="05f5d-132">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    6.  <span data-ttu-id="05f5d-133">Clique com botão direito do **ReceiveTx** de fila e selecione **propriedades**.</span><span class="sxs-lookup"><span data-stu-id="05f5d-133">Right click the **ReceiveTx** queue and select **Properties**.</span></span>  
  
    7.  <span data-ttu-id="05f5d-134">Selecione o **segurança** guia e permitir **todos** ter permissões para **receber mensagem**, **inspecionar mensagem**, e  **Enviar mensagem**.</span><span class="sxs-lookup"><span data-stu-id="05f5d-134">Select the **Security** tab and allow **Everyone** to have permissions to **Receive Message**, **Peek Message**, and **Send Message**.</span></span>  
  
4.  <span data-ttu-id="05f5d-135">Agora, executar o exemplo.</span><span class="sxs-lookup"><span data-stu-id="05f5d-135">Now, run the sample.</span></span>  
  
    1.  <span data-ttu-id="05f5d-136">Em [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], execute o projeto SampleWorkflowApp novamente sem depuração pressionando **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="05f5d-136">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], run the SampleWorkflowApp project again without debugging by pressing **Ctrl+F5**.</span></span> <span data-ttu-id="05f5d-137">Dois endereços de ponto de extremidade será impresso na janela do console: um para o ponto final do aplicativo e então outro de <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="05f5d-137">Two endpoint addresses will be printed in the console window: one for the application endpoint and then other from the <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span></span> <span data-ttu-id="05f5d-138">Uma instância de fluxo de trabalho é criada em seguida, e os registros de controle para essa instância aparecerá na janela do console.</span><span class="sxs-lookup"><span data-stu-id="05f5d-138">A workflow instance is then created, and tracking records for that instance will appear in the console window.</span></span> <span data-ttu-id="05f5d-139">A instância de fluxo de trabalho irá acionar uma exceção que causou a instância a ser suspendida e anuladas.</span><span class="sxs-lookup"><span data-stu-id="05f5d-139">The workflow instance will throw an exception causing the instance to be suspended and aborted.</span></span>  
  
    2.  <span data-ttu-id="05f5d-140">O utilitário de linha de comando pode então ser usado para executar uma ação adicional em uma destas instâncias.</span><span class="sxs-lookup"><span data-stu-id="05f5d-140">The command-line utility can then be used to take further action on any of these instances.</span></span> <span data-ttu-id="05f5d-141">A sintaxe para argumentos de linha de comando é como o follows::</span><span class="sxs-lookup"><span data-stu-id="05f5d-141">The syntax for command line arguments is as follows::</span></span>  
  
         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`  
  
         <span data-ttu-id="05f5d-142">Os comandos são suportados: `Query`, `Resume`, e `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="05f5d-142">The supported commands are: `Query`, `Resume`, and `Terminate`.</span></span>  <span data-ttu-id="05f5d-143">Alterne de InstanceId é necessário somente para `Resume` e operações de `Terminate` .</span><span class="sxs-lookup"><span data-stu-id="05f5d-143">The InstanceId switch is only required for `Resume` and `Terminate` operations.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="05f5d-144">A limpeza (opcional)</span><span class="sxs-lookup"><span data-stu-id="05f5d-144">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="05f5d-145">Abra o console de Gerenciamento do Computador executando Compmgmt.msc de um prompt de comando `vs2010` .</span><span class="sxs-lookup"><span data-stu-id="05f5d-145">Open the Computer Management console by running Compmgmt.msc from a `vs2010` command prompt.</span></span>  
  
2.  <span data-ttu-id="05f5d-146">Expanda **serviços e aplicativos**, **enfileiramento**, **filas particulares**.</span><span class="sxs-lookup"><span data-stu-id="05f5d-146">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="05f5d-147">Excluir o **ReceiveTx** fila.</span><span class="sxs-lookup"><span data-stu-id="05f5d-147">Delete the **ReceiveTx** queue.</span></span>  
  
4.  <span data-ttu-id="05f5d-148">Para remover o base de dados de persistência, cleanup.cmd execução.</span><span class="sxs-lookup"><span data-stu-id="05f5d-148">To remove the persistence database, run cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="05f5d-149">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="05f5d-149">The samples may already be installed on your machine.</span></span> <span data-ttu-id="05f5d-150">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="05f5d-150">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="05f5d-151">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="05f5d-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="05f5d-152">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="05f5d-152">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`