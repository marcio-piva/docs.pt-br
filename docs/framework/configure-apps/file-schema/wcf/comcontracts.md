---
title: '&lt;comContracts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 168bd57652aca5f3c1b61c90abea5288bd1a6719
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcomcontractsgt"></a><span data-ttu-id="c06f4-102">&lt;comContracts&gt;</span><span class="sxs-lookup"><span data-stu-id="c06f4-102">&lt;comContracts&gt;</span></span>
<span data-ttu-id="c06f4-103">O `comContracts` seção de configuração contém elementos que permitem que você especificar várias propriedades de um contrato de serviço de integração COM+.</span><span class="sxs-lookup"><span data-stu-id="c06f4-103">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="c06f4-104">Especificando o Namespace e um contrato</span><span class="sxs-lookup"><span data-stu-id="c06f4-104">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="c06f4-105">Contratos de serviço COM+ integration estão restritos atualmente para o namespace "http://tempuri.org" e nome de contrato é derivado da interface COM suporte.</span><span class="sxs-lookup"><span data-stu-id="c06f4-105">COM+ integration service contracts are currently restricted to the "http://tempuri.org" namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="c06f4-106">No entanto, você pode especificar alternativas usando o `comContracts` seção no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="c06f4-106">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="c06f4-107">Por exemplo, você pode usar a configuração a seguir para especificar o nome do contrato e do namespace do contrato de serviço, bem como uma opção para impor o uso de associações de sessão.</span><span class="sxs-lookup"><span data-stu-id="c06f4-107">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
  </comContract>  
</comContracts>  
```  
  
 <span data-ttu-id="c06f4-108">Quando o serviço é inicializado, os namespaces especificados e os nomes de contrato são aplicados as descrições de serviço gerado.</span><span class="sxs-lookup"><span data-stu-id="c06f4-108">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="c06f4-109">Quando esta seção está vazia, a inicialização do serviço se aplica a um nome de namespace e contrato padrão obtido com a ID de interface COM suporte.</span><span class="sxs-lookup"><span data-stu-id="c06f4-109">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="c06f4-110">Além disso, você pode usar o [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elemento para especificar o COM+ métodos que são expostos quando a interface em um componente COM+ é exposta como um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="c06f4-110">In addition, you can use the [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="c06f4-111">Você também pode usar o [ \<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) para especificar os tipos persistentes usados na integração.</span><span class="sxs-lookup"><span data-stu-id="c06f4-111">You can also use the [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="c06f4-112">Finalmente, você pode usar o [ \<userDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) elemento para incluir um usuário definido tipos (UDT) que devem ser incluídas no contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="c06f4-112">Finally, you can use the [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c06f4-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c06f4-113">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="c06f4-114">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="c06f4-114">\<exposedMethod></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)  
 [<span data-ttu-id="c06f4-115">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="c06f4-115">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)  
 [<span data-ttu-id="c06f4-116">\<userDefinedType ></span><span class="sxs-lookup"><span data-stu-id="c06f4-116">\<userDefinedType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)  
 [<span data-ttu-id="c06f4-117">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="c06f4-117">\<comContract></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)  
 [<span data-ttu-id="c06f4-118">Integrando aplicativos COM+</span><span class="sxs-lookup"><span data-stu-id="c06f4-118">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="c06f4-119">Como: definir configurações de serviço COM+</span><span class="sxs-lookup"><span data-stu-id="c06f4-119">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)