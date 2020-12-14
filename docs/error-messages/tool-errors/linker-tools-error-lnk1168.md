---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1168'
title: Błąd narzędzi konsolidatora LNK1168
ms.date: 11/04/2016
f1_keywords:
- LNK1168
helpviewer_keywords:
- LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
ms.openlocfilehash: 692bfbcc744307f32c8017b41ec27f5f421ea17c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253497"
---
# <a name="linker-tools-error-lnk1168"></a>Błąd narzędzi konsolidatora LNK1168

nie można otworzyć pliku do zapisu

Konsolidator nie może zapisać do `filename` . Plik może być używany i jego uchwyt jest zablokowany przez inny proces lub nie masz uprawnienia do zapisu dla pliku lub katalogu lub udziału sieciowego, w którym się on znajduje. Ten błąd jest często spowodowany przez warunek przejściowy — na przykład blokadę zainstalowaną przez program antywirusowy, proces indeksowania wyszukiwania plików lub opóźnienie zwalniania blokady przechowywanej przez system kompilacji programu Visual Studio.

Aby rozwiązać ten problem, upewnij się, że `filename` dojście do pliku nie jest zablokowane i że masz uprawnienia do zapisu dla tego pliku. Jeśli jest to plik wykonywalny, sprawdź, czy nie jest uruchomiony.

Możesz użyć [uchwytu](/sysinternals/downloads/handle) narzędzi Windows Sysinternals lub [Eksploratora procesów](/sysinternals/downloads/process-explorer) , aby określić, który proces ma blokadę obsługi plików `filename` . Przy użyciu Eksploratora procesów możesz zwalniać blokady uchwytów otwartego pliku. Aby uzyskać informacje dotyczące sposobu korzystania z tych narzędzi, przeczytaj pliki pomocy, które są z nimi dostarczane.

Jeśli plik jest zablokowany przez program antywirusowy, można naprawić ten problem poprzez wykluczenie katalogów danych wyjściowych kompilacji z funkcji automatycznego skanowania przez program antywirusowy. Tworzenie nowych plików w systemie plików często wyzwala skanery antywirusowe, które w trakcie skanowania nakładają blokady na pliki. Szczegółowe informacje na temat wykluczania określonych katalogów ze skanowania można znaleźć w dokumentacji programu antywirusowego.

Jeśli plik jest zablokowany przez usługę indeksowania wyszukiwania, można naprawić ten problem poprzez wykluczenie katalogów danych wyjściowych kompilacji z automatycznego indeksowania. Aby uzyskać więcej informacji, zobacz dokumentację dotyczącą usługi indeksowania. Aby zmienić usługę indeksowania wyszukiwania systemu Windows, użyj **opcji indeksowania** w **Panelu sterowania** systemu Windows. Aby uzyskać więcej informacji, zobacz [indeksowanie wyszukiwania w systemie Windows 10: często zadawane pytania](https://support.microsoft.com/help/4098843/windows-10-search-indexing-faq).

Jeśli plik wykonywalny nie może zostać zastąpiony przez proces kompilacji, może być zablokowany przez Eksplorator plików. Jeśli usługa **Experience aplikacji** została wyłączona, Eksplorator plików może zawiesić się do pliku wykonywalnego blokady przez dłuższy czas. Aby rozwiązać ten problem, uruchom program **Services. msc** , a następnie otwórz okno dialogowe **Właściwości** dla usługi **środowisko obsługi aplikacji** . Zmień **Typ uruchamiania** z **wyłączone** na **ręczny**.
