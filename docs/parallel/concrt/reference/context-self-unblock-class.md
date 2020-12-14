---
description: Dowiedz się więcej na temat klasy context_self_unblock
title: context_self_unblock — Klasa
ms.date: 11/04/2016
f1_keywords:
- context_self_unblock
- CONCRT/concurrency::context_self_unblock
- CONCRT/concurrency::context_self_unblock::context_self_unblock
helpviewer_keywords:
- context_self_unblock class
ms.assetid: 9601cd28-4f40-4c2e-89ab-747068956331
ms.openlocfilehash: 51fae67530e2836b92a6ab7a13e2b136f1d438c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188979"
---
# <a name="context_self_unblock-class"></a>context_self_unblock — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy `Unblock` Metoda `Context` obiektu jest wywoływana z tego samego kontekstu. Spowoduje to wskazanie próby odblokowania przez dany kontekst.

## <a name="syntax"></a>Składnia

```cpp
class context_self_unblock : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[context_self_unblock](#ctor)|Przeciążone. Konstruuje `context_self_unblock` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`context_self_unblock`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="context_self_unblock"></a><a name="ctor"></a> context_self_unblock

Konstruuje `context_self_unblock` obiekt.

```cpp
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

context_self_unblock() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
