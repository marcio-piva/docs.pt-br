---
title: '&lt;adicionar&gt; &lt;issuerChannelBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: e0f49f71a3f9649492b3ad7ccf263114957ee4e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729925"
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a>&lt;adicionar&gt; &lt;issuerChannelBehaviors&gt;
Adiciona um comportamento de ponto de extremidade a ser usado ao se comunicar com um STS.  
  
> [!NOTE]
>  Se qualquer comportamento de ponto de extremidade contém um [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, uma exceção será gerada.  
  
 \<system.ServiceModel>  
\<comportamentos >  
seção endpointBehaviors  
\<behavior>  
\<clientCredentials>  
\<issuedToken>  
\<issuerChannelBehaviors > elemento  
\<add>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<add issuerAddress="string"
     behaviorConfiguraton="string" />
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|issuerAddress|O URI do emissor do token de segurança para se comunicar com.|  
|behaviorConfiguration|O nome de um comportamento de ponto de extremidade definido no mesmo arquivo de configuração.|  
  
### <a name="child-elements"></a>Elementos filho  
 nenhuma.  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<issuerChannelBehaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Contém uma coleção de comportamentos de ponto de extremidade do cliente Windows Communication Foundation (WCF) a ser usado ao se comunicar com os serviços de Token de serviço especificados.|  
  
## <a name="remarks"></a>Comentários  
 `issuerAddress` contém o URI do serviço de Token de segurança que o cliente quer se comunicar com. `behaviorConfiguration` aponta para um comportamento de ponto de extremidade que o aplicativo usa nos canais criados pelo Windows Communication Foundation (WCF) para obter os tokens emitidos de serviços de Token de segurança.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [Autenticação e identidade de serviço](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Comportamentos de segurança](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Federação e tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Protegendo serviços e clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Protegendo clientes](../../../../../docs/framework/wcf/securing-clients.md)
- [Como: Criar um cliente federado](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Como: Configurar um emissor Local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Federação e tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
