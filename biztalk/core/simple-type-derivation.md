---
title: "単純型の派生 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d43932a0-039c-4211-82c0-087bae186145
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcc74796de8543f1e0f895d0b3dff705aeb2930e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation"></a><span data-ttu-id="03ae0-102">単純型の派生</span><span class="sxs-lookup"><span data-stu-id="03ae0-102">Simple Type Derivation</span></span>
<span data-ttu-id="03ae0-103">XSD (XML Schema Definition) 言語は、次のように、既存の単純型の派生を使用した単純型のバリエーションを定義するための複数のメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="03ae0-103">XML Schema definition (XSD) language provides several mechanisms for defining variations of simple types, based on derivations of existing simple types, as follows:</span></span>  
  
-   <span data-ttu-id="03ae0-104">**制限**です。</span><span class="sxs-lookup"><span data-stu-id="03ae0-104">**Restriction**.</span></span> <span data-ttu-id="03ae0-105">制約メカニズムを使用した単純型の派生は、この型に指定できる値を制限します。</span><span class="sxs-lookup"><span data-stu-id="03ae0-105">Simple type derivation by using the restriction mechanism involves the introduction of restrictions to the possible values for that type.</span></span> <span data-ttu-id="03ae0-106">たとえば、数値型の最小値および最大値または文字列型の最小値および最大値です。</span><span class="sxs-lookup"><span data-stu-id="03ae0-106">Examples are minimum and/or maximum values for numeric types, or a minimum and maximum length for string types.</span></span>  
  
-   <span data-ttu-id="03ae0-107">**リスト**です。</span><span class="sxs-lookup"><span data-stu-id="03ae0-107">**List**.</span></span> <span data-ttu-id="03ae0-108">リスト メカニズムを使用して、単純型の派生では、1 つの属性または要素値を許可で構成されるとして定義するインスタンス メッセージ内の特定の種類のスペースで区切られた値の一覧です。</span><span class="sxs-lookup"><span data-stu-id="03ae0-108">Simple type derivation by using the list mechanism allows a single attribute or element value in an instance message to be defined as consisting of a list of space-separated values of a particular type.</span></span>  
  
-   <span data-ttu-id="03ae0-109">**共用体**です。</span><span class="sxs-lookup"><span data-stu-id="03ae0-109">**Union**.</span></span> <span data-ttu-id="03ae0-110">ユニオン メカニズムを使用して、単純型の派生は、いくつかの指定した種類のいずれか 1 つの値として定義するインスタンス メッセージ内の 1 つの属性または要素値を許可します。</span><span class="sxs-lookup"><span data-stu-id="03ae0-110">Simple type derivation by using the union mechanism allows a single attribute or element value in an instance message to be defined as a single value of one of several specified types.</span></span>  
  
 <span data-ttu-id="03ae0-111">このセクションでは、これらの単純型の派生の詳細について説明します。また、[プロパティ] ウィンドウの適切なノード プロパティの設定によってこれらの派生を定義する方法、および対応する XSD の構築方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="03ae0-111">This section describes these simple type derivations in more detail, including how to define these derivations by setting the appropriate node properties in the Properties window, as well as how the corresponding XSD is constructed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03ae0-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="03ae0-112">In This Section</span></span>  
  
-   [<span data-ttu-id="03ae0-113">制約メカニズムを使用して単純型の派生</span><span class="sxs-lookup"><span data-stu-id="03ae0-113">Simple Type Derivation Using the Restriction Mechanism</span></span>](../core/simple-type-derivation-using-the-restriction-mechanism.md)  
  
-   [<span data-ttu-id="03ae0-114">リスト メカニズムを使用した単純型の派生</span><span class="sxs-lookup"><span data-stu-id="03ae0-114">Simple Type Derivation Using the List Mechanism</span></span>](../core/simple-type-derivation-using-the-list-mechanism.md)  
  
-   [<span data-ttu-id="03ae0-115">ユニオン メカニズムを使用して単純型の派生</span><span class="sxs-lookup"><span data-stu-id="03ae0-115">Simple Type Derivation Using the Union Mechanism</span></span>](../core/simple-type-derivation-using-the-union-mechanism.md)