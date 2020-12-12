---
description: 'Dowiedz się więcej o: platform::D elegata Class'
title: Platforma::D Klasa elegata
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
ms.openlocfilehash: 58baedf595d3ee8d9cc4975e787193abf522233c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176109"
---
# <a name="platformdelegate-class"></a>Platforma::D Klasa elegata

Reprezentuje obiekt Function.

## <a name="syntax"></a>Składnia

```cpp
public delegate void delegate_name();
```

### <a name="members"></a>Elementy członkowskie

Klasa delegat ma metody Equals (), GetHashCode () i ToString () pochodne od [klasy platform:: Object](../cppcx/platform-object-class.md).

### <a name="remarks"></a>Uwagi

Użyj słowa kluczowego [delegata](../extensions/delegate-cpp-component-extensions.md) , aby utworzyć delegatów; nie używaj elegata platformy:D: jawnie. Aby uzyskać więcej informacji, zobacz [delegats](../cppcx/delegates-c-cx.md). Aby zapoznać się z przykładem tworzenia i używania delegata, zobacz [Tworzenie składników Środowisko wykonawcze systemu Windows w języku C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Metadane:** obiekt platform. winmd

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw platformy](../cppcx/platform-namespace-c-cx.md)
