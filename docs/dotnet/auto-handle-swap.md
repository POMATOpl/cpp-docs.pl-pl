---
title: auto_handle::swap | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_handle::swap
- auto_handle.swap
- auto_handle::swap
- msclr..auto_handle.swap
dev_langs:
- C++
helpviewer_keywords:
- auto_handle::swap
ms.assetid: 3ebf82d7-9b69-4a72-a22d-69b4f640f9b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 87a0a59197a7ebe22c5419e992f681787cd3ea7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103921"
---
# <a name="autohandleswap"></a>auto_handle::swap
Zamienia obiekty z innym `auto_handle`.  
  
## <a name="syntax"></a>Składnia  
  
```  
void swap(  
   auto_handle<_element_type> % _right  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `_right`  
 `auto_handle` Umożliwiające wymiany obiektów.  
  
## <a name="example"></a>Przykład  
  
```  
// msl_auto_handle_swap.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1 = "string one";  
   auto_handle<String> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   s1.swap( s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
```Output  
s1 = 'string one', s2 = 'string two'  
s1 = 'string two', s2 = 'string one'  
```  
  
## <a name="requirements"></a>Wymagania  
 **Plik nagłówka** \<msclr\auto_handle.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Zobacz też  
 [auto_handle — członkowie](../dotnet/auto-handle-members.md)   
 [Funkcja swap (auto_handle)](../dotnet/swap-function-auto-handle.md)