---
description: 'Dowiedz się więcej o: PRJ0041 dotyczące ostrzeżenie kompilacji projektu'
title: Ostrzeżenie PRJ0041 dotyczące kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0041
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
ms.openlocfilehash: dc6b36e052d3402f047257a4bf0035d7ec30f92a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206451"
---
# <a name="project-build-warning-prj0041"></a>Ostrzeżenie PRJ0041 dotyczące kompilacji projektu

Nie można odnaleźć brakującej zależności "zależność" dla pliku "File". Projekt może być nadal kompilowany, ale może być nadal nieaktualny do momentu znalezienia tego pliku.

Plik (plik zasobów lub IDL/. ODL, na przykład zawiera instrukcję include, której system projektu nie mógł rozpoznać.

Ponieważ system projektu nie przetwarza instrukcji preprocesora (na przykład #if), instrukcja powodująca problemy może nie być częścią kompilacji.

Aby usunąć to ostrzeżenie, usuń cały niezbędny kod w plikach. RC lub Dodaj pliki zastępcze o odpowiedniej nazwie.
