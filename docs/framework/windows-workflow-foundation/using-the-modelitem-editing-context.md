---
title: "Usando o contexto de edição de ModelItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fde8bf45e01f8e3fede04c08d63177271a4a6faf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="5ec38-102">Usando o contexto de edição de ModelItem</span><span class="sxs-lookup"><span data-stu-id="5ec38-102">Using the ModelItem Editing Context</span></span>
<span data-ttu-id="5ec38-103"><xref:System.Activities.Presentation.Model.ModelItem> que contexto de edição é o objeto que o aplicativo host usa para se comunicar com o designer.</span><span class="sxs-lookup"><span data-stu-id="5ec38-103">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <span data-ttu-id="5ec38-104"><xref:System.Activities.Presentation.EditingContext> expõe dois métodos, <xref:System.Activities.Presentation.EditingContext.Items%2A> e <xref:System.Activities.Presentation.EditingContext.Services%2A>, que podem ser usados</span><span class="sxs-lookup"><span data-stu-id="5ec38-104"><xref:System.Activities.Presentation.EditingContext> exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="5ec38-105">A coleção de itens</span><span class="sxs-lookup"><span data-stu-id="5ec38-105">The Items collection</span></span>  
 <span data-ttu-id="5ec38-106">A coleção de <xref:System.Activities.Presentation.EditingContext.Items%2A> é usada para acessar os dados que são compartilhados entre o host e o designer, ou os dados que estão disponíveis para todos os designers.</span><span class="sxs-lookup"><span data-stu-id="5ec38-106">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="5ec38-107">Essa coleção possui os seguintes recursos, acessados por meio da classe <xref:System.Activities.Presentation.ContextItemManager> :</span><span class="sxs-lookup"><span data-stu-id="5ec38-107">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1.  <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2.  <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="5ec38-108">A coleção de serviços</span><span class="sxs-lookup"><span data-stu-id="5ec38-108">The Services collection</span></span>  
 <span data-ttu-id="5ec38-109">A coleção de <xref:System.Activities.Presentation.EditingContext.Services%2A> é usada para acessar os serviços que o designer usa para interagir com o host, ou serviços que todos os designers usam.</span><span class="sxs-lookup"><span data-stu-id="5ec38-109">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="5ec38-110">Esta coleção tem os seguintes métodos de observação:</span><span class="sxs-lookup"><span data-stu-id="5ec38-110">This collection has the following methods of note:</span></span>  
  
1.  <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2.  <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="5ec38-111">Atribuindo a um designer uma atividade</span><span class="sxs-lookup"><span data-stu-id="5ec38-111">Assigning a designer an activity</span></span>  
 <span data-ttu-id="5ec38-112">Para especificar que o designer uma atividade, use o atributo de designer é usado.</span><span class="sxs-lookup"><span data-stu-id="5ec38-112">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="5ec38-113">Criando um serviço</span><span class="sxs-lookup"><span data-stu-id="5ec38-113">Creating a service</span></span>  
 <span data-ttu-id="5ec38-114">Para criar um serviço que os serve como uma canalização de informações entre o designer e o host, uma interface e uma implementação deve ser criados.</span><span class="sxs-lookup"><span data-stu-id="5ec38-114">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="5ec38-115">A interface é usada pelo método de <xref:System.Activities.Presentation.ServiceManager.Publish%2A> para definir os membros de serviço, e a implementação contém a lógica para o serviço.</span><span class="sxs-lookup"><span data-stu-id="5ec38-115">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="5ec38-116">No exemplo de código, uma interface e uma implementação de serviço são criadas.</span><span class="sxs-lookup"><span data-stu-id="5ec38-116">In the following code example, a service interface and implementation are created.</span></span>  
  
```  
public interface IMyService  
    {  
        IEnumerable<string> GetValues(string DisplayName);  
    }  
  
    public class MyServiceImpl : IMyService  
    {  
        public IEnumerable<string> GetValues(string DisplayName)  
        {  
            return new string[]  {   
                DisplayName + " One",   
                DisplayName + " Two",  
                "Three " + DisplayName  
            } ;  
        }  
    }  
```  
  
