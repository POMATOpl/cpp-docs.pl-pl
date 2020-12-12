---
description: Dowiedz się więcej na temat integracji środowiska CLR (C++/CX)
title: Integracja ze środowiskiem uruchomieniowym CLR (C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: ae335168ee456f0461154ab48e9d92325fdc599b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190240"
---
# <a name="clr-integration-ccx"></a>Integracja ze środowiskiem uruchomieniowym CLR (C++/CX)

Niektóre typy środowisko wykonawcze systemu Windows otrzymują specjalną obsługę w języku C++/CX i Języki, które są oparte na środowisku uruchomieniowym języka wspólnego (CLR). W tym artykule omówiono, jak kilka typów w jednym języku jest mapowanych na inny język. Na przykład środowisko CLR mapuje Windows. Foundation. IVector do System. Collections. IList, Windows. Foundation. IMap do System. Collections. IDictionary i tak dalej. Podobnie/CX języka C++ specjalnie mapuje typy takie jak platforma::D elegata i platform:: String.

## <a name="mapping-the-windows-runtime-to-ccx"></a>Mapowanie środowisko wykonawcze systemu Windows na C++/CX

Gdy C++/CX odczytuje plik metadanych systemu Windows (WinMD), kompilator automatycznie mapuje typowe przestrzenie nazw środowisko wykonawcze systemu Windows i typów do przestrzeni nazw i typów C++/CX. Na przykład typ liczbowy środowisko wykonawcze systemu Windows `UInt32` jest automatycznie mapowany do `default::uint32` .

C++/CX mapuje kilka innych typów środowisko wykonawcze systemu Windows do przestrzeni nazw **platformy** . Na przykład dojście HString **systemu Windows:: Foundation** , które reprezentuje ciąg tekstowy w formacie Unicode, jest mapowany na klasę C++/CX `Platform::String` . Gdy operacja środowisko wykonawcze systemu Windows zwraca błąd HRESULT, jest mapowana na C++/CX `Platform::Exception` .

C++/CX mapuje także niektóre typy w środowisko wykonawcze systemu Windows przestrzenie nazw w celu zwiększenia funkcjonalności typu. W przypadku tych typów C++/CX zapewnia konstruktory pomocnika i metody, które są specyficzne dla języka C++ i nie są dostępne w standardowym pliku winmd typu.

Na poniższej liście przedstawiono struktury wartości obsługujące nowe konstruktory i metody pomocnika. Jeśli wcześniej Zapisano kod, który używa list inicjalizacji struktury, zmień go tak, aby korzystał z nowo dodanych konstruktorów.

**Windows:: Foundation**

- Moment

- Rect

- Rozmiar

**Windows:: UI**

- Kolor

**Windows:: UI:: XAML**

- CornerRadius

- Czas trwania

- GridLength

- Grubość

**Windows:: UI:: XAML:: Interop**

- TypeName

**Windows:: UI:: XAML:: Media**

- Macierz

**Windows:: UI:: XAML:: Media:: Animation**

- KeyTime

- RepeatBehavior

**Windows:: UI:: XAML:: Media:: Media3D**

- Matrix3D

## <a name="mapping-the-clr-to-ccx"></a>Mapowanie środowiska CLR do języka C++/CX

Gdy kompilatory języka Microsoft C++ lub C# odczytają plik winmd, automatycznie mapują pewne typy w pliku metadanych na odpowiednie typy C++/CX lub CLR. Na przykład w środowisku CLR \<T> interfejs IVector jest mapowany na IList \<T> . Jednak w języku C++/CX interfejs IVector \<T> nie jest zamapowany na inny typ.

IReference \<T> środowisko wykonawcze systemu Windows mapowania na wartość null \<T> w programie .NET.

## <a name="see-also"></a>Zobacz też

[Współdziałanie z innymi językami](../cppcx/interoperating-with-other-languages-c-cx.md)
