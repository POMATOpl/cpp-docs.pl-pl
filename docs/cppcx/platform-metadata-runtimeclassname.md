---
description: 'Dowiedz się więcej o: platform:: Metadata:: RuntimeClassName'
title: Platform::Metadata::RuntimeClassName
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
ms.openlocfilehash: 25d6f3ae6b7509029b08f809fa20d5bd0ca5e735
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308383"
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName

W przypadku zastosowania do definicji klasy, zapewnia, że Klasa prywatna zwraca poprawną nazwę z funkcji GetRuntimeClassName —.

## <a name="syntax"></a>Składnia

```cpp
[Platform::Metadata::RuntimeClassName] name
```

#### <a name="parameters"></a>Parametry

*Nazwij*<br/>
Nazwa istniejącego typu publicznego, który jest widoczny w środowisko wykonawcze systemu Windows.

### <a name="remarks"></a>Uwagi

Użyj tego atrybutu dla prywatnych klas referencyjnych, aby określić niestandardową nazwę typu środowiska uruchomieniowego i/lub jeśli istniejąca nazwa nie spełnia wymagań. Określ jako nazwę interfejs publiczny, który implementuje Klasa.

### <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak używać atrybutu. W tym przykładzie nazwa typu środowiska uruchomieniowego HellowWorldImpl jest test:: Native:: webcomponent:: IHelloWorld

```cpp
namespace Test
{
    namespace Native
    {
        namespace MyComponent
        {
            public interface class IHelloWorld
            {
                Platform::String^ SayHello();
            };

            private ref class HelloWorldImpl sealed :[Platform::Metadata::RuntimeClassName] IHelloWorld
            {
            public:
                HelloWorldImpl();
                virtual Platform::String^ SayHello();
            };

            Platform::String^ HelloWorldImpl::SayHello()
            {
                return L"Hello World!";
            }
        }
    }
}
```

## <a name="see-also"></a>Zobacz też

[Platform:: Metadata — przestrzeń nazw](../cppcx/platform-metadata-namespace.md)
