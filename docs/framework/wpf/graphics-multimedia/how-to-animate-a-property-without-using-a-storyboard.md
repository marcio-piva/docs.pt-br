---
title: 'Como: Animar uma propriedade sem usar um storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: f2cb3533010579f912da62cb2f7fe28d982890c7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678129"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a>Como: Animar uma propriedade sem usar um storyboard
Este exemplo mostra uma maneira de aplicar uma animação a uma propriedade sem usar um <xref:System.Windows.Media.Animation.Storyboard>.  
  
> [!NOTE]
>  Essa funcionalidade não está disponível no [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Para obter informações sobre como animar uma propriedade em [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], veja [Animar uma propriedade usando um storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Para aplicar um animação local a uma propriedade, use o <xref:System.Windows.UIElement.BeginAnimation%2A> método. Esse método usa dois parâmetros: um <xref:System.Windows.DependencyProperty> que especifica a propriedade a ser animada e a animação a ser aplicado a essa propriedade.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como animar a cor de plano de fundo e a largura de um <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 Uma variedade de classes de animação no <xref:System.Windows.Media.Animation> namespace existe para diferentes tipos de propriedades de animação. Para obter mais informações sobre propriedades de animação, consulte [Visão geral da animação](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Para obter mais informações sobre propriedades de dependência (o tipo de propriedades mostradas neste exemplo) e suas funcionalidades, veja [Visão geral das propriedades de dependência](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Há outras maneiras de animar sem usar <xref:System.Windows.Media.Animation.Storyboard> objetos; para obter mais informações, consulte [visão geral das técnicas de animação de propriedade](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Visão geral das técnicas de animação da propriedade](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
- [Visão geral da animação](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
