---
description: 'Dowiedz się więcej na temat: przy użyciu parametrów wymiennych (Rejestrator&#39;s preprocesor)'
title: Używanie parametrów wymiennych (Rejestrator ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: 5b8b8071115186a462bbf9ca0b12d869458dd925
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157205"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Używanie parametrów wymiennych (Rejestrator&#39;s preprocesora)

Parametry wymienne umożliwiają klientowi rejestratora określanie danych czasu wykonywania. W tym celu Rejestrator utrzymuje mapę zastępującą, do której wprowadza wartości skojarzone z parametrami wymiennymi w skrypcie. Rejestrator wprowadza te wpisy w czasie wykonywania.

## <a name="using-module"></a><a name="_atl_using_.25.module.25"></a> Korzystanie z% MODULE%

[Kreator kontrolki ATL](../atl/reference/atl-control-wizard.md) automatycznie generuje skrypt, który używa programu `%MODULE%` . ATL używa tego parametru do przemieszczenia dla rzeczywistej lokalizacji biblioteki DLL lub EXE serwera.

## <a name="concatenating-run-time-data-with-script-data"></a>Łączenie Run-Time danych z danymi skryptu

Innym sposobem użycia preprocesora jest łączenie danych czasu wykonywania z danymi skryptu. Załóżmy na przykład, że wpis zawiera pełną ścieżkę do modułu z ciągiem " `, 1` " dołączonym na końcu. Najpierw Zdefiniuj następujące rozszerzenie:

```rgs
'MySampleKey' = s '%MODULE%, 1'
```

Następnie przed wywołaniem jednej z metod przetwarzania skryptu z listy [Wywoływanie skryptów](../atl/invoking-scripts.md)Dodaj zastąpienie do mapy:

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

Podczas analizowania skryptu, rejestrator rozszerza `'%MODULE%, 1'` się do `c:\mycode\mydll.dll, 1` .

> [!NOTE]
> W skrypcie rejestratora jest maksymalny rozmiar tokenu 4K. (Token jest dowolnym rozpoznawalnym elementem w składni). Obejmuje to tokeny, które zostały utworzone lub rozwinięte przez preprocesor.

> [!NOTE]
> Aby zastąpić wartości zastępcze w czasie wykonywania, Usuń wywołanie skryptu do [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) lub [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) makro. Zamiast tego zastąp go własną `UpdateRegistry` metodą, która wywołuje [CAtlModule:: UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) lub [CAtlModule:: UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources), i przekaż swoją tablicę struktur _ATL_REGMAP_ENTRY. Tablica _ATL_REGMAP_ENTRY musi mieć co najmniej jeden wpis ustawiony na wartość {NULL, NULL}, a ten wpis powinien zawsze być ostatnim wpisem. W przeciwnym razie błąd naruszenia zasad dostępu zostanie wygenerowany, gdy `UpdateRegistryFromResource` zostanie wywołane.

> [!NOTE]
> Podczas kompilowania projektu, który wyprowadza plik wykonywalny, ATL automatycznie dodaje znaki cudzysłowu wokół nazwy ścieżki utworzonej w czasie wykonywania za pomocą parametru skryptu **% module%** rejestratora. Jeśli nie chcesz, aby nazwa ścieżki zawierała znaki cudzysłowu, zamiast tego użyj nowego parametru **% MODULE_RAW%** .
>
> Podczas kompilowania projektu, który wyprowadza bibliotekę DLL, ATL nie doda cudzysłowu do nazwy ścieżki, jeśli użyto **% module%** lub **% MODULE_RAW%** .

## <a name="see-also"></a>Zobacz też

[Tworzenie skryptów rejestratora](../atl/creating-registrar-scripts.md)
