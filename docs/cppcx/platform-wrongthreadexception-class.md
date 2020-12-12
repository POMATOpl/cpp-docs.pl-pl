---
description: 'Dowiedz się więcej na temat: platform:: WrongThreadException, Klasa'
title: 'Platform:: WrongThreadException, Klasa'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WrongThreadException
- VCCORLIB/Platform::WrongThreadException::WrongThreadException
helpviewer_keywords:
- Platform::WrongThreadException
ms.assetid: c193f97e-0392-4535-a4c4-0711e4e4a836
ms.openlocfilehash: a7fbaed7766a3928ca24d56f5233c38d9298d466
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307733"
---
# <a name="platformwrongthreadexception-class"></a>Platform:: WrongThreadException, Klasa

Zgłaszany, gdy wątek wywołuje metodę wskaźnika interfejsu dla obiektu serwera proxy, który nie należy do apartamentu wątku.

## <a name="syntax"></a>Składnia

```cpp
public ref class WrongThreadException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [COMException](../cppcx/platform-comexception-class.md).

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Metadane:** obiekt platform. winmd

## <a name="see-also"></a>Zobacz też

[Platform:: COMException, Klasa](../cppcx/platform-comexception-class.md)
