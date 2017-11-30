---
title: "Como definir uma duração para uma animação"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9560e9d0a2809ae8f55a060eaec3b271539d5f94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="a8198-102">Como definir uma duração para uma animação</span><span class="sxs-lookup"><span data-stu-id="a8198-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="a8198-103">Um <xref:System.Windows.Media.Animation.Timeline> representa um segmento de tempo e o comprimento do segmento são determinados pela linha do tempo <xref:System.Windows.Duration>.</span><span class="sxs-lookup"><span data-stu-id="a8198-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="a8198-104">Quando um <xref:System.Windows.Media.Animation.Timeline> atinge o final de sua duração, sua execução é interrompida.</span><span class="sxs-lookup"><span data-stu-id="a8198-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="a8198-105">Se o <xref:System.Windows.Media.Animation.Timeline> possui linhas filho, são interrompidas também.</span><span class="sxs-lookup"><span data-stu-id="a8198-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="a8198-106">No caso de uma animação, a <xref:System.Windows.Duration> Especifica quanto tempo a animação leva para fazer a transição do seu valor inicial ao seu valor final.</span><span class="sxs-lookup"><span data-stu-id="a8198-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="a8198-107">Você pode especificar um <xref:System.Windows.Duration> com um tempo específico, finito ou os valores especiais <xref:System.Windows.Duration.Automatic%2A> ou <xref:System.Windows.Duration.Forever%2A>.</span><span class="sxs-lookup"><span data-stu-id="a8198-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="a8198-108">A duração de uma animação sempre deve ser um valor temporal, porque uma animação deve sempre ter uma duração finita definida, caso contrário, a animação não saberia como fazer a transição entre seus valores de destino.</span><span class="sxs-lookup"><span data-stu-id="a8198-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="a8198-109">Cronogramas contêiner (<xref:System.Windows.Media.Animation.TimelineGroup> objetos), como <xref:System.Windows.Media.Animation.Storyboard> e <xref:System.Windows.Media.Animation.ParallelTimeline>, ter uma duração padrão de <xref:System.Windows.Duration.Automatic%2A>, o que significa que elas automaticamente terminam quando seu último filho termina de executar.</span><span class="sxs-lookup"><span data-stu-id="a8198-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="a8198-110">No seguinte exemplo, a largura, altura e preenchimento de cor de um <xref:System.Windows.Shapes.Rectangle> é animado.</span><span class="sxs-lookup"><span data-stu-id="a8198-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="a8198-111">As durações são definidas na animação e linhas de tempo do contêiner resultando em efeitos de animação, incluindo o controle da velocidade percebida de uma animação e a substituição da duração das linhas de tempo filho pela linha de tempo do contêiner.</span><span class="sxs-lookup"><span data-stu-id="a8198-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8198-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a8198-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a8198-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a8198-113">See Also</span></span>  
 <xref:System.Windows.Duration>  
 [<span data-ttu-id="a8198-114">Visão geral da animação</span><span class="sxs-lookup"><span data-stu-id="a8198-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)