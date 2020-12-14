---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0050'
title: Błąd PRJ0050 kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0050
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
ms.openlocfilehash: 07a4df24f48a61e29214431840649566716bbac3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240809"
---
# <a name="project-build-error-prj0050"></a>Błąd PRJ0050 kompilacji projektu

Nie można zarejestrować danych wyjściowych. Upewnij się, że masz odpowiednie uprawnienia do modyfikowania rejestru.

System kompilacji Visual C++ nie mógł zarejestrować danych wyjściowych kompilacji (DLL lub exe). Aby zmodyfikować rejestr, należy zalogować się jako administrator.

Jeśli tworzysz plik. dll, możesz spróbować zarejestrować plik. dll ręcznie przy użyciu regsvr32.exe, aby wyświetlić informacje o przyczynie niepowodzenia kompilacji.

Jeśli nie tworzysz pliku dll, poszukaj w dzienniku kompilacji polecenia, które powoduje błąd.
