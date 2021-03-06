---
title: '&lt;adicionar&gt; &lt;serviços&gt;'
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: dc68357332ebe06affd18f1539a66587b6ed1b91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549987"
---
# <a name="ltaddgt-of-ltservicesgt"></a>&lt;adicionar&gt; &lt;serviços&gt;
Especifica configurações para uma instância de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar os serviços do Windows Communication Foundation (WCF) baseados em fluxo de trabalho. Esse elemento é do tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  
  
 \<system.ServiceModel>  
\<comportamentos >  
\<serviceBehaviors>  
\<behavior>  
\<services>  
\<add>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|tipo|Uma cadeia de caracteres que especifica o nome de tipo qualificado pelo assembly do serviço a ser inicializado. O serviço especificado deve seguir determinadas regras sobre as assinaturas de seus construtores. Consulte <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obter mais informações.|  
  
### <a name="child-elements"></a>Elementos filho  
 nenhuma.  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|Uma coleção de serviços que serão adicionados para o <xref:System.Workflow.Runtime.WorkflowRuntime> mecanismo. Os elementos são do tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  Os serviços especificados na coleção serão inicializados pelo mecanismo de tempo de execução de fluxo de trabalho e adicionados a seus serviços quando apropriado <xref:System.Workflow.Runtime.WorkflowRuntime> construtor é chamado. Portanto, os serviços especificados na coleção devem seguir determinadas regras sobre as assinaturas de seus construtores. Consulte <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obter mais informações.|  
  
## <a name="remarks"></a>Comentários  
 O serviço especificado nesse elemento será inicializado pelo mecanismo de tempo de execução de fluxo de trabalho e adicionado a seus serviços quando apropriado <xref:System.Workflow.Runtime.WorkflowRuntime> construtor é chamado. Portanto, o serviço especificado deve seguir determinadas regras sobre as assinaturas de seus construtores. Consulte <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obter mais informações.  
  
## <a name="example"></a>Exemplo  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>Consulte também
- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- [Arquivos de configuração do fluxo de trabalho](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
