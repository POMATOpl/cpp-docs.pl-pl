---
description: 'Dowiedz się więcej o: kompilowanie aplikacji izolowanych C/C++'
title: Kompilowanie izolowanych kompilacji C/C++
ms.date: 05/06/2019
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: a8cd99032c27d21efaec7f213c470017e52777c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163213"
---
# <a name="building-cc-isolated-applications"></a>Kompilowanie izolowanych kompilacji C/C++

Izolowana aplikacja zależy tylko od zestawów równoległych i wiąże się z jej zależnościami przy użyciu manifestu. Nie jest wymagane, aby aplikacja była całkowicie izolowana w celu prawidłowego działania w systemie Windows; Jednak dzięki zainwestowaniu w aplikację w sposób całkowicie odizolowany, można zaoszczędzić czas, jeśli trzeba będzie obniżyć swoją aplikację w przyszłości. Aby uzyskać więcej informacji na temat zalet tworzenia aplikacji w sposób całkowicie izolowany, zobacz [izolowane aplikacje](/windows/win32/SbsCs/isolated-applications).

Podczas kompilowania natywnej aplikacji C/C++ przy użyciu programu Visual Studio domyślnie system projektu programu Visual Studio generuje plik manifestu, który opisuje zależności aplikacji w bibliotekach programu Visual Studio. Jeśli są to jedyne zależności aplikacji, to zostanie ona izolowana, gdy tylko zostanie odbudowana przy użyciu programu Visual Studio. Jeśli aplikacja korzysta z innych bibliotek w czasie wykonywania, może być konieczne odbudowanie tych bibliotek jako zestawów równoległych zgodnie z krokami opisanymi w temacie [Tworzenie zestawów równoległych C/C++](building-c-cpp-side-by-side-assemblies.md).

## <a name="see-also"></a>Zobacz też

[Koncepcje izolowanych aplikacji i zestawów równoległych](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Kompilowanie aplikacji izolowanych C/C++ i zestawów równoległych](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
