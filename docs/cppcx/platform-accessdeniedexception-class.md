---
description: 'Dowiedz się więcej na temat: platform:: AccessDeniedException, Klasa'
title: 'Platform:: AccessDeniedException, Klasa'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
ms.openlocfilehash: 2dd1e543093000521bceb0abed128a1dac27a6e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276793"
---
# <a name="platformaccessdeniedexception-class"></a>Platform:: AccessDeniedException, Klasa

Zgłaszany w przypadku odmowy dostępu do zasobu lub funkcji.

## <a name="syntax"></a>Składnia

```cpp
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable
```

### <a name="remarks"></a>Uwagi

Jeśli osiągnięto ten wyjątek, upewnij się, że zażądano odpowiedniej możliwości i przeprowadzono wymagane deklaracje w manifeście pakietu aplikacji. Aby uzyskać więcej informacji, zobacz Klasa [COMException](../cppcx/platform-comexception-class.md) .

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Metadane:** obiekt platform. winmd

## <a name="see-also"></a>Zobacz też

[Platform:: COMException, Klasa](../cppcx/platform-comexception-class.md)
