---
title: 'Como: Personalizar a aparência de células no controle DataGridView dos Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 14667854ce4ebad561aa662fcf7d92632cc43530
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515973"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Como: Personalizar a aparência de células no controle DataGridView dos Windows Forms
Você pode personalizar a aparência de qualquer célula manipulando o <xref:System.Windows.Forms.DataGridView> do controle <xref:System.Windows.Forms.DataGridView.CellPainting> eventos. Você pode extrair os <xref:System.Windows.Forms.DataGridView> do controle <xref:System.Drawing.Graphics> da <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> propriedade do <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>. Com isso <xref:System.Drawing.Graphics>, você pode afetar a aparência de todo o <xref:System.Windows.Forms.DataGridView> controle, mas você geralmente desejará afetam apenas a aparência da célula que está atualmente sendo pintada. O <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> propriedade do <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> permite restringir suas operações de pintura da célula que está atualmente sendo pintada.  
  
 No exemplo de código a seguir, você vai pintar todas as células em uma `ContactName` coluna usando o <xref:System.Windows.Forms.DataGridView> esquema de cores do controle. Conteúdo de texto de cada célula é pintado em <xref:System.Drawing.Color.Crimson%2A>, e um retângulo de inserção é desenhado na mesma cor como o <xref:System.Windows.Forms.DataGridView> do controle <xref:System.Windows.Forms.DataGridView.GridColor%2A> propriedade.  
  
## <a name="example"></a>Exemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Um <xref:System.Windows.Forms.DataGridView> controle chamado `dataGridView1` com um `ContactName` coluna como o mostrado na tabela Customers no banco de dados de exemplo Northwind.  
  
-   Referências aos assemblies System, System.Windows.Forms e System.Drawing.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [Personalizando o controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
