---
description: Dowiedz się więcej na temat klasy context_unblock_unbalanced
title: context_unblock_unbalanced — Klasa
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: d262ff52a675935f95664d2f7ddd69aa159aa0bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188966"
---
# <a name="context_unblock_unbalanced-class"></a>context_unblock_unbalanced — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy wywołania `Block` `Unblock` metod i `Context` obiektu nie są prawidłowo sparowane.

## <a name="syntax"></a>Składnia

```cpp
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|Przeciążone. Konstruuje `context_unblock_unbalanced` obiekt.|

## <a name="remarks"></a>Uwagi

Wywołania `Block` `Unblock` metod i `Context` obiektu muszą zawsze być prawidłowo sparowane. Środowisko uruchomieniowe współbieżności umożliwia wykonywanie operacji w dowolnej kolejności. Na przykład wywołanie `Block` może następować po wywołaniu `Unblock` lub na odwrót. Ten wyjątek zostałby wygenerowany, jeśli na przykład dwa wywołania `Unblock` metody zostały wykonane w wierszu, na `Context` obiekcie, który nie został zablokowany.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="context_unblock_unbalanced"></a><a name="ctor"></a> context_unblock_unbalanced

Konstruuje `context_unblock_unbalanced` obiekt.

```cpp
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
