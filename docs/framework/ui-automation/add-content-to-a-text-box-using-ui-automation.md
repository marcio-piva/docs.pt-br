---
title: Acrescentar Conteúdo a um Text Box Utilizando Automação de IU
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: b8f64b12400098d94d0e25590559877d61519777
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582146"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Acrescentar Conteúdo a um Text Box Utilizando Automação de IU
> [!NOTE]
>  Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>. Para obter as informações mais recentes sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automação de interface do usuário](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tópico contém código de exemplo que demonstra como usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para inserir texto em uma caixa de texto de linha única. Um método alternativo é fornecido para controles de várias linhas e de texto rico onde [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] não é aplicável. Para fins de comparação, o exemplo também demonstra como usar os métodos Win32 para obter os mesmos resultados.  
  
## <a name="example"></a>Exemplo  
 As seguintes etapas de exemplo por meio de uma sequência de controles de texto em um aplicativo de destino. Cada controle de texto é testado para ver se um <xref:System.Windows.Automation.ValuePattern> objeto pode ser obtido usando o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> método. Se o controle de texto der suporte à <xref:System.Windows.Automation.ValuePattern>, o <xref:System.Windows.Automation.ValuePattern.SetValue%2A> método é usado para inserir uma cadeia de caracteres definida pelo usuário no controle de texto. Caso contrário, o <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> método é usado.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>Consulte também
- [Exemplo de inserção de TextPattern de texto](https://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
