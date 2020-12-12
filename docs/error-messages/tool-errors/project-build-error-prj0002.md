---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0002'
title: Błąd PRJ0002 kompilacji projektu
ms.date: 08/27/2018
f1_keywords:
- PRJ0002
helpviewer_keywords:
- PRJ0002
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
ms.openlocfilehash: b9f3d06a71183902c92102f12f665decdbf35a9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119424"
---
# <a name="project-build-error-prj0002"></a>Błąd PRJ0002 kompilacji projektu

> wynik błędu zwrócony z "*wiersz polecenia*".

Polecenie, *wiersz polecenia*, który został utworzony na podstawie danych wejściowych użytkownika w oknie dialogowym **strony właściwości** , zwróciło kod błędu, ale w oknie **danych wyjściowych** nie będą wyświetlane żadne informacje.

Rozwiązanie tego błędu zależy od tego, który narzędzie wygenerowało błąd. W przypadku MIDL uzyskasz informacje o tym, co poszło źle, jeśli są zdefiniowane/o (dane wyjściowe przekierowania).

Przyczyną tego błędu może być plik wsadowy, taki jak niestandardowy krok kompilacji lub zdarzenie kompilacji, które nie opisują warunków błędu.
