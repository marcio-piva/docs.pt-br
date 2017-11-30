---
title: Como usar o elemento de imagem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 75177c8aae8964ebdc50ae94b2f3a6372991e2c6
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-the-image-element"></a><span data-ttu-id="7c0e1-102">Como usar o elemento de imagem</span><span class="sxs-lookup"><span data-stu-id="7c0e1-102">How to: Use the Image Element</span></span>
<span data-ttu-id="7c0e1-103">Este exemplo mostra como incluir imagens em um aplicativo usando o <xref:System.Windows.Controls.Image> elemento.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-103">This example shows how to include images in an application by using the <xref:System.Windows.Controls.Image> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c0e1-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7c0e1-104">Example</span></span>  
 <span data-ttu-id="7c0e1-105">O exemplo a seguir mostra como renderizar uma imagem de 200 pixels de largura.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-105">The following example shows how to render an image 200 pixels wide.</span></span> <span data-ttu-id="7c0e1-106">Neste exemplo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], a sintaxe de atributo e a de marca de propriedade são usadas para definir a imagem.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-106">In this [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example, both attribute syntax and property tag syntax are used to define the image.</span></span> <span data-ttu-id="7c0e1-107">Para obter mais informações sobre a sintaxe de atributo e a sintaxe de propriedade, consulte [Visão geral de propriedades de dependência](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7c0e1-107">For more information on attribute syntax and property syntax, see [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span> <span data-ttu-id="7c0e1-108">Um <xref:System.Windows.Media.Imaging.BitmapImage> é usado para definir os dados de origem da imagem e é explicitamente definida para o exemplo de sintaxe de marca de propriedade.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-108">A <xref:System.Windows.Media.Imaging.BitmapImage> is used to define the image's source data and is explicitly defined for the property tag syntax example.</span></span> <span data-ttu-id="7c0e1-109">Além disso, o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> do <xref:System.Windows.Media.Imaging.BitmapImage> é definido como a mesma largura que o <xref:System.Windows.FrameworkElement.Width%2A> do <xref:System.Windows.Controls.Image>.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-109">In addition, the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> of the <xref:System.Windows.Media.Imaging.BitmapImage> is set to the same width as the <xref:System.Windows.FrameworkElement.Width%2A> of the <xref:System.Windows.Controls.Image>.</span></span> <span data-ttu-id="7c0e1-110">Isso é feito para garantir que a quantidade mínima de memória seja usada ao renderizar a imagem.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-110">This is done to ensure that the minimum amount of memory is used rendering the image.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c0e1-111">Em geral, se você quiser especificar o tamanho de uma imagem renderizada, especifique apenas o <xref:System.Windows.FrameworkElement.Width%2A> ou <xref:System.Windows.FrameworkElement.Height%2A> , mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-111">In general, if you want to specify the size of a rendered image, specify only the <xref:System.Windows.FrameworkElement.Width%2A> or the <xref:System.Windows.FrameworkElement.Height%2A> but not both.</span></span> <span data-ttu-id="7c0e1-112">Se você especificar apenas um, a taxa de proporção da imagem será preservada.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-112">If you only specify one, the image's aspect ratio is preserved.</span></span> <span data-ttu-id="7c0e1-113">Caso contrário, a imagem pode parecer inesperadamente alongada ou distorcida.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-113">Otherwise, the image may unexpectedly appear stretched or warped.</span></span> <span data-ttu-id="7c0e1-114">Para controlar a imagem do alongando comportamento, use o <xref:System.Windows.Controls.Image.Stretch%2A> e <xref:System.Windows.Controls.Image.StretchDirection%2A> propriedades.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-114">To control the image's stretching behavior, use the <xref:System.Windows.Controls.Image.Stretch%2A> and <xref:System.Windows.Controls.Image.StretchDirection%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c0e1-115">Quando você especifica o tamanho de uma imagem com um <xref:System.Windows.FrameworkElement.Width%2A> ou <xref:System.Windows.FrameworkElement.Height%2A>, você também deve definir o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> ou <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> para o mesmo tamanho respectivo.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-115">When you specify the size of an image with either <xref:System.Windows.FrameworkElement.Width%2A> or <xref:System.Windows.FrameworkElement.Height%2A>, you should also set either <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> or <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> to the same respective size.</span></span>  
  
 <span data-ttu-id="7c0e1-116">O <xref:System.Windows.Controls.Image.Stretch%2A> propriedade determina como a origem da imagem é esticada para preencher o elemento de imagem.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-116">The <xref:System.Windows.Controls.Image.Stretch%2A> property determines how the image source is stretched to fill the image element.</span></span> <span data-ttu-id="7c0e1-117">Para obter mais informações, consulte a enumeração <xref:System.Windows.Media.Stretch>.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-117">For more information, see the <xref:System.Windows.Media.Stretch> enumeration.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="7c0e1-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7c0e1-118">Example</span></span>  
 <span data-ttu-id="7c0e1-119">O exemplo a seguir mostra como renderizar uma imagem de 200 pixels de largura usando código.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-119">The following example shows how to render an image 200 pixels wide using code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c0e1-120">Configuração <xref:System.Windows.Media.Imaging.BitmapImage> propriedades devem ser feitas dentro de um <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> e <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> bloco.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-120">Setting <xref:System.Windows.Media.Imaging.BitmapImage> properties must be done within a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> and <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> block.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="7c0e1-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7c0e1-121">See Also</span></span>  
 [<span data-ttu-id="7c0e1-122">Visão geral da geração de imagens</span><span class="sxs-lookup"><span data-stu-id="7c0e1-122">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)