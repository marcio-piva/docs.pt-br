---
title: '&lt;clientCertificate&gt; de &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: e1334e42149de29c4fc7534863f02ede93c638ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536822"
---
# <a name="ltclientcertificategt-of-ltservicecredentialsgt"></a>&lt;clientCertificate&gt; de &lt;serviceCredentials&gt;
Define um certificado X.509 usado para assinar e criptografar mensagens para um cliente de um serviço em um padrão de comunicação duplex.  
  
 \<system.ServiceModel>  
\<comportamentos >  
\<serviceBehaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceCredentials>  
\<clientCertificate>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai  
  
### <a name="attributes"></a>Atributos  
 nenhuma.  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<authentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|Especifica opções de autenticação para o certificado do cliente.|  
|[\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|Especifica o certificado a ser usado.|  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<serviceCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Especifica as credenciais a serem usadas ao autenticar o serviço, e configurações relacionadas à validação de credenciais do cliente.|  
  
## <a name="remarks"></a>Comentários  
 Esse elemento é usado quando o serviço deve ter o certificado do cliente com antecedência para se comunicar com segurança com o cliente. Isso ocorre ao usar o padrão de comunicação duplex. No padrão mais comum de solicitação/resposta, o cliente inclui seu certificado na solicitação, o serviço usa para criptografar e assinar sua resposta ao cliente. No padrão de comunicação duplex, no entanto, o serviço não tem uma solicitação do cliente e, portanto, ele precisa que o certificado do cliente com antecedência para proteger a mensagem ao cliente. Portanto você deve obter o certificado do cliente em uma negociação de out-of-band e especificar o certificado usando esse elemento. Para obter mais informações sobre serviços duplex, consulte [como: Criar um contrato Duplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
 O certificado definido neste elemento é usado para criptografar mensagens para o cliente somente para associações que estão configurados com `MutualCertificateDuplex` modo de autenticação de segurança de mensagem.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [Como: Criar um contrato Duplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [Comportamentos de segurança](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Trabalhando com certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
