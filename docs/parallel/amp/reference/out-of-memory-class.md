---
description: Dowiedz się więcej na temat klasy out_of_memory
title: out_of_memory — Klasa
ms.date: 11/04/2016
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
ms.openlocfilehash: bb7ba1db5be5921111b1fba2e12ea5cf6a5bea1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329923"
---
# <a name="out_of_memory-class"></a>out_of_memory — Klasa

Wyjątek, który jest generowany, gdy metoda nie powiedzie się z powodu braku pamięci systemowej lub urządzenia.

## <a name="syntax"></a>Składnia

```cpp
class out_of_memory : public runtime_exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor out_of_memory](#ctor)|Inicjuje nowe wystąpienie klasy `out_of_memory`.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amprt. h

**Przestrzeń nazw:** Współbieżności

## <a name="out_of_memory"></a><a name="ctor"></a> out_of_memory

Inicjuje nowe wystąpienie klasy.

### <a name="syntax"></a>Składnia

```cpp
explicit out_of_memory(
    const char * _Message ) throw();

out_of_memory () throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opis błędu.

### <a name="return-value"></a>Wartość zwracana

Nowe wystąpienie `out_of_memory` klasy.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
