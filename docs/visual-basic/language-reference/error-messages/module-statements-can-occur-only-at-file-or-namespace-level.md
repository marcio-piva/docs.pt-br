---
title: '&#39;Módulo&#39; instruções podem ocorrer apenas no nível de namespace ou arquivo'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bdbf8df5942e9df4b9696aeea4e3492121efe21a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746306"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a>&#39;Módulo&#39; instruções podem ocorrer apenas no nível de namespace ou arquivo
`Module` as instruções devem aparecer na parte superior do seu arquivo de origem imediatamente após `Option` e `Imports` instruções, atributos globais e declarações de namespace, mas antes de todas as outras declarações.  
  
 **ID do erro:** BC30617  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
-   Mover o `Module` instrução na parte superior do seu arquivo de origem ou de declaração de namespace.  
  
## <a name="see-also"></a>Consulte também
- [Instrução Module](../../../visual-basic/language-reference/statements/module-statement.md)
