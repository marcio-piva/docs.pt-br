---
title: Instâncias por segundo
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: f0797c38a5eb7399817eaf6aad9fb5b6ecbfab89
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519464"
---
# <a name="instances-per-second"></a>Instâncias por segundo
Nome do contador: Instâncias criadas por segundo.  
  
## <a name="description"></a>Descrição  
 Número total de instâncias de serviço criada em um segundo.  
  
 Esse contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cujo valor é calculado usando a fórmula a seguir.  
  
 (N 1 - N 0) / ((1!D 1 - D 0) / F)
