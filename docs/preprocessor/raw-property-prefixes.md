---
title: raw_property_prefixes — | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1f548c9513a086dd4741a9c61c51acebebb25db
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes
**Określonego języka C++**  
  
 Określa alternatywny prefiksów dla trzech metod właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>Parametry  
 `GetPrefix`  
 Prefiks do zastosowania w przypadku **propget** metody.  
  
 `PutPrefix`  
 Prefiks do zastosowania w przypadku **propput** metody.  
  
 `PutRefPrefix`  
 Prefiks do zastosowania w przypadku **propputref** metody.  
  
## <a name="remarks"></a>Uwagi  
 Domyślnie niskiego poziomu **propget**, **propput**, i **propputref** metody są udostępniane przez funkcje elementu członkowskiego o nazwie z prefiksami **get_**, **put_**, i **putref_** odpowiednio. Tymi prefiksami są zgodne z nazwami używany w plikach nagłówka wygenerowano przez MIDL.  
  
 **KOŃCOWY określonego języka C++**  
  
## <a name="see-also"></a>Zobacz też  
 [atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)