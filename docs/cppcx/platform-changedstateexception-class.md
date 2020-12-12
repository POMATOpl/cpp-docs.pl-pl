---
description: 'Dowiedz się więcej na temat: platform:: ChangedStateException, Klasa'
title: 'Platform:: ChangedStateException, Klasa'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ChangedStateException
- VCCORLIB/Platform::ChangedStateException::ChangedStateException
helpviewer_keywords:
- Platform::ChangedStateException
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
ms.openlocfilehash: baabf54cacfc4dd03256b569fb868c402ea98a97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284034"
---
# <a name="platformchangedstateexception-class"></a>Platform:: ChangedStateException, Klasa

Zgłaszany, gdy zmienił się stan wewnętrzny obiektu, co unieważnia wyniki metody.

## <a name="syntax"></a>Składnia

```cpp
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Uwagi

Przykładem, gdy ten wyjątek jest zgłaszany, jest wywoływanie metod iteratora kolekcji lub widoku kolekcji po zmianie kolekcji nadrzędnej, unieważnienie wyników metody.

Aby uzyskać więcej informacji, zobacz Klasa [COMException](../cppcx/platform-comexception-class.md) .

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Metadane:** obiekt platform. winmd

## <a name="see-also"></a>Zobacz też

[Platform:: COMException, Klasa](../cppcx/platform-comexception-class.md)
