---
description: 'Dowiedz się więcej o: punkty zaczepienia powiadomień'
title: Punkty zaczepienia powiadomień
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
ms.openlocfilehash: 716d2b31faa71c77ec436662ce00368d15afc4b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209753"
---
# <a name="notification-hooks"></a>Punkty zaczepienia powiadomień

Punkty zaczepienia powiadomień są wywoływane tuż przed wykonaniem następujących akcji w procedurze pomocnika:

- Zachowane dojście do biblioteki jest sprawdzane w celu sprawdzenia, czy zostało już załadowane.

- Funkcja **LoadLibrary** jest wywoływana w celu próby ZAŁADOWANIA biblioteki DLL.

- Wywołanie **GetProcAddress** jest wywoływane w celu uzyskania adresu procedury.

- Wróć do opóźnienia importowania thunk.

Punkt zaczepienia powiadomienia jest włączony:

- Dostarczając nową definicję **__pfnDliNotifyHook2** wskaźnika, która została zainicjowana, aby wskazywała własną funkcję, która otrzymuje powiadomienia.

   \-oraz

- Ustawiając **__pfnDliNotifyHook2** wskaźnika na funkcję haka przed dowolnymi wywołaniami do biblioteki DLL, które program jest opóźniony ładowania.

Jeśli powiadomienie jest **dliStartProcessing**, funkcja Hook może zwrócić:

- NULL

   Domyślny pomocnik obsługuje ładowanie biblioteki DLL. Jest to przydatne do wywoływania wyłącznie w celach informacyjnych.

- wskaźnik funkcji

   Pomiń domyślną obsługę ładowania opóźnienia. Pozwala to na dostarczenie własnego programu obsługi obciążenia.

Jeśli powiadomienie jest **dliNotePreLoadLibrary**, funkcja Hook może zwrócić:

- 0, jeśli tylko chcą otrzymywać powiadomienia informacyjne.

- HMODULE dla załadowanej biblioteki DLL, jeśli załadowana sama Biblioteka DLL.

Jeśli powiadomienie jest **dliNotePreGetProcAddress**, funkcja Hook może zwrócić:

- 0, jeśli tylko chcą otrzymywać powiadomienia informacyjne.

- Adres zaimportowanej funkcji, jeśli funkcja Hook Pobiera adres.

Jeśli powiadomienie jest **dliNoteEndProcessing**, zwracana wartość funkcji Hook jest ignorowana.

Jeśli ten wskaźnik zostanie zainicjowany (niezerowy), pomocnik ładowania opóźnienia wywoła funkcję w określonych punktach powiadomień w trakcie jego wykonywania. Wskaźnik funkcji ma następującą definicję:

```C
// The "notify hook" gets called for every call to the
// delay load helper.  This allows a user to hook every call and
// skip the delay load helper entirely.
//
// dliNotify == {
//  dliStartProcessing |
//  dliNotePreLoadLibrary  |
//  dliNotePreGetProc |
//  dliNoteEndProcessing}
//  on this call.
//
ExternC
PfnDliHook   __pfnDliNotifyHook2;

// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

Powiadomienia są przekazywane w strukturze **DelayLoadInfo** do funkcji Hook wraz z wartością powiadomienia. Te dane są identyczne z tymi, które są używane przez procedurę pomocnika ładowania opóźnień. Wartość powiadomienia będzie jedną z wartości zdefiniowanych w [strukturze i stałych definicjach](structure-and-constant-definitions.md).

## <a name="see-also"></a>Zobacz też

[Obsługa błędów i powiadomienia](error-handling-and-notification.md)
