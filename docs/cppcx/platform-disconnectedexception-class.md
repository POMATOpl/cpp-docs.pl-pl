---
description: 'Dowiedz się więcej na temat: platform::D isconnectobject Class'
title: Platforma::D isconnectobject Class
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::DisconnectedException
- VCCORLIB/Platform::DisconnectedException::DisconnectedException
helpviewer_keywords:
- Platform::DisconnectedException
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
ms.openlocfilehash: 6ccfedc143d0245582c7c1f95110207d583949fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195323"
---
# <a name="platformdisconnectedexception-class"></a>Platforma::D isconnectobject Class

Zgłaszany, gdy obiekt serwera proxy COM próbuje odwołać się do serwera COM, który już nie istnieje

## <a name="syntax"></a>Składnia

```
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Uwagi

Gdy klasa A odwołuje się do innej klasy (klasy B), która znajduje się w oddzielnym procesie, Klasa A wymaga obiektu proxy do komunikacji z nieprocesowym serwerem COM, który zawiera klasę B. Czasami serwer może wykroczyć ilość pamięci bez znajomości klasy. W takim przypadku zostanie zgłoszony wyjątek RPC_E_DISCONNECTED i zostanie on przetłumaczony na platformę::D isconnectexception. Taki scenariusz występuje, gdy źródło zdarzenia wywołuje delegata, który został do niego przekazano, ale delegat został zniszczony w pewnym momencie po zasubskrybowaniu zdarzenia. W takim przypadku Źródło zdarzenia usuwa tego delegata z listy wywołań.

Aby uzyskać więcej informacji, zobacz Klasa [COMException](../cppcx/platform-comexception-class.md) .

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Metadane:** obiekt platform. winmd

## <a name="see-also"></a>Zobacz też

[Platform:: COMException, Klasa](../cppcx/platform-comexception-class.md)
