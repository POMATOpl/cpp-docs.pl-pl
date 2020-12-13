---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0008'
title: Błąd PRJ0008 kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0008
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
ms.openlocfilehash: 2ae4952dfd3e5c5f53a3f549536598402ce1fd48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343915"
---
# <a name="project-build-error-prj0008"></a>Błąd PRJ0008 kompilacji projektu

Nie można usunąć pliku "File".

**Upewnij się, że plik nie jest otwarty przez inny proces i nie jest chroniony przed zapisem.**

Podczas odbudowywania lub czyszczenia, Visual C++ usuwa wszystkie znane pliki pośrednich i wyjściowych dla kompilacji, a także wszystkie pliki, które spełniają wymagania dotyczące symboli wieloznacznych w **rozszerzeniach, aby usunąć Właściwość Clean na** [stronie właściwości ogólne ustawienia konfiguracji](../../build/reference/general-property-page-project.md).

Ten błąd zostanie wyświetlony, jeśli Visual C++ nie można usunąć pliku. Aby rozwiązać ten problem, wprowadź plik i jego katalog zapisywalny dla użytkownika wykonującego kompilację.
