---
title: Platform::CallbackContext, wyliczenie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b80fe7749fdb2f91e300cff007c01001edfa557
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755115"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext, wyliczenie
Określa kontekst wątku, w którym wykonuje funkcję wywołania zwrotnego (program obsługi zdarzeń).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>Elementy członkowskie  
  
|Kod typu|Opis|  
|---------------|-----------------|  
|Wszystkie|Funkcja wywołania zwrotnego można wykonywać w dowolnym kontekście wątku.|  
|Ten sam|Funkcja wywołania zwrotnego można wykonać w kontekście wątku, który uruchomił operację asynchroniczną.|  
  
### <a name="requirements"></a>Wymagania  
 **Minimalna obsługiwana klienta:** systemu Windows 8  
  
 **Minimalna obsługiwana serwera:** systemu Windows Server 2012  
  
 **Namespace:** platformy  
  
 **Metadane:** platform.winmd