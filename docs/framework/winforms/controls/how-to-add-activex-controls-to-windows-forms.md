---
title: Como adicionar controles ActiveX aos Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: afee07f2f5009abb6cf8facc94b138f4ea2a11fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="92be7-102">Como adicionar controles ActiveX aos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92be7-102">How to: Add ActiveX Controls to Windows Forms</span></span>
<span data-ttu-id="92be7-103">Enquanto o Designer de Formulários do Windows é otimizado para hospedar controles dos Windows Forms, também é possível colocar controles ActiveX nos Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="92be7-103">While the Windows Forms Designer is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="92be7-104">Há limitações de desempenho para o Windows Forms quando os controles ActiveX são adicionados a ele.</span><span class="sxs-lookup"><span data-stu-id="92be7-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>  
  
 <span data-ttu-id="92be7-105">Antes de adicionar controles ActiveX ao seu formulário, você deve adicioná-los à caixa de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="92be7-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="92be7-106">Para obter mais informações, consulte [Componentes COM, Caixa de diálogo Personalizar caixa de ferramentas](http://msdn.microsoft.com/en-us/171333f3-f207-4e02-bbdc-17862556212c).</span><span class="sxs-lookup"><span data-stu-id="92be7-106">For more information, see [COM Components, Customize Toolbox Dialog Box](http://msdn.microsoft.com/en-us/171333f3-f207-4e02-bbdc-17862556212c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92be7-107">As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas.</span><span class="sxs-lookup"><span data-stu-id="92be7-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="92be7-108">Para alterar as configurações, clique em **Importar e exportar configurações** no menu **Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="92be7-108">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="92be7-109">Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="92be7-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="92be7-110">Para adicionar um controle ActiveX ao seu Windows Form</span><span class="sxs-lookup"><span data-stu-id="92be7-110">To add an ActiveX control to your Windows Form</span></span>  
  
-   <span data-ttu-id="92be7-111">Clique duas vezes no controle na Caixa de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="92be7-111">Double-click the control on the Toolbox.</span></span>  
  
     [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]<span data-ttu-id="92be7-112"> adiciona todas as referências ao controle em seu projeto.</span><span class="sxs-lookup"><span data-stu-id="92be7-112"> adds all references to the control in your project.</span></span> <span data-ttu-id="92be7-113">Para obter mais informações sobre as coisas para ter em mente ao usar controles ActiveX nos Windows Forms, consulte [Considerações sobre quando hospedar um controle ActiveX em um Windows Form](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="92be7-113">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92be7-114">O Importador de controle ActiveX dos Windows Forms (AxImp.exe) cria os argumentos de evento de um tipo diferente do que o esperado após a importação de bibliotecas de link dinâmico do ActiveX.</span><span class="sxs-lookup"><span data-stu-id="92be7-114">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="92be7-115">Os argumentos criados pelo AxImp.exe são semelhantes ao seguinte: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, quando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` for esperado.</span><span class="sxs-lookup"><span data-stu-id="92be7-115">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="92be7-116">Lembre-se de que essa irregularidade não impede que o código funcione normalmente.</span><span class="sxs-lookup"><span data-stu-id="92be7-116">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="92be7-117">Para obter detalhes, consulte [Importador de Controle ActiveX dos Windows Forms (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).</span><span class="sxs-lookup"><span data-stu-id="92be7-117">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92be7-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="92be7-118">See Also</span></span>  
 [<span data-ttu-id="92be7-119">Controles dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92be7-119">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="92be7-120">Controles e objetos programáveis comparados em diversas linguagens e bibliotecas</span><span class="sxs-lookup"><span data-stu-id="92be7-120">Controls and Programmable Objects Compared in Various Languages and Libraries</span></span>](http://msdn.microsoft.com/en-us/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [<span data-ttu-id="92be7-121">Como Adicionar Controles ao Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92be7-121">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="92be7-122">Organizando Controles nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92be7-122">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="92be7-123">Rotulando controles individuais dos Windows Forms e fornecendo atalhos para eles</span><span class="sxs-lookup"><span data-stu-id="92be7-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="92be7-124">Controles a serem usados nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92be7-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="92be7-125">Controles dos Windows Forms por função</span><span class="sxs-lookup"><span data-stu-id="92be7-125">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)