---
title: 'Como: Criar imagens em miniatura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: fd5e0b5341a712f25f9d41670f9b3ede5414dda4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497005"
---
# <a name="how-to-create-thumbnail-images"></a>Como: Criar imagens em miniatura
Uma imagem em miniatura é uma versão pequena de uma imagem. Você pode criar uma imagem em miniatura chamando o <xref:System.Drawing.Image.GetThumbnailImage%2A> método de um <xref:System.Drawing.Image> objeto.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir constrói um <xref:System.Drawing.Image> objeto de um arquivo JPG. A imagem original tem uma largura de 640 pixels e uma altura de 479 pixels. O código cria uma imagem em miniatura que tem uma largura de 100 pixels e uma altura de 100 pixels.  
  
 A ilustração a seguir mostra a imagem em miniatura.  
  
 ![Thumbnail Image](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  Neste exemplo, um método de retorno de chamada é declarado, mas nunca usado. Isso dá suporte a todas as versões do GDI+.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 O exemplo anterior foi projetado para uso com o Windows Forms e requer <xref:System.Windows.Forms.PaintEventArgs> `e`, que é um parâmetro do <xref:System.Windows.Forms.Control.Paint> manipulador de eventos. Para executar o exemplo, siga estas etapas:  
  
1.  Criar um novo aplicativo Windows Form.  
  
2.  Adicione o código de exemplo ao formulário.  
  
3.  Criar um manipulador para o formulário <xref:System.Windows.Forms.Control.Paint> evento  
  
4.  No <xref:System.Windows.Forms.Control.Paint> manipulador, a chamada a `GetThumbnail` método e passar `e` para <xref:System.Windows.Forms.PaintEventArgs>.  
  
5.  Localize um arquivo de imagem do qual deseja criar uma miniatura.  
  
6.  No método `GetThumbnail`, especifique o caminho e nome do arquivo para sua imagem.  
  
7.  Pressione F5 para executar o exemplo.  
  
     Uma imagem em miniatura de 100 por 100 aparece no formulário.  
  
## <a name="see-also"></a>Consulte também
- [Imagens, bitmaps e metarquivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [Trabalhando com Imagens, Bitmaps, Ícones e Metarquivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