## <a name="publishing-a-service"></a><span data-ttu-id="5ec38-117">Publicando um serviço</span><span class="sxs-lookup"><span data-stu-id="5ec38-117">Publishing a service</span></span>  
 <span data-ttu-id="5ec38-118">Para que um designer consome um serviço, deve primeiro ser publicados pelo host que usa o método de <xref:System.Activities.Presentation.ServiceManager.Publish%2A> .</span><span class="sxs-lookup"><span data-stu-id="5ec38-118">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="5ec38-119">Assinar um serviço</span><span class="sxs-lookup"><span data-stu-id="5ec38-119">Subscribing to a service</span></span>  
 <span data-ttu-id="5ec38-120">O designer obtém o acesso ao serviço usando o método de <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> no método de <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> .</span><span class="sxs-lookup"><span data-stu-id="5ec38-120">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="5ec38-121">O trecho de código a seguir demonstra como assinar um serviço.</span><span class="sxs-lookup"><span data-stu-id="5ec38-121">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
```  
protected override void OnModelItemChanged(object newItem)  
{  
    if (!subscribed)  
    {  
        this.Context.Services.Subscribe<IMyService>(  
            servInstance =>  
            {  
                listBox1.ItemsSource = servInstance.GetValues(this.ModelItem.Properties["DisplayName"].ComputedValue.ToString());  
            }  
            );  
        subscribed = true;   
    }  
}  
```  
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="5ec38-122">Compartilhando dados usando a coleção de itens</span><span class="sxs-lookup"><span data-stu-id="5ec38-122">Sharing data using the Items collection</span></span>  
 <span data-ttu-id="5ec38-123">Usar a coleção de itens é semelhante a usar a coleção de serviços, exceto que <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> é usado em vez de publicação.</span><span class="sxs-lookup"><span data-stu-id="5ec38-123">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="5ec38-124">Essa coleção é mais adequado para compartilhar dados simples entre os designers e o host, em vez de funcionalidades complexas.</span><span class="sxs-lookup"><span data-stu-id="5ec38-124">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="5ec38-125">Itens e serviços de host de EditingContext</span><span class="sxs-lookup"><span data-stu-id="5ec38-125">EditingContext host items and services</span></span>  
 <span data-ttu-id="5ec38-126">. Framework .NET fornece um número de itens e serviços internos acessados com o contexto de edição.</span><span class="sxs-lookup"><span data-stu-id="5ec38-126">The .Net Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="5ec38-127">Itens:</span><span class="sxs-lookup"><span data-stu-id="5ec38-127">Items:</span></span>  
  
-   <span data-ttu-id="5ec38-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Gerencia a lista de assemblies locais referenciados que serão usados dentro de fluxo de trabalho para controles (como o editor de expressão).</span><span class="sxs-lookup"><span data-stu-id="5ec38-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
-   <span data-ttu-id="5ec38-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indica se o designer está em um estado somente leitura.</span><span class="sxs-lookup"><span data-stu-id="5ec38-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indicates whether the designer is in a read-only state.</span></span>  
  
-   <span data-ttu-id="5ec38-130"><xref:System.Activities.Presentation.View.Selection>: Define a coleção de objetos que são selecionados no momento.</span><span class="sxs-lookup"><span data-stu-id="5ec38-130"><xref:System.Activities.Presentation.View.Selection>: Defines the collection of objects that are currently selected.</span></span>  
  
-   <span data-ttu-id="5ec38-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span><span class="sxs-lookup"><span data-stu-id="5ec38-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span></span>  
  
-   <span data-ttu-id="5ec38-132"><xref:System.Activities.Presentation.WorkflowFileItem>: Fornece informações sobre o arquivo que a sessão de edição atual é baseada em sobre.</span><span class="sxs-lookup"><span data-stu-id="5ec38-132"><xref:System.Activities.Presentation.WorkflowFileItem>: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="5ec38-133">Serviços:</span><span class="sxs-lookup"><span data-stu-id="5ec38-133">Services:</span></span>  
  
-   <span data-ttu-id="5ec38-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Permite que as propriedades são adicionadas à instância atual, usando o <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ec38-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
-   <span data-ttu-id="5ec38-135"><xref:System.Activities.Presentation.View.DesignerView>: Permite o acesso às propriedades de tela de designer.</span><span class="sxs-lookup"><span data-stu-id="5ec38-135"><xref:System.Activities.Presentation.View.DesignerView>: Allows access to the properties of the designer canvas.</span></span>  
  
-   <span data-ttu-id="5ec38-136"><xref:System.Activities.Presentation.IActivityToolboxService>: Permite que o conteúdo da caixa de ferramentas são atualizados.</span><span class="sxs-lookup"><span data-stu-id="5ec38-136"><xref:System.Activities.Presentation.IActivityToolboxService>: Allows the contents of the toolbox to be updated.</span></span>  
  
-   <span data-ttu-id="5ec38-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: Usado para integrar comandos de designer (como o menu de contexto) com personalizada forneceu implementações de serviço.</span><span class="sxs-lookup"><span data-stu-id="5ec38-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
-   <span data-ttu-id="5ec38-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Fornece a funcionalidade para o depurador de designer.</span><span class="sxs-lookup"><span data-stu-id="5ec38-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Provides functionality for the designer debugger.</span></span>  
  
-   <span data-ttu-id="5ec38-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: Fornece acesso a caixa de diálogo editor de expressão.</span><span class="sxs-lookup"><span data-stu-id="5ec38-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: Provides access to the Expression Editor dialog.</span></span>  
  
-   <span data-ttu-id="5ec38-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: Fornece o designer com funcionalidade integrado da ajuda.</span><span class="sxs-lookup"><span data-stu-id="5ec38-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: Provides the designer with integrated help functionality.</span></span>  
  
-   <span data-ttu-id="5ec38-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: Fornece acesso aos erros de validação usando o <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ec38-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
-   <span data-ttu-id="5ec38-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Fornece um serviço interno para armazenar e recuperar dados.</span><span class="sxs-lookup"><span data-stu-id="5ec38-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="5ec38-143">Esse serviço é usado internamente pelo. Framework .NET, e não é destinada para uso externo.</span><span class="sxs-lookup"><span data-stu-id="5ec38-143">This service is used internally by the .Net Framework, and is not intended for external use.</span></span>  
  
-   <span data-ttu-id="5ec38-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: Fornece acesso à coleção de erro de carregamento XAML usando o <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ec38-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
-   <span data-ttu-id="5ec38-145"><xref:System.Activities.Presentation.Services.ModelService>: Usado pelo designer para interagir com o modelo de fluxo de trabalho que está sendo editado.</span><span class="sxs-lookup"><span data-stu-id="5ec38-145"><xref:System.Activities.Presentation.Services.ModelService>: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
-   <span data-ttu-id="5ec38-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: Fornece acesso à raiz da árvore modelo de item usando <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ec38-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
-   <span data-ttu-id="5ec38-147"><xref:System.Activities.Presentation.UndoEngine>: Fornece etapas desfaz e refaz a funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="5ec38-147"><xref:System.Activities.Presentation.UndoEngine>: Provides undo and redo functionality.</span></span>  
  
-   <span data-ttu-id="5ec38-148"><xref:System.Activities.Presentation.Services.ViewService>: Mapeia elementos visuais aos itens modelo subjacente.</span><span class="sxs-lookup"><span data-stu-id="5ec38-148"><xref:System.Activities.Presentation.Services.ViewService>: Maps visual elements to underlying model items.</span></span>  
  
-   <span data-ttu-id="5ec38-149"><xref:System.Activities.Presentation.View.ViewStateService>: Armazena estados de exibição para os itens modelo.</span><span class="sxs-lookup"><span data-stu-id="5ec38-149"><xref:System.Activities.Presentation.View.ViewStateService>: Stores view states for model items.</span></span>  
  
-   <span data-ttu-id="5ec38-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: Usado para personalizar o comportamento virtual de interface de usuário do recipiente.</span><span class="sxs-lookup"><span data-stu-id="5ec38-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: Used to customize the virtual container UI behavior.</span></span>  
  
-   <span data-ttu-id="5ec38-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: Usado para registrar e representantes de unregister notificações de eventos.</span><span class="sxs-lookup"><span data-stu-id="5ec38-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="5ec38-152">Também permite que um proprietário da janela é definido.</span><span class="sxs-lookup"><span data-stu-id="5ec38-152">Also allows a window owner to be set.</span></span>