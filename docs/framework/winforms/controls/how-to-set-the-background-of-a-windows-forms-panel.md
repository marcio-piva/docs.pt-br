---
title: 'Como: Definir plano de fundo de um painel do Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: 1c4eadaadf561e127ac2eaa87f62aea4e1dc7ea4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636073"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Como: Definir plano de fundo de um painel do Windows Forms
Um Windows Forms <xref:System.Windows.Forms.Panel> controle pode exibir uma cor de fundo e uma imagem de plano de fundo. O <xref:System.Windows.Forms.Control.BackColor%2A> propriedade define a cor de plano de fundo de controles contidos, como rótulos e botões de opção. Se o <xref:System.Windows.Forms.Control.BackgroundImage%2A> não está definida, o <xref:System.Windows.Forms.Control.BackColor%2A> seleção preencherá o painel inteiro. Se o <xref:System.Windows.Forms.Control.BackgroundImage%2A> estiver definida, a imagem será exibida por trás de controles contidos.  
  
### <a name="to-set-the-background-programmatically"></a>Definir o plano de fundo de maneira programática  
  
1.  Definir o painel <xref:System.Windows.Forms.Control.BackColor%2A> propriedade para um valor do tipo <xref:System.Drawing.Color?displayProperty=nameWithType>.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2.  Definir o painel <xref:System.Windows.Forms.Control.BackgroundImage%2A> propriedade usando o <xref:System.Drawing.Image.FromFile%2A> método o <xref:System.Drawing.Image?displayProperty=nameWithType> classe.  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Controle de painel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)
- [Visão geral do controle Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)
