---
description: 'Dowiedz się więcej na temat: platform:: Metadata Namespace'
title: 'Platform:: Metadata — przestrzeń nazw'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata
helpviewer_keywords:
- Platform::Metadata Namespace
ms.assetid: e3e114d8-a4b0-47f0-865a-9ce9d7212e86
ms.openlocfilehash: 5dd699c0136c4ee37462dd22f9ee27bec345e8b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308396"
---
# <a name="platformmetadata-namespace"></a>Platform:: Metadata — przestrzeń nazw

Ta przestrzeń nazw zawiera atrybuty, które modyfikują deklaracje typów.

## <a name="syntax"></a>Składnia

```cpp
namespace Platform {
   namespace Metadata {
}}
```

### <a name="members"></a>Elementy członkowskie

Mimo że ta przestrzeń nazw jest przeznaczona do użytku wewnętrznego, przeglądarki mogą wyświetlać następujące elementy członkowskie tej przestrzeni nazw.

|Nazwa|Dyskusji|
|----------|------------|
|Atrybut|Klasa bazowa dla atrybutów.|
|[Platform:: Metadata::D atrybut efaultMemberAttribute](../cppcx/platform-metadata-defaultmemberattribute-attribute.md)|Wskazuje preferowaną funkcję do wywołania między kilkoma możliwymi przeciążonymi funkcjami.|
|[Platform:: Metadata:: FlagsAttribute, atrybut](../cppcx/platform-metadata-flagsattribute-attribute.md) Znaczników|Deklaruje Wyliczenie jako Wyliczenie pól bitowych.<br /><br /> Poniższy przykład pokazuje, jak zastosować `Flags` atrybut Wyliczenie.<br /><br /> `[Flags] enum class MyEnumeration { enumA = 1, enumB = 2, enumC = 3}`|
|[Platform:: Metadata:: RuntimeClassNameAttribute](../cppcx/platform-metadata-runtimeclassname.md)|Zapewnia, że prywatna Klasa referencyjna ma prawidłową nazwę klasy środowiska uruchomieniowego.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`Platform`

### <a name="requirements"></a>Wymagania

**Metadane:** obiekt platform. winmd

**Przestrzeń nazw:** Platform:: Metadata

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw platformy](platform-namespace-c-cx.md)
