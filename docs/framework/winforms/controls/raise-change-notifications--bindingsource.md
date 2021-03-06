---
title: 'Como: Gerar notificações de alteração usando um BindingSource e a Interface INotifyPropertyChanged'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: cf6f39154b7b896a835bda7f946134fbff8dbe17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543952"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>Como: Gerar notificações de alteração usando um BindingSource e a Interface INotifyPropertyChanged
O <xref:System.Windows.Forms.BindingSource> componente detectará automaticamente as alterações em uma fonte de dados quando o tipo contido de fonte de dados implementa a <xref:System.ComponentModel.INotifyPropertyChanged> interface e gera <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos quando um valor da propriedade é alterado. Isso é útil porque os controles associados ao <xref:System.Windows.Forms.BindingSource> , em seguida, atualizará automaticamente como sendo a alteração de valores de fonte de dados.  
  
> [!NOTE]
>  Se a fonte de dados implementa <xref:System.ComponentModel.INotifyPropertyChanged> e você estiver executando operações assíncronas, você não deve fazer alterações à fonte de dados em um thread em segundo plano. Em vez disso, você deve ler os dados em um thread em segundo plano e mesclar os dados em uma lista no thread da interface do usuário.  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir demonstra uma implementação simples dos <xref:System.ComponentModel.INotifyPropertyChanged> interface. Ele também mostra como o <xref:System.Windows.Forms.BindingSource> passa automaticamente uma alteração de fonte de dados para um limite controlar quando o <xref:System.Windows.Forms.BindingSource> está associado a uma lista da <xref:System.ComponentModel.INotifyPropertyChanged> tipo.  
  
 Se você usar o atributo `CallerMemberName`, chamadas para o método `NotifyPropertyChanged` não precisarão especificar o nome da propriedade como um argumento de cadeia de caracteres. Para obter mais informações, consulte [Informações do chamador](https://msdn.microsoft.com/library/9cb2b8c0-c4f6-44b8-9c90-38948455b373).  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Referências aos assemblies System, System.Data, System.Drawing e System.Windows.Forms.  
  
 Para obter informações sobre como compilar este exemplo da linha de comando para o Visual Basic ou Visual c#, consulte [compilando da linha de comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [criação de linha de comando com csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Você também pode criar este exemplo no Visual Studio colando o código em um novo projeto. Consulte também [como: Compilar e executar um exemplo de código completa do Windows Forms usando o Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb129228(v=vs.100)).  
  
## <a name="see-also"></a>Consulte também
- <xref:System.ComponentModel.INotifyPropertyChanged>
- [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [Como: Gerar notificações de alteração usando o método BindingSource ResetItem](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
