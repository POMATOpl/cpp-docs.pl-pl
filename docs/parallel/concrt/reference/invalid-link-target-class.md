---
description: Dowiedz się więcej na temat klasy invalid_link_target
title: invalid_link_target — Klasa
ms.date: 11/04/2016
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
ms.openlocfilehash: d080886c3aab0ecc120d4ce13f5f75f2eecfea8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334589"
---
# <a name="invalid_link_target-class"></a>invalid_link_target — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy `link_target` wywoływana jest metoda bloku komunikatów i blok komunikatów nie może połączyć się z obiektem docelowym. Może to wynikać z przekroczenia liczby linków, do których blok komunikatów jest dozwolony, lub próba łączenia określonego elementu docelowego dwa razy do tego samego źródła.

## <a name="syntax"></a>Składnia

```cpp
class invalid_link_target : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[invalid_link_target](#ctor)|Przeciążone. Konstruuje `invalid_link_target` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`invalid_link_target`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="invalid_link_target"></a><a name="ctor"></a> invalid_link_target

Konstruuje `invalid_link_target` obiekt.

```cpp
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Bloki komunikatów asynchronicznych](../../../parallel/concrt/asynchronous-message-blocks.md)
