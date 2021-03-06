---
title: 'Como: Reduzir a cintilação em elementos gráficos com buffers duplos para formulários e controles'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: 96bdaa8882b5f33c68d2a87dd28163c1acd606bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663577"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>Como: Reduzir a cintilação em elementos gráficos com buffers duplos para formulários e controles
O buffer duplo usa um buffer de memória para resolver os problemas de cintilação associados a várias operações de pintura. Quando o buffer duplo estiver habilitado, todas as operações de pintura serão renderizadas primeiro em um buffer de memória, em vez de na superfície de desenho na tela. Depois que todas as operações de pintura estiverem concluídas, o buffer de memória será copiado diretamente para a superfície de desenho associada a ele. Como apenas uma operação de elemento gráfico é executada na tela, a cintilação da imagem associada a operações de pintura complexas é eliminada. Para a maioria dos aplicativos, o buffer duplo padrão fornecido pelo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] oferecerá os melhores resultados. Controles padrão dos Windows Forms são buffers duplos por padrão. Você pode habilitar o buffer duplo padrão em seus formulários e controles criados de duas maneiras. Você pode definir as <xref:System.Windows.Forms.Control.DoubleBuffered%2A> propriedade para `true`, ou você pode chamar o <xref:System.Windows.Forms.Control.SetStyle%2A> método para definir a <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> sinalizador como `true`. Ambos os métodos habilitarão o buffer duplo padrão para o formulário ou controle e fornecerão a renderização de gráficos sem cintilações. Chamar o <xref:System.Windows.Forms.Control.SetStyle%2A> método é recomendado somente para controles personalizados para o qual você tenha escrito o código de renderização.  
  
 Para cenários de buffer duplo mais avançados, como animação ou gerenciamento avançado de memória, você pode implementar sua própria lógica de buffer duplo. Para obter mais informações, confira [Como: Gerenciar elementos gráficos em buffer manualmente](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
### <a name="to-reduce-flicker"></a>Para reduzir a cintilação  
  
-   Defina a propriedade <xref:System.Windows.Forms.Control.DoubleBuffered%2A> como `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- ou -  
  
-   Chame o <xref:System.Windows.Forms.Control.SetStyle%2A> método para definir o <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> sinalizador como `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [Elementos Gráficos em Buffer Duplo](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)
- [Elementos Gráficos e Desenho nos Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
