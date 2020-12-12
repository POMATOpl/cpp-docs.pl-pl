---
description: 'Dowiedz się więcej na temat: Używanie wyrażeń lambda, obiektów funkcyjnych i funkcji z ograniczeniami'
title: Używanie wyrażeń lambda, obiektów Function i funkcji z ograniczeniami
ms.date: 11/04/2016
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
ms.openlocfilehash: bef02f30b5d5b5f11b8051c7a596ac0a141eef0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314454"
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>Używanie wyrażeń lambda, obiektów Function i funkcji z ograniczeniami

Kod C++ AMP, który ma być uruchamiany na akceleratorze, jest określany jako argument w wywołaniu metody [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) . Jako ten argument można podać wyrażenie lambda lub obiekt funkcji (Funktor). Ponadto wyrażenie lambda lub obiekt funkcji może wywoływać funkcję z ograniczeniami C++ AMP. W tym temacie jest używany algorytm dodawania tablicy do prezentowania wyrażeń lambda, obiektów funkcyjnych i funkcji z ograniczeniami. Poniższy przykład pokazuje algorytm bez kodu C++ AMP. 2 1 — tworzone są tablice jednowymiarowe o równej długości. Odpowiednie elementy całkowite są dodawane i przechowywane w trzeciej tablicy 1-wymiarowej. C++ AMP nie jest używany.

```cpp
void CpuMethod() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    for (int idx = 0; idx <5; idx++)
    {
        sumCPP[idx] = aCPP[idx] + bCPP[idx];
    }

    for (int idx = 0; idx <5; idx++)
    {
        std::cout <<sumCPP[idx] <<"\n";
    }
}
```

## <a name="lambda-expression"></a>Wyrażenie lambda

Użycie wyrażenia lambda jest najbardziej bezpośrednim sposobem na użycie C++ AMP do ponownego zapisania kodu.

```cpp
void AddArraysWithLambda() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
             sum[idx] = a[idx] + b[idx];
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Wyrażenie lambda musi zawierać jeden parametr indeksowania i musi zawierać `restrict(amp)` . W przykładzie obiekt [array_view](../../parallel/amp/reference/array-view-class.md) `sum` ma rangę 1. W związku z tym, parametr do instrukcji lambda jest obiektem [indeksu](../../parallel/amp/reference/index-class.md) , który ma rangę 1. W czasie wykonywania wyrażenie lambda jest wykonywane raz dla każdego elementu w obiekcie [array_view](../../parallel/amp/reference/array-view-class.md) . Aby uzyskać więcej informacji, zobacz [składnia wyrażenia lambda](../../cpp/lambda-expression-syntax.md).

## <a name="function-object"></a>Obiekt Function

Kod akceleratora można obsłużyć do obiektu funkcji.

```cpp
class AdditionFunctionObject
{
public:
    AdditionFunctionObject(const array_view<int, 1>& a,
    const array_view<int, 1>& b,
    const array_view<int, 1>& sum)
    : a(a), b(b), sum(sum)
    {
    }

    void operator()(index<1> idx) restrict(amp)
    {
        sum[idx] = a[idx] + b[idx];
    }

private:
    array_view<int, 1> a;
    array_view<int, 1> b;
    array_view<int, 1> sum;
};

void AddArraysWithFunctionObject() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        AdditionFunctionObject(a, b, sum));

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Obiekt Function musi zawierać konstruktora i musi zawierać Przeciążenie operatora wywołania funkcji. Operator wywołania funkcji musi zawierać jeden parametr indeksowania. Wystąpienie obiektu Function jest przesyłane jako drugi argument do metody [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) . W tym przykładzie trzy obiekty [array_view](../../parallel/amp/reference/array-view-class.md) są przesyłane do konstruktora obiektu Function. Obiekt [array_view](../../parallel/amp/reference/array-view-class.md) `sum` ma rangę 1. W związku z tym parametr do operatora wywołania funkcji jest obiektem [indeksu](../../parallel/amp/reference/index-class.md) , który ma rangę 1. W czasie wykonywania funkcja jest wykonywana jeden raz dla każdego elementu w obiekcie [array_view](../../parallel/amp/reference/array-view-class.md) . Aby uzyskać więcej informacji, zobacz [wywołania funkcji](../../cpp/function-call-cpp.md) i [obiekty funkcji w standardowej bibliotece języka C++](../../standard-library/function-objects-in-the-stl.md).

## <a name="c-amp-restricted-function"></a>Funkcja C++ AMP-Restricted

Można bardziej zwiększyć współczynnik kodu akceleratora, tworząc funkcję ograniczoną i wywołując ją z wyrażenia lambda lub obiektu funkcji. Poniższy przykład kodu demonstruje, jak wywołać funkcję ograniczoną z wyrażenia lambda.

```cpp
void AddElementsWithRestrictedFunction(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)
{
    sum[idx] = a[idx] + b[idx];
}

void AddArraysWithFunction() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<int, 1> a(5, aCPP);

    array_view<int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
            AddElementsWithRestrictedFunction(idx, sum, a, b);
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Funkcja z ograniczeniami musi zawierać `restrict(amp)` i być zgodna z ograniczeniami opisanymi w temacie [ograniczanie (C++ amp)](../../cpp/restrict-cpp-amp.md).

## <a name="see-also"></a>Zobacz też

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Składnia wyrażenia lambda](../../cpp/lambda-expression-syntax.md)<br/>
[Wywołanie funkcji](../../cpp/function-call-cpp.md)<br/>
[Obiekty funkcji w standardowej bibliotece języka C++](../../standard-library/function-objects-in-the-stl.md)<br/>
[ograniczenie (C++ AMP)](../../cpp/restrict-cpp-amp.md)
