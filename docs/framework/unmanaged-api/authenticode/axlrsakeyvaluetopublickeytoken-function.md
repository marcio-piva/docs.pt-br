---
title: Função axlrsakeyvaluetopublickeytoken
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a340af9ba196dbcd8618afdd83bcf7e56124bf7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529902"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a>\_Função AxlRSAKeyValueToPublicKeyToken

Converte um Módulo e um Expoente em um token de chave pública com nome forte.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
### <a name="parameters"></a>Parâmetros  
 `pModulusBlob`  
 [in] O blob de módulo codificado na base64 (da \<Modulus > elemento).  Consulte a [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estrutura.  
  
 `pExponentBlob`  
 [in] O blob de expoente codificado de base64 (da \<expoente > elemento). Consulte a [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estrutura.  
  
 `ppwszPublicKeyToken`  
 [out] Um ponteiro para WCHAR * para receber o token de chave pública com codificação hexadecimal.  
  
## <a name="return-value"></a>Valor de retorno  
 `S_OK` se a função for bem-sucedida. Caso contrário, retornará um código de erro.  
  
## <a name="see-also"></a>Consulte também
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
