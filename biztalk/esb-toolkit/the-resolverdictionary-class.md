---
title: ResolverDictionary クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46deb8a0-0523-4a5c-ac6b-45c506de7a72
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1ec9080b0ad12910cc46a2844836a3b48887967
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399690"
---
# <a name="the-resolverdictionary-class"></a><span data-ttu-id="e2335-102">ResolverDictionary クラス</span><span class="sxs-lookup"><span data-stu-id="e2335-102">The ResolverDictionary Class</span></span>
<span data-ttu-id="e2335-103">**ResolverDictionary**クラスは、**ディクショナリ**-ベースのクラスのインスタンスを格納できる、**リゾルバー**クラスとして**文字列**名前/値のペア。</span><span class="sxs-lookup"><span data-stu-id="e2335-103">The **ResolverDictionary** class is a **Dictionary**-based class that can store instances of the **Resolver** class as **String** name/value pairs.</span></span> <span data-ttu-id="e2335-104">インスタンスを作成するときに、 **ResolverDictionary**クラスを既存の参照を提供する必要があります**ディクショナリ**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e2335-104">When creating instances of the **ResolverDictionary** class, you must provide a reference to an existing **Dictionary** instance.</span></span> <span data-ttu-id="e2335-105">**ResolverDictionary**クラスの提供、データ、**リゾルバー**実行時の解決を実行するとき、クラスで使用します。</span><span class="sxs-lookup"><span data-stu-id="e2335-105">The **ResolverDictionary** class provides the data that the **Resolver** class uses when it performs run-time resolution.</span></span>  
  
 <span data-ttu-id="e2335-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]インストーラーがインストールおよび登録され、 **Microsoft.Practices.ESB.Resolver.dll**を持つアセンブリ、 **ResolverDictionary**グローバル アセンブリ キャッシュ内のクラス。</span><span class="sxs-lookup"><span data-stu-id="e2335-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with the **ResolverDictionary** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="e2335-107">**ResolverDictionary**クラスが 1 つのメソッドと 1 つのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="e2335-107">The **ResolverDictionary** class exposes one method and one property:</span></span>  
  
-   <span data-ttu-id="e2335-108">**項目 (** キー **)** します。</span><span class="sxs-lookup"><span data-stu-id="e2335-108">**Item(** key **)**.</span></span> <span data-ttu-id="e2335-109">このメソッドは、キー名を表す文字列値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e2335-109">This method takes a string value that contains a key name.</span></span> <span data-ttu-id="e2335-110">基になるは、項目が存在しない場合、対応する文字列値または空の文字列を返します**ディクショナリ**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e2335-110">It returns the corresponding string value or an empty string if the item does not exist in the underlying **Dictionary** instance.</span></span>  
  
-   <span data-ttu-id="e2335-111">**BaseDictionary**します。</span><span class="sxs-lookup"><span data-stu-id="e2335-111">**BaseDictionary**.</span></span> <span data-ttu-id="e2335-112">このプロパティは、基になるへの参照を返します**ディクショナリ**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e2335-112">This property returns a reference to the underlying **Dictionary** instance.</span></span>