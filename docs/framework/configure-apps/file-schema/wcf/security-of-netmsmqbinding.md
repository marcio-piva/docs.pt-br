---
title: "&lt;segurança&gt; do &lt;netMsmqBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 15ebbd1f0f139ef0d66ed802b990876735074485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="df975-102">&lt;segurança&gt; do &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="df975-102">&lt;security&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="df975-103">Define as configurações de segurança para uma associação de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="df975-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="df975-104">Especifica se o transporte ou segurança SOAP está habilitada e, em caso afirmativo, quais níveis de proteção e o modo de autenticação estão em uso.</span><span class="sxs-lookup"><span data-stu-id="df975-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="df975-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="df975-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="df975-106">\<associações ></span><span class="sxs-lookup"><span data-stu-id="df975-106">\<bindings></span></span>  
<span data-ttu-id="df975-107">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="df975-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="df975-108">\<associação ></span><span class="sxs-lookup"><span data-stu-id="df975-108">\<binding></span></span>  
<span data-ttu-id="df975-109">\<segurança ></span><span class="sxs-lookup"><span data-stu-id="df975-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df975-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df975-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df975-111">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="df975-111">Attributes and Elements</span></span>  
 <span data-ttu-id="df975-112">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="df975-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df975-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="df975-113">Attributes</span></span>  
  
|<span data-ttu-id="df975-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="df975-114">Attribute</span></span>|<span data-ttu-id="df975-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="df975-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df975-116">modo</span><span class="sxs-lookup"><span data-stu-id="df975-116">mode</span></span>|<span data-ttu-id="df975-117">Especifica o tipo de segurança que controla a confidencialidade, integridade e a autenticação.</span><span class="sxs-lookup"><span data-stu-id="df975-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="df975-118">Os valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="df975-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="df975-119">-Nenhum: Isso desabilita a segurança.</span><span class="sxs-lookup"><span data-stu-id="df975-119">-   None: This disables security.</span></span><br /><span data-ttu-id="df975-120">-Transporte: Autenticação e proteção são oferecidos pelo transporte.</span><span class="sxs-lookup"><span data-stu-id="df975-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="df975-121">Isso se aplica à segurança de mensagem entre os gerenciadores de fila de dois.</span><span class="sxs-lookup"><span data-stu-id="df975-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="df975-122">Não há nenhuma segurança oferecida entre o aplicativo e o Gerenciador de fila.</span><span class="sxs-lookup"><span data-stu-id="df975-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="df975-123">Os aplicativos Msmq existentes são funcionalmente equivalentes com esse tipo de modo de segurança.</span><span class="sxs-lookup"><span data-stu-id="df975-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="df975-124">-Mensagem: Especifica a segurança do aplicativo ponta.</span><span class="sxs-lookup"><span data-stu-id="df975-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="df975-125">Não há nenhuma segurança oferecida na camada de transporte.</span><span class="sxs-lookup"><span data-stu-id="df975-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="df975-126">Isso é semelhante para a segurança oferecida por outras associações padrão.</span><span class="sxs-lookup"><span data-stu-id="df975-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="df975-127">-Ambos: Oferece segurança de transporte e de camada de mensagens SOAP.</span><span class="sxs-lookup"><span data-stu-id="df975-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="df975-128">A mesma credencial é necessária em ambos os níveis.</span><span class="sxs-lookup"><span data-stu-id="df975-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="df975-129">O valor padrão é o transporte.</span><span class="sxs-lookup"><span data-stu-id="df975-129">The default value is Transport.</span></span> <span data-ttu-id="df975-130">Esse atributo é do tipo <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="df975-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df975-131">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="df975-131">Child Elements</span></span>  
  
|<span data-ttu-id="df975-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="df975-132">Element</span></span>|<span data-ttu-id="df975-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="df975-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df975-134">\<mensagem ></span><span class="sxs-lookup"><span data-stu-id="df975-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="df975-135">Define as configurações de segurança de mensagem SOAP.</span><span class="sxs-lookup"><span data-stu-id="df975-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="df975-136">Esse elemento é do tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="df975-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="df975-137">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="df975-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="df975-138">Define as configurações de segurança para o transporte MSMQ.</span><span class="sxs-lookup"><span data-stu-id="df975-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="df975-139">Esse elemento é do tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="df975-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df975-140">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="df975-140">Parent Elements</span></span>  
  
|<span data-ttu-id="df975-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="df975-141">Element</span></span>|<span data-ttu-id="df975-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="df975-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df975-143">associação</span><span class="sxs-lookup"><span data-stu-id="df975-143">binding</span></span>|<span data-ttu-id="df975-144">O elemento de associação do [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="df975-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df975-145">Consulte também</span><span class="sxs-lookup"><span data-stu-id="df975-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [<span data-ttu-id="df975-146">Protegendo serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="df975-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="df975-147">[Bindings](../../../../../docs/framework/wcf/bindings.md) (Associações)</span><span class="sxs-lookup"><span data-stu-id="df975-147">[Bindings](../../../../../docs/framework/wcf/bindings.md)</span></span>  
 [<span data-ttu-id="df975-148">Configurando associações fornecidas pelo sistema</span><span class="sxs-lookup"><span data-stu-id="df975-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="df975-149">Usando associações para configurar clientes e serviços do Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="df975-149">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="df975-150">\<associação ></span><span class="sxs-lookup"><span data-stu-id="df975-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="df975-151">Filas no WCF</span><span class="sxs-lookup"><span data-stu-id="df975-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)