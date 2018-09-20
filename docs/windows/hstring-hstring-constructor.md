---
title: HString::HString, Konstruktor | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59ec7c1635b825cc300e28e5c02e2a3864a6c123
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442256"
---
# <a name="hstringhstring-constructor"></a>HString::HString — Konstruktor

Inicjuje nowe wystąpienie klasy **HString** klasy.

## <a name="syntax"></a>Składnia

```cpp
HString(HSTRING hstr = nullptr) throw();
HString(HString&& other) throw();
```

#### <a name="parameters"></a>Parametry

*HSTR*<br/>
Dojścia HSTRING.

*other*<br/>
Istniejące **HString** obiektu.

## <a name="remarks"></a>Uwagi

Pierwszy Konstruktor inicjuje nową **HString** obiektu, który jest pusty.

Drugi Konstruktor inicjuje nowe **HString** obiektu do wartości istniejących *innych* parametru i następnie niszczy *innych* parametru.

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers.h

**Namespace:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>Zobacz też

[HString, klasa](../windows/hstring-class.md)