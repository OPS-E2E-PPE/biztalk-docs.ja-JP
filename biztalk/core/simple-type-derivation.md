---
title: 単純型の派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d43932a0-039c-4211-82c0-087bae186145
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1b1904c96c2786abad283db7133a9755c8743d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998499"
---
# <a name="simple-type-derivation"></a><span data-ttu-id="95693-102">単純型の派生</span><span class="sxs-lookup"><span data-stu-id="95693-102">Simple Type Derivation</span></span>
<span data-ttu-id="95693-103">XSD (XML Schema Definition) 言語は、次のように、既存の単純型の派生を使用した単純型のバリエーションを定義するための複数のメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="95693-103">XML Schema definition (XSD) language provides several mechanisms for defining variations of simple types, based on derivations of existing simple types, as follows:</span></span>  
  
- <span data-ttu-id="95693-104">**制限**します。</span><span class="sxs-lookup"><span data-stu-id="95693-104">**Restriction**.</span></span> <span data-ttu-id="95693-105">制約メカニズムを使用した単純型の派生は、この型に指定できる値を制限します。</span><span class="sxs-lookup"><span data-stu-id="95693-105">Simple type derivation by using the restriction mechanism involves the introduction of restrictions to the possible values for that type.</span></span> <span data-ttu-id="95693-106">たとえば、数値型の最小値および最大値または文字列型の最小値および最大値です。</span><span class="sxs-lookup"><span data-stu-id="95693-106">Examples are minimum and/or maximum values for numeric types, or a minimum and maximum length for string types.</span></span>  
  
- <span data-ttu-id="95693-107">**リスト**します。</span><span class="sxs-lookup"><span data-stu-id="95693-107">**List**.</span></span> <span data-ttu-id="95693-108">リスト メカニズムを使用して単純型の派生で構成されるとして定義されるインスタンス メッセージに 1 つの属性または要素値は、特定の種類の値をスペース区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="95693-108">Simple type derivation by using the list mechanism allows a single attribute or element value in an instance message to be defined as consisting of a list of space-separated values of a particular type.</span></span>  
  
- <span data-ttu-id="95693-109">**共用体**します。</span><span class="sxs-lookup"><span data-stu-id="95693-109">**Union**.</span></span> <span data-ttu-id="95693-110">ユニオン メカニズムを使用して単純型の派生では、1 つの属性または要素値をいくつかの指定した種類のいずれか 1 つの値として定義されるインスタンス メッセージにできます。</span><span class="sxs-lookup"><span data-stu-id="95693-110">Simple type derivation by using the union mechanism allows a single attribute or element value in an instance message to be defined as a single value of one of several specified types.</span></span>  
  
  <span data-ttu-id="95693-111">このセクションでは、これらの単純型の派生の詳細について説明します。また、[プロパティ] ウィンドウの適切なノード プロパティの設定によってこれらの派生を定義する方法、および対応する XSD の構築方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="95693-111">This section describes these simple type derivations in more detail, including how to define these derivations by setting the appropriate node properties in the Properties window, as well as how the corresponding XSD is constructed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95693-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="95693-112">In This Section</span></span>  
  
-   [<span data-ttu-id="95693-113">制約メカニズムを使用した単純型の派生</span><span class="sxs-lookup"><span data-stu-id="95693-113">Simple Type Derivation Using the Restriction Mechanism</span></span>](../core/simple-type-derivation-using-the-restriction-mechanism.md)  
  
-   [<span data-ttu-id="95693-114">リスト メカニズムを使用した単純型の派生</span><span class="sxs-lookup"><span data-stu-id="95693-114">Simple Type Derivation Using the List Mechanism</span></span>](../core/simple-type-derivation-using-the-list-mechanism.md)  
  
-   [<span data-ttu-id="95693-115">ユニオン メカニズムを使用した単純型の派生</span><span class="sxs-lookup"><span data-stu-id="95693-115">Simple Type Derivation Using the Union Mechanism</span></span>](../core/simple-type-derivation-using-the-union-mechanism.md)