---
title: "Herança visual dos Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inheritance
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 857eb737-3602-4d49-bd8b-f70d33ace345
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c9d53cf3e54e4a0a0de3207ea59a67f3493f5e88
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="windows-forms-visual-inheritance"></a><span data-ttu-id="77e80-102">Herança visual dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="77e80-102">Windows Forms Visual Inheritance</span></span>
<span data-ttu-id="77e80-103">Às vezes decidimos que um projeto precisa de um formulário semelhante a outro criado em um projeto anterior.</span><span class="sxs-lookup"><span data-stu-id="77e80-103">Occasionally, you may decide that a project calls for a form similar to one that you have created in a previous project.</span></span> <span data-ttu-id="77e80-104">Ou talvez queiramos criar um formulário básico, com configurações como marca-d'água ou determinado controle de layout que usaremos novamente em um projeto, com cada iteração contendo modificações ao modelo de formulário original.</span><span class="sxs-lookup"><span data-stu-id="77e80-104">Or, you may want to create a basic form with settings such as a watermark or certain control layout that you will then use again within a project, with each iteration containing modifications to the original form template.</span></span> <span data-ttu-id="77e80-105">A herança de formulário permite criar um formulário base, herdar dele, fazer modificações e ao mesmo tempo preserva quaisquer configurações originais necessárias.</span><span class="sxs-lookup"><span data-stu-id="77e80-105">Form inheritance enables you to create a base form and then inherit from it and make modifications while preserving whatever original settings you need.</span></span>  
  
 <span data-ttu-id="77e80-106">É possível criar formulários de classe derivada de forma programática ou usando o selecionador de herança visual.</span><span class="sxs-lookup"><span data-stu-id="77e80-106">You can create derived-class forms programmatically or by using the Visual Inheritance picker.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77e80-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="77e80-107">In This Section</span></span>  
 [<span data-ttu-id="77e80-108">Como Herdar Windows Forms</span><span class="sxs-lookup"><span data-stu-id="77e80-108">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 <span data-ttu-id="77e80-109">Fornece instruções para criar formulários herdados em código.</span><span class="sxs-lookup"><span data-stu-id="77e80-109">Gives directions for creating inherited forms in code.</span></span>  
  
 [<span data-ttu-id="77e80-110">Como Herdar Formulários Usando a Caixa de Diálogo Selecionador de Herança</span><span class="sxs-lookup"><span data-stu-id="77e80-110">How to: Inherit Forms Using the Inheritance Picker Dialog Box</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)  
 <span data-ttu-id="77e80-111">Fornece instruções para criar formulários herdados com o selecionador de herança.</span><span class="sxs-lookup"><span data-stu-id="77e80-111">Gives directions for creating inherited forms with the Inheritance Picker.</span></span>  
  
 [<span data-ttu-id="77e80-112">Efeitos da Modificação da Aparência de um Formulário Base</span><span class="sxs-lookup"><span data-stu-id="77e80-112">Effects of Modifying a Base Form's Appearance</span></span>](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 <span data-ttu-id="77e80-113">Fornece instruções para alterar os controles de um formulário base e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="77e80-113">Gives directions for changing a base form's controls and their properties.</span></span>  
  
 [<span data-ttu-id="77e80-114">Instruções passo a passo: demonstrando herança visual</span><span class="sxs-lookup"><span data-stu-id="77e80-114">Walkthrough: Demonstrating Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 <span data-ttu-id="77e80-115">Descreve como criar um Windows Form base e compilá-lo em uma biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="77e80-115">Describes how to create a base Windows Form and compile it into a class library.</span></span> <span data-ttu-id="77e80-116">A biblioteca de classes será importada em outro projeto e criará um novo formulário que herda do formulário base.</span><span class="sxs-lookup"><span data-stu-id="77e80-116">You will import this class library into another project, and create a new form that inherits from the base form.</span></span>  
  
 [<span data-ttu-id="77e80-117">Como Usar os Modificadores e as Propriedades GenerateMember</span><span class="sxs-lookup"><span data-stu-id="77e80-117">How to: Use the Modifiers and GenerateMember Properties</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-the-modifiers-and-generatemember-properties.md)  
 <span data-ttu-id="77e80-118">Fornece instruções para usar as propriedades `GenerateMember` e `Modifiers`, que são relevantes quando o Designer de Formulários do Windows gera uma variável de membro para um componente.</span><span class="sxs-lookup"><span data-stu-id="77e80-118">Gives directions for using the `GenerateMember` and `Modifiers` properties, which are relevant when the Windows Forms Designer generates a member variable for a component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="77e80-119">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="77e80-119">Related Sections</span></span>  
 [<span data-ttu-id="77e80-120">Noções básicas de herança (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77e80-120">Inheritance basics (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 <span data-ttu-id="77e80-121">Descreve como definir classes Visual Basic que servem como base para outras classes.</span><span class="sxs-lookup"><span data-stu-id="77e80-121">Describes how to define Visual Basic classes that serve as the basis for other classes.</span></span>  
  
 [<span data-ttu-id="77e80-122">class</span><span class="sxs-lookup"><span data-stu-id="77e80-122">class</span></span>](~/docs/csharp/language-reference/keywords/class.md)  
 <span data-ttu-id="77e80-123">Descreve a abordagem C# de classes, na qual a herança simples é permitida.</span><span class="sxs-lookup"><span data-stu-id="77e80-123">Describes the C# approach of classes, in which single inheritance is allowed.</span></span>  
  
 [<span data-ttu-id="77e80-124">Solucionando problemas de manipuladores de eventos herdados no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77e80-124">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="77e80-125">Lista problemas comuns que ocorrem com os manipuladores de eventos em componentes herdados</span><span class="sxs-lookup"><span data-stu-id="77e80-125">Lists common issues that arise with event handlers in inherited components</span></span>