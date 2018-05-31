---
title: ヘルパー クラスを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 593d6e41-8fef-4355-a779-800e8b3298dd
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e015627591077d7b8d4d63f2fef978827f4497d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294858"
---
# <a name="using-the-helper-classes"></a><span data-ttu-id="11ff6-102">ヘルパー クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="11ff6-102">Using the Helper Classes</span></span>
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]<span data-ttu-id="11ff6-103">他のプロセス、サービス、および、ツールキットでのコンポーネントで使用されるヘルパー クラスのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="11ff6-103"> includes a set of helper classes used by the other processes, services, and components in the toolkit.</span></span> <span data-ttu-id="11ff6-104">これらのヘルパー クラスがパブリックでもため、必要に応じて、独自のコードで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="11ff6-104">Because these helper classes are also public, you can use them in your own code as required.</span></span>  
  
 <span data-ttu-id="11ff6-105">場合によっては、する必要がありますを使用して、ESB の他のクラスのメソッドの適切な型のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="11ff6-105">In some cases, you must use them to provide parameters of the appropriate type for methods of other classes in the ESB.</span></span> <span data-ttu-id="11ff6-106">たとえば、競合回避モジュールの Web サービス メソッドがのインスタンスのジェネリック コレクションを返す、**リゾルバー**クラスです。</span><span class="sxs-lookup"><span data-stu-id="11ff6-106">For example, the Resolver Web service methods return a generic collection of instances of the **Resolver** class.</span></span>  
  
 <span data-ttu-id="11ff6-107">次のセクションでは、説明のクラスが含まれているヘルパー [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="11ff6-107">The following sections describe the helper classes are included in [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span></span>  
  
-   [<span data-ttu-id="11ff6-108">MapHelper クラス</span><span class="sxs-lookup"><span data-stu-id="11ff6-108">The MapHelper Class</span></span>](../esb-toolkit/the-maphelper-class.md)  
  
-   [<span data-ttu-id="11ff6-109">競合回避モジュール クラス</span><span class="sxs-lookup"><span data-stu-id="11ff6-109">The Resolver Class</span></span>](../esb-toolkit/the-resolver-class.md)  
  
-   [<span data-ttu-id="11ff6-110">ResolverDictionary クラス</span><span class="sxs-lookup"><span data-stu-id="11ff6-110">The ResolverDictionary Class</span></span>](../esb-toolkit/the-resolverdictionary-class.md)  
  
-   [<span data-ttu-id="11ff6-111">競合回避モジュール マネージャー (ResolverMgr) クラス</span><span class="sxs-lookup"><span data-stu-id="11ff6-111">The Resolver Manager (ResolverMgr) Class</span></span>](../esb-toolkit/the-resolver-manager-resolvermgr-class.md)