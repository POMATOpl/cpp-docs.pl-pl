---
title: "hash — struktura | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: typeindex/std::hash
dev_langs: C++
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf65a9bd325863afba11021e0bb35223b7e9f6c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="hash-structure"></a>hash — Struktura
Klasa szablon definiuje jej metodę jako zwracanie `val.hash_code()`. Metoda definiuje funkcji skrótu, który jest używany do mapowania wartości typu [type_index —](../standard-library/type-index-class.md) dystrybucji wartości indeksu.  
  
## <a name="syntax"></a>Składnia  
  
```
template <>
struct hash<type_index>  
: public unary_function<type_index, size_t>
 { // hashes a typeinfo object
    size_t operator()(type_index val) const;

 };
```  
  
## <a name="see-also"></a>Zobacz też  
 [\<typeindex >](../standard-library/typeindex.md)



