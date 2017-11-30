---
title: "&lt;SMTP&gt; elemento (configurações de rede)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 17b4050c43354da7e7ba6c3ea13a0c7621faf0a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="981f6-102">&lt;SMTP&gt; elemento (configurações de rede)</span><span class="sxs-lookup"><span data-stu-id="981f6-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="981f6-103">Configura o formato de entrega, o método de entrega, endereço de envio de emails.</span><span class="sxs-lookup"><span data-stu-id="981f6-103">Configures the delivery format, delivery method, and from address for sending e-mails.</span></span>  
  
 <span data-ttu-id="981f6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="981f6-104">\<configuration></span></span>  
<span data-ttu-id="981f6-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="981f6-105">\<system.net></span></span>  
<span data-ttu-id="981f6-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="981f6-106">\<mailSettings></span></span>  
<span data-ttu-id="981f6-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="981f6-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981f6-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="981f6-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="981f6-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="981f6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="981f6-110">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="981f6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="981f6-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="981f6-111">Attributes</span></span>  
  
|<span data-ttu-id="981f6-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="981f6-112">Attribute</span></span>|<span data-ttu-id="981f6-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="981f6-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="981f6-114">Especifica o formato de entrega de emails de saída.</span><span class="sxs-lookup"><span data-stu-id="981f6-114">Specifies the delivery format for outgoing e-mails.</span></span> <span data-ttu-id="981f6-115">Os valores aceitáveis são SevenBit e tratados internacionais.</span><span class="sxs-lookup"><span data-stu-id="981f6-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="981f6-116">Especifica o método de entrega de emails.</span><span class="sxs-lookup"><span data-stu-id="981f6-116">Specifies the delivery method for e-mails.</span></span> <span data-ttu-id="981f6-117">Os valores aceitáveis são specifiedPickupDirectory, pickupDirectoryFromIis e rede.</span><span class="sxs-lookup"><span data-stu-id="981f6-117">Acceptable values are network, pickupDirectoryFromIis, and specifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="981f6-118">Especifica o endereço para emails de saída do.</span><span class="sxs-lookup"><span data-stu-id="981f6-118">Specifies the from address for outgoing e-mails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="981f6-119">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="981f6-119">Child Elements</span></span>  
  
|<span data-ttu-id="981f6-120">Atributo</span><span class="sxs-lookup"><span data-stu-id="981f6-120">Attribute</span></span>|<span data-ttu-id="981f6-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="981f6-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="981f6-122">Configura o diretório local para um servidor de transporte protocolo SMTP (Simple Mail).</span><span class="sxs-lookup"><span data-stu-id="981f6-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="981f6-123">Configura as opções de rede para um servidor SMTP externo.</span><span class="sxs-lookup"><span data-stu-id="981f6-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="981f6-124">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="981f6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="981f6-125">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="981f6-125">**Element**</span></span>|<span data-ttu-id="981f6-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="981f6-126">**Description**</span></span>|  
|-----------------|---------------------|  
|<span data-ttu-id="981f6-127">[\<mailSettings> Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md) [Elemento mailSettings> (configurações de rede)]</span><span class="sxs-lookup"><span data-stu-id="981f6-127">[\<mailSettings> Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)</span></span>|<span data-ttu-id="981f6-128">Configura as opções de envio de email.</span><span class="sxs-lookup"><span data-stu-id="981f6-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="981f6-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="981f6-129">Example</span></span>  
 <span data-ttu-id="981f6-130">O exemplo a seguir especifica os parâmetros apropriados de SMTP para enviar email usando as credenciais de rede padrão.</span><span class="sxs-lookup"><span data-stu-id="981f6-130">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="981f6-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="981f6-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="981f6-132">Esquema de configurações de rede</span><span class="sxs-lookup"><span data-stu-id="981f6-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)