---
title: ComPtr::ptr_, składowa danych | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ptr_
dev_langs:
- C++
helpviewer_keywords:
- ptr_ data member
ms.assetid: c84f9dda-8ff9-422d-91f2-1a41206bf9ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c1e1a8bc076144d80358191cd8eca209057b869
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599180"
---
# <a name="comptrptr-data-member"></a>ComPtr::ptr_ — Członek danych

Zawiera wskaźnik do interfejsu, który jest skojarzony z i zarządzanego przez to **ComPtr**.

## <a name="syntax"></a>Składnia

```cpp
InterfaceType *ptr_;
```

## <a name="remarks"></a>Uwagi

**ptr_ — element** jest elementem członkowskim wewnętrznego, chronionych danych.

## <a name="requirements"></a>Wymagania

**Nagłówek:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Zobacz też

[ComPtr, klasa](../windows/comptr-class.md)