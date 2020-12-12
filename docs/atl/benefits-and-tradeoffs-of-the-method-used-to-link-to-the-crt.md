---
description: 'Dowiedz się więcej na temat: zalety i wady metody używanej do łączenia z CRT'
title: Zalety i wady metody używanej do łączenia z CRT
ms.date: 05/06/2019
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
ms.openlocfilehash: 763332de9615e978d84902f67f2c97efd0767c89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148528"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>Zalety i wady metody używanej do łączenia z CRT

Projekt może być połączony z CRT dynamicznie lub statycznie. W poniższej tabeli przedstawiono korzyści i kompromisy związane z wybraniem metody, która ma zostać użyta.

|Metoda|Korzyść|Uboczn|
|------------|-------------|--------------|
|Statyczne łączenie z CRT<br /><br /> (**Biblioteka środowiska uruchomieniowego** jest ustawiona na **jedną wielowątkowość**)|Biblioteka DLL CRT nie jest wymagana w systemie, w którym zostanie uruchomiony obraz.|Informacje o 25K kodu startowego są dodawane do obrazu, znacznie zwiększając jego rozmiar.|
|Dynamiczne łączenie z CRT<br /><br /> (**Biblioteka środowiska uruchomieniowego** ustawiona na **wiele wątków**)|Obraz nie wymaga kodu uruchamiania CRT, więc jest znacznie mniejszy.|Biblioteka DLL CRT musi znajdować się w systemie, na którym jest uruchomiony obraz.|

Temat [łączący się z CRT w projekcie ATL](../atl/linking-to-the-crt-in-your-atl-project.md) zawiera opis sposobu wybierania sposobu łączenia z CRT.

## <a name="see-also"></a>Zobacz też

[Programowanie za pomocą kodu ATL i języka C Run-Time](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Zachowanie biblioteki wykonawczej DLL i Visual C++](../build/run-time-library-behavior.md)<br/>
[Funkcje biblioteki CRT](../c-runtime-library/crt-library-features.md)
