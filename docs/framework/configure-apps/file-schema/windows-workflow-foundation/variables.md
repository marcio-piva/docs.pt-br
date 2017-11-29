---
title: "&lt;variáveis&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 51476e9d3fc0e57ec261f63683dc139491541bce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltvariablesgt"></a><span data-ttu-id="05544-102">&lt;variáveis&gt;</span><span class="sxs-lookup"><span data-stu-id="05544-102">&lt;variables&gt;</span></span>
<span data-ttu-id="05544-103">Representa uma coleção de variáveis associadas a essa consulta de atividade.</span><span class="sxs-lookup"><span data-stu-id="05544-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="05544-104">Para obter mais informações sobre consultas de perfil de controle, consulte [perfis controle](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="05544-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="05544-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="05544-105">\<system.serviceModel></span></span>  
<span data-ttu-id="05544-106">\<controle ></span><span class="sxs-lookup"><span data-stu-id="05544-106">\<tracking></span></span>  
<span data-ttu-id="05544-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="05544-107">\<trackingProfile></span></span>  
<span data-ttu-id="05544-108">\<fluxo de trabalho ></span><span class="sxs-lookup"><span data-stu-id="05544-108">\<workflow></span></span>  
<span data-ttu-id="05544-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="05544-109">\<activityStateQueries></span></span>  
<span data-ttu-id="05544-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="05544-110">\<activityStateQuery></span></span>  
<span data-ttu-id="05544-111">\<variáveis ></span><span class="sxs-lookup"><span data-stu-id="05544-111">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05544-112">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="05544-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05544-113">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="05544-113">Attributes and Elements</span></span>  
 <span data-ttu-id="05544-114">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="05544-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05544-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="05544-115">Attributes</span></span>  
 <span data-ttu-id="05544-116">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="05544-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05544-117">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="05544-117">Child Elements</span></span>  
  
|<span data-ttu-id="05544-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="05544-118">Element</span></span>|<span data-ttu-id="05544-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="05544-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05544-120">\<variável ></span><span class="sxs-lookup"><span data-stu-id="05544-120">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="05544-121">Uma variável associada a uma consulta de estado de atividade.</span><span class="sxs-lookup"><span data-stu-id="05544-121">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05544-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="05544-122">Parent Elements</span></span>  
  
|<span data-ttu-id="05544-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="05544-123">Element</span></span>|<span data-ttu-id="05544-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="05544-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05544-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="05544-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="05544-126">Representa um elemento de configuração que é usado para controlar solicitações cancelar uma atividade filho pela atividade pai.</span><span class="sxs-lookup"><span data-stu-id="05544-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="05544-127">A consulta é necessária para um participante de rastreamento inscrever-se para Cancelar solicitação objetos de registro.</span><span class="sxs-lookup"><span data-stu-id="05544-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05544-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="05544-128">Remarks</span></span>  
 <span data-ttu-id="05544-129">Um recurso exclusivo de um ActivityStateQuery é a capacidade de extrair dados para controlar a execução de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="05544-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="05544-130">Isso fornece contexto adicional ao acessar o rastreamento registra pós execução.</span><span class="sxs-lookup"><span data-stu-id="05544-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="05544-131">Você pode usar o [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementos para extrair qualquer variável ou argumento de qualquer atividade em um fluxo de trabalho. O exemplo a seguir mostra uma consulta de estado de atividade que extrai os argumentos e variáveis quando a atividade `Closed` registro de rastreamento é emitido.</span><span class="sxs-lookup"><span data-stu-id="05544-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="05544-132">Variáveis e argumentos pode ser extraídos apenas com um ActivityStateRecord e, portanto, se inscreveu em um controle de perfil usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="05544-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="05544-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="05544-133">See Also</span></span>  
 <span data-ttu-id="05544-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="05544-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="05544-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="05544-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="05544-136">Acompanhamento e rastreamento de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="05544-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="05544-137">Acompanhando perfis</span><span class="sxs-lookup"><span data-stu-id="05544-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)