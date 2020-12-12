---
description: 'Dowiedz się więcej na temat: platform:: CallbackContext Enumeration'
title: Platform::CallbackContext, wyliczenie
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
ms.openlocfilehash: 36c30b674065f42f7d50a403d1506344ffcfecac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170974"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext, wyliczenie

Określa kontekst wątku, w którym jest wykonywana funkcja wywołania zwrotnego (procedura obsługi zdarzeń).

## <a name="syntax"></a>Składnia

```cpp
enum class CallbackContext {};
```

### <a name="members"></a>Elementy członkowskie

|Kod typu|Opis|
|---------------|-----------------|
|Dowolne|Funkcja wywołania zwrotnego można wykonać w dowolnym kontekście wątku.|
|Ta sama|Funkcja wywołania zwrotnego można wykonać tylko w kontekście wątku, w którym uruchomiono operację asynchroniczną.|

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Metadane:** obiekt platform. winmd
