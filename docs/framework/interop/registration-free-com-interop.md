---
title: Interoperabilidade COM sem registro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- assemblies [.NET Framework], interop
- COM interop, registration-free COM interop
- registration-free COM interop
- manifests [.NET Framework]
- registration-free activation
- object activation
- registration-free COM interop, about registration-free COM interop
ms.assetid: 90f308b9-82dc-414a-bce1-77e0155e56bd
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dd08f4d4466582b1e6ff1f80f586482cd3e2ec0c
ms.contentlocale: pt-br
ms.lasthandoff: 08/21/2017

---
# <a name="registration-free-com-interop"></a>Interoperabilidade COM sem registro
A interoperabilidade COM sem registro ativa um componente sem usar o Registro do Windows para armazenar informações de assembly. Em vez de registrar um componente em um computador durante a implantação, você pode criar arquivos de manifesto estilo Win32 em tempo de design que contêm informações sobre associação e a ativação. Esses arquivos de manifesto, em vez de chaves do Registro, direcionam a ativação de um objeto.  
  
 Usar a ativação sem registro dos assemblies em vez de registrá-los durante a implantação oferece duas vantagens:  
  
-   Você pode controlar qual versão DLL é ativada quando mais de uma versão é instalada em um computador.  
  
-   Os usuários finais podem usar XCOPY ou FTP para copiar seu aplicativo para um diretório apropriado no computador deles. Assim, o aplicativo pode ser executado nesse diretório.  
  
 Esta seção descreve os dois tipos de manifestos necessários para a interoperação COM sem registro: manifestos de aplicativo e de componente. Esses manifestos são arquivos XML. Um manifesto de aplicativo, que é criado por um desenvolvedor de aplicativos, contém metadados que descrevem os assemblies e as dependências de assembly. Um manifesto do componente, criado por um desenvolvedor de componente, contém informações que residem no Registro do Windows.  
  
### <a name="requirements-for-registration-free-com-interop"></a>Requisitos da interoperabilidade COM sem registro  
  
1.  O suporte para a interoperabilidade COM sem registro varia ligeiramente dependendo do tipo de assembly de biblioteca; especificamente, se o assembly é não gerenciado (COM lado a lado) ou gerenciado (baseado em .NET). A tabela a seguir mostra o sistema operacional e os requisitos de versão do .NET Framework para cada tipo de assembly.  
  
    |Tipo de assembly|Sistema operacional|Versão do .NET Framework|  
    |-------------------|----------------------|----------------------------|  
    |COM lado a lado|Microsoft Windows XP|Não obrigatório.|  
    |Com base em .NET|Windows XP com SP2|.NET framework versão 1.1 ou posterior.|  
  
     A família Windows Server 2003 também dá suporte à interoperabilidade COM sem registro para assemblies com base em .NET.  
  
     Para que uma classe com base em .NET seja compatível com a ativação sem registro do COM, a classe deve ter um construtor padrão e deve ser pública.  
  
### <a name="configuring-com-components-for-registration-free-activation"></a>Configurando componentes COM para ativação sem registro  
  
1.  Para um componente COM participar da ativação sem registro, ele deve ser implantado como um assembly lado a lado. Assemblies de lado a lado são não gerenciados.  Para obter mais informações, veja “Assemblies lado a lado” na Biblioteca MSDN.  
  
     Para usar os assemblies com lado a lado COM, um desenvolvedor de aplicativos baseados em .NET em sua empresa deve fornecer um manifesto de aplicativo contendo as informações de associação e a ativação. O suporte para assemblies lado a lado não gerenciados é criado no sistema operacional Windows XP. O tempo de execução de COM, com suporte pelo sistema operacional, verifica um manifesto de aplicativo para obter informações de ativação quando o componente está sendo ativado não está no Registro.  
  
     Ativação sem registro é opcional para componentes COM instalados no Windows XP. Para obter instruções detalhadas sobre como adicionar um assembly lado a lado para um aplicativo, pesquise por "Usando assemblies lado a lado" na biblioteca MSDN.  
  
    > [!NOTE]
    >  A execução lado a lado é um recurso do .NET que habilita várias versões do tempo de execução e várias versões de aplicativos e componentes que usam uma versão do tempo de execução no mesmo computador, ao mesmo tempo. Execução lado a lado e assemblies lado a lado são mecanismos diferentes para fornecer funcionalidade de lado a lado.  
  
## <a name="see-also"></a>Consulte também  
 [Como configurar componentes do COM baseados no .NET Framework para ativação sem registro](../../../docs/framework/interop/configure-net-framework-based-com-components-for-reg.md)
