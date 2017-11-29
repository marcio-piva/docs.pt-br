---
title: "Suporte de automação de interface de usuário para o tipo de controle ProgressBar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control types, Progress Bar
- ProgressBar control type
- UI Automation, Progress Bar control type
ms.assetid: 302e778c-24b0-4789-814a-c8d37cf53a5f
caps.latest.revision: "21"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 84ff5d1d59204fec4bbddd43dd834d1c9b22406d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-support-for-the-progressbar-control-type"></a><span data-ttu-id="f7102-102">Suporte de automação de interface de usuário para o tipo de controle ProgressBar</span><span class="sxs-lookup"><span data-stu-id="f7102-102">UI Automation Support for the ProgressBar Control Type</span></span>
> [!NOTE]
>  <span data-ttu-id="f7102-103">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="f7102-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f7102-104">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="f7102-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f7102-105">Este tópico fornece informações sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] suporte para o tipo de controle ProgressBar.</span><span class="sxs-lookup"><span data-stu-id="f7102-105">This topic provides information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support for the ProgressBar control type.</span></span> <span data-ttu-id="f7102-106">Em [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], um tipo de controle é um conjunto de condições que um controle precisa atender para usar o <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> propriedade.</span><span class="sxs-lookup"><span data-stu-id="f7102-106">In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a control type is a set of conditions that a control must meet in order to use the <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> property.</span></span> <span data-ttu-id="f7102-107">As condições incluem diretrizes específicas para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] estrutura de árvore [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] valores de propriedade, padrões de controle e [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] eventos.</span><span class="sxs-lookup"><span data-stu-id="f7102-107">The conditions include specific guidelines for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values, control patterns, and [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events.</span></span>  
  
 <span data-ttu-id="f7102-108">Controles de barra de progresso são um exemplo de controles que implementam o tipo de controle ProgressBar.</span><span class="sxs-lookup"><span data-stu-id="f7102-108">Progress bar controls are an example of controls that implement the ProgressBar control type.</span></span> <span data-ttu-id="f7102-109">Controles de barra de progresso são usados para indicar o progresso de uma operação demorada.</span><span class="sxs-lookup"><span data-stu-id="f7102-109">Progress bar controls are used to indicate the progress of a lengthy operation.</span></span> <span data-ttu-id="f7102-110">O controle consiste em um retângulo que é preenchido com a cor de realce de sistema como uma operação progride.</span><span class="sxs-lookup"><span data-stu-id="f7102-110">The control consists of a rectangle that is gradually filled with the system highlight color as an operation progresses.</span></span>  
  
 <span data-ttu-id="f7102-111">As seções a seguir definem as [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] eventos para o tipo de controle ProgressBar, propriedades, padrões de controle e estrutura de árvore.</span><span class="sxs-lookup"><span data-stu-id="f7102-111">The following sections define the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, properties, control patterns, and events for the ProgressBar control type.</span></span> <span data-ttu-id="f7102-112">O [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisitos se aplicam a todos os controles de lista, se [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], ou [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7102-112">The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requirements apply to all list controls, whether [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], or [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a><span data-ttu-id="f7102-113">Estrutura de árvore de automação da interface do usuário necessário</span><span class="sxs-lookup"><span data-stu-id="f7102-113">Required UI Automation Tree Structure</span></span>  
 <span data-ttu-id="f7102-114">A tabela a seguir descreve o modo de exibição de controle e exibição de conteúdo de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] controles de árvore referente a barra de progresso e descreve o que pode ser contido em cada modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="f7102-114">The following table depicts the control view and the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree that pertains to progress bar controls and describes what can be contained in each view.</span></span> <span data-ttu-id="f7102-115">Para obter mais informações sobre o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de árvore, consulte [visão geral de árvore de automação de interface do usuário](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f7102-115">For more information on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span></span>  
  
|<span data-ttu-id="f7102-116">Exibição de controle</span><span class="sxs-lookup"><span data-stu-id="f7102-116">Control View</span></span>|<span data-ttu-id="f7102-117">Exibição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="f7102-117">Content View</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="f7102-118">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="f7102-118">ProgressBar</span></span>|<span data-ttu-id="f7102-119">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="f7102-119">ProgressBar</span></span>|  
  
 <span data-ttu-id="f7102-120">Os controles de barra de progresso não possuem nenhum filho na exibição de controle ou conteúdo do [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árvore.</span><span class="sxs-lookup"><span data-stu-id="f7102-120">The progress bar controls do not have any children in the control or content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree.</span></span>  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a><span data-ttu-id="f7102-121">Propriedades de automação de interface do usuário necessário</span><span class="sxs-lookup"><span data-stu-id="f7102-121">Required UI Automation Properties</span></span>  
 <span data-ttu-id="f7102-122">A seguinte tabela lista o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] propriedades cujos valores ou definição são especialmente relevantes para controles de barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="f7102-122">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties whose value or definition is especially relevant to progress bar controls.</span></span> <span data-ttu-id="f7102-123">Para obter mais informações sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] propriedades, consulte [propriedades de automação de interface do usuário para clientes](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f7102-123">For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="f7102-124">Propriedade</span><span class="sxs-lookup"><span data-stu-id="f7102-124"> Property</span></span>|<span data-ttu-id="f7102-125">Valor</span><span class="sxs-lookup"><span data-stu-id="f7102-125">Value</span></span>|<span data-ttu-id="f7102-126">Observações</span><span class="sxs-lookup"><span data-stu-id="f7102-126">Notes</span></span>|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|<span data-ttu-id="f7102-127">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f7102-127">See notes.</span></span>|<span data-ttu-id="f7102-128">O valor dessa propriedade deve ser exclusivo em todos os controles em um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f7102-128">The value of this property needs to be unique across all controls in an application.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|<span data-ttu-id="f7102-129">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f7102-129">See notes.</span></span>|<span data-ttu-id="f7102-130">O retângulo mais externo que contém todo o controle.</span><span class="sxs-lookup"><span data-stu-id="f7102-130">The outermost rectangle that contains the whole control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|<span data-ttu-id="f7102-131">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f7102-131">See notes.</span></span>|<span data-ttu-id="f7102-132">Suporte se houver um retângulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="f7102-132">Supported if there is a bounding rectangle.</span></span> <span data-ttu-id="f7102-133">Se não for todo ponto dentro do retângulo delimitador é clicável, e você executa o teste de hit especializado, substituir e forneça um ponto clicável.</span><span class="sxs-lookup"><span data-stu-id="f7102-133">If not every point within the bounding rectangle is clickable, and you perform specialized hit testing, then override and provide a clickable point.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|<span data-ttu-id="f7102-134">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f7102-134">See notes.</span></span>|<span data-ttu-id="f7102-135">Se o controle pode receber o foco do teclado, deve suportar essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="f7102-135">If the control can receive keyboard focus, it must support this property.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|<span data-ttu-id="f7102-136">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f7102-136">See notes.</span></span>|<span data-ttu-id="f7102-137">O controle de barra de progresso normalmente obtém seu nome de um rótulo de texto estático.</span><span class="sxs-lookup"><span data-stu-id="f7102-137">The progress bar control typically gets its name from a static text label.</span></span> <span data-ttu-id="f7102-138">Se não houver um rótulo de texto estático o desenvolvedor do aplicativo deve expor um valor para o `Name` propriedade.</span><span class="sxs-lookup"><span data-stu-id="f7102-138">If there is not a static text label the application developer must expose a value for the `Name` property.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|<span data-ttu-id="f7102-139">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f7102-139">See notes.</span></span>|<span data-ttu-id="f7102-140">Se houver um rótulo de texto estático, em seguida, essa propriedade deve expor uma referência para esse controle.</span><span class="sxs-lookup"><span data-stu-id="f7102-140">If there is a static text label then this property must expose a reference to that control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|<span data-ttu-id="f7102-141">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="f7102-141">ProgressBar</span></span>|<span data-ttu-id="f7102-142">Esse valor é o mesmo para todas as estruturas de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="f7102-142">This value is the same for all UI frameworks.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|<span data-ttu-id="f7102-143">"barra de progresso"</span><span class="sxs-lookup"><span data-stu-id="f7102-143">"progress bar"</span></span>|<span data-ttu-id="f7102-144">Cadeia de caracteres localizada correspondente ao tipo de controle ProgressBar.</span><span class="sxs-lookup"><span data-stu-id="f7102-144">Localized string corresponding to the ProgressBar control type.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|<span data-ttu-id="f7102-145">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="f7102-145">True</span></span>|<span data-ttu-id="f7102-146">O controle de barra de progresso é sempre incluído na exibição de conteúdo do [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árvore.</span><span class="sxs-lookup"><span data-stu-id="f7102-146">The progress bar control is always included in the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|<span data-ttu-id="f7102-147">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="f7102-147">True</span></span>|<span data-ttu-id="f7102-148">O controle de barra de progresso é sempre incluído na exibição de controle de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árvore.</span><span class="sxs-lookup"><span data-stu-id="f7102-148">The progress bar control is always included in the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree.</span></span>|  
  
<a name="Required_UI_Automation_Control_Patterns_and_Properties"></a>   
## <a name="required-ui-automation-control-patterns-and-properties"></a><span data-ttu-id="f7102-149">Padrões de controle de automação de interface do usuário e propriedades necessários</span><span class="sxs-lookup"><span data-stu-id="f7102-149">Required UI Automation Control Patterns and Properties</span></span>  
 <span data-ttu-id="f7102-150">A seguinte tabela lista o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] devem ser suportados por controles de barra de progresso de padrões de controle.</span><span class="sxs-lookup"><span data-stu-id="f7102-150">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] control patterns required to be supported by progress bar controls.</span></span> <span data-ttu-id="f7102-151">Para obter mais informações sobre padrões de controle, consulte [visão geral de padrões de controle de automação de interface do usuário](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f7102-151">For more information on control patterns, see [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span></span>  
  
|<span data-ttu-id="f7102-152">Propriedade padrão/padrão de controle</span><span class="sxs-lookup"><span data-stu-id="f7102-152">Control Pattern/Pattern Property</span></span>|<span data-ttu-id="f7102-153">Valor do suporte</span><span class="sxs-lookup"><span data-stu-id="f7102-153">Support/Value</span></span>|<span data-ttu-id="f7102-154">Observações</span><span class="sxs-lookup"><span data-stu-id="f7102-154">Notes</span></span>|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|<span data-ttu-id="f7102-155">Depende</span><span class="sxs-lookup"><span data-stu-id="f7102-155">Depends</span></span>|<span data-ttu-id="f7102-156">Controles de barra de progresso que fornecem uma indicação de progresso textual deve implementar <xref:System.Windows.Automation.Provider.IValueProvider>.</span><span class="sxs-lookup"><span data-stu-id="f7102-156">Progress bar controls that give a textual indication of progress must implement <xref:System.Windows.Automation.Provider.IValueProvider>.</span></span>|  
|<xref:System.Windows.Automation.Provider.IValueProvider.IsReadOnly%2A>|<span data-ttu-id="f7102-157">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="f7102-157">True</span></span>|<span data-ttu-id="f7102-158">O valor dessa propriedade é sempre verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="f7102-158">The value for this property is always True.</span></span>|  
|<xref:System.Windows.Automation.Provider.IValueProvider.Value%2A>|<span data-ttu-id="f7102-159">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f7102-159">See notes.</span></span>|<span data-ttu-id="f7102-160">Essa propriedade expõe progresso textual de um controle de barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="f7102-160">This property exposes textual progress of a progress bar control.</span></span>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|<span data-ttu-id="f7102-161">Depende</span><span class="sxs-lookup"><span data-stu-id="f7102-161">Depends</span></span>|<span data-ttu-id="f7102-162">Controles de barra de progresso que levam um intervalo numérico devem implementar<xref:System.Windows.Automation.Provider.IRangeValueProvider></span><span class="sxs-lookup"><span data-stu-id="f7102-162">Progress bar controls that take a numeric range must implement <xref:System.Windows.Automation.Provider.IRangeValueProvider></span></span>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Minimum%2A>|<span data-ttu-id="f7102-163">0.0</span><span class="sxs-lookup"><span data-stu-id="f7102-163">0.0</span></span>|<span data-ttu-id="f7102-164">O valor dessa propriedade é o menor valor que o controle pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="f7102-164">The value of this property is the smallest value that the control can be set to.</span></span>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Maximum%2A>|<span data-ttu-id="f7102-165">100.0</span><span class="sxs-lookup"><span data-stu-id="f7102-165">100.0</span></span>|<span data-ttu-id="f7102-166">O valor dessa propriedade é o maior valor que o controle pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="f7102-166">The value of this property is the largest value that the control can be set to.</span></span>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.SmallChange%2A>|<span data-ttu-id="f7102-167">NaN</span><span class="sxs-lookup"><span data-stu-id="f7102-167">NaN</span></span>|<span data-ttu-id="f7102-168">Essa propriedade não é necessária porque os controles de barra de progresso são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="f7102-168">This property is not required because progress bar controls are read-only.</span></span>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.LargeChange%2A>|<span data-ttu-id="f7102-169">NaN</span><span class="sxs-lookup"><span data-stu-id="f7102-169">NaN</span></span>|<span data-ttu-id="f7102-170">Essa propriedade não é necessária porque os controles de barra de progresso são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="f7102-170">This property is not required because progress bar controls are read-only.</span></span>|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a><span data-ttu-id="f7102-171">Eventos de automação de interface do usuário necessário</span><span class="sxs-lookup"><span data-stu-id="f7102-171">Required UI Automation Events</span></span>  
 <span data-ttu-id="f7102-172">A seguinte tabela lista o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] eventos que devem ser suportados por todos os controles de barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="f7102-172">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events required to be supported by all progress bar controls.</span></span> <span data-ttu-id="f7102-173">Para obter mais informações sobre eventos, consulte [visão geral sobre eventos de automação de interface do usuário](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f7102-173">For more information on events, see [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="f7102-174">Evento</span><span class="sxs-lookup"><span data-stu-id="f7102-174"> Event</span></span>|<span data-ttu-id="f7102-175">Suporte</span><span class="sxs-lookup"><span data-stu-id="f7102-175">Support</span></span>|<span data-ttu-id="f7102-176">Observações</span><span class="sxs-lookup"><span data-stu-id="f7102-176">Notes</span></span>|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<span data-ttu-id="f7102-177"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>evento de propriedade alterada.</span><span class="sxs-lookup"><span data-stu-id="f7102-177"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> property-changed event.</span></span>|<span data-ttu-id="f7102-178">Necessária</span><span class="sxs-lookup"><span data-stu-id="f7102-178">Required</span></span>|<span data-ttu-id="f7102-179">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f7102-179">None</span></span>|  
|<span data-ttu-id="f7102-180"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>evento de propriedade alterada.</span><span class="sxs-lookup"><span data-stu-id="f7102-180"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> property-changed event.</span></span>|<span data-ttu-id="f7102-181">Necessária</span><span class="sxs-lookup"><span data-stu-id="f7102-181">Required</span></span>|<span data-ttu-id="f7102-182">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f7102-182">None</span></span>|  
|<span data-ttu-id="f7102-183"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>evento de propriedade alterada.</span><span class="sxs-lookup"><span data-stu-id="f7102-183"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> property-changed event.</span></span>|<span data-ttu-id="f7102-184">Necessária</span><span class="sxs-lookup"><span data-stu-id="f7102-184">Required</span></span>|<span data-ttu-id="f7102-185">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f7102-185">None</span></span>|  
|<span data-ttu-id="f7102-186"><xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>evento de propriedade alterada.</span><span class="sxs-lookup"><span data-stu-id="f7102-186"><xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> property-changed event.</span></span>|<span data-ttu-id="f7102-187">Necessária</span><span class="sxs-lookup"><span data-stu-id="f7102-187">Required</span></span>|<span data-ttu-id="f7102-188">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f7102-188">None</span></span>|  
|<span data-ttu-id="f7102-189"><xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty>evento de propriedade alterada.</span><span class="sxs-lookup"><span data-stu-id="f7102-189"><xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> property-changed event.</span></span>|<span data-ttu-id="f7102-190">Depende</span><span class="sxs-lookup"><span data-stu-id="f7102-190">Depends</span></span>|<span data-ttu-id="f7102-191">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f7102-191">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|<span data-ttu-id="f7102-192">Necessária</span><span class="sxs-lookup"><span data-stu-id="f7102-192">Required</span></span>|<span data-ttu-id="f7102-193">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f7102-193">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|<span data-ttu-id="f7102-194">Necessária</span><span class="sxs-lookup"><span data-stu-id="f7102-194">Required</span></span>|<span data-ttu-id="f7102-195">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f7102-195">None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7102-196">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f7102-196">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType.ProgressBar>  
 [<span data-ttu-id="f7102-197">Visão geral de tipos de controle de automação da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="f7102-197">UI Automation Control Types Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [<span data-ttu-id="f7102-198">Visão geral de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="f7102-198">UI Automation Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-overview.md)