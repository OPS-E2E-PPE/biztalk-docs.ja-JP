---
title: ResolverDictionary クラス |Microsoft ドキュメント
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
ms.openlocfilehash: a2dfe0082ffc7f7b68c5c56811a28d5ccd20e93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295002"
---
# <a name="the-resolverdictionary-class"></a><span data-ttu-id="f895e-102">ResolverDictionary クラス</span><span class="sxs-lookup"><span data-stu-id="f895e-102">The ResolverDictionary Class</span></span>
<span data-ttu-id="f895e-103">**ResolverDictionary**クラスは、**ディクショナリ**-クラスのインスタンスに格納できる、**リゾルバー**としてクラス**文字列**名前/値のペア。</span><span class="sxs-lookup"><span data-stu-id="f895e-103">The **ResolverDictionary** class is a **Dictionary**-based class that can store instances of the **Resolver** class as **String** name/value pairs.</span></span> <span data-ttu-id="f895e-104">インスタンスを作成するときに、 **ResolverDictionary**クラス、既存の参照を提供する必要があります**ディクショナリ**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="f895e-104">When creating instances of the **ResolverDictionary** class, you must provide a reference to an existing **Dictionary** instance.</span></span> <span data-ttu-id="f895e-105">**ResolverDictionary**クラスのデータを提供する、**リゾルバー**クラスの実行時の解像度の実行時に使用します。</span><span class="sxs-lookup"><span data-stu-id="f895e-105">The **ResolverDictionary** class provides the data that the **Resolver** class uses when it performs run-time resolution.</span></span>  
  
 <span data-ttu-id="f895e-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]インストーラーがインストールおよび登録され、 **Microsoft.Practices.ESB.Resolver.dll**を持つアセンブリ、 **ResolverDictionary**グローバル アセンブリ キャッシュ内のクラスです。</span><span class="sxs-lookup"><span data-stu-id="f895e-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with the **ResolverDictionary** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="f895e-107">**ResolverDictionary**クラスは、1 つのメソッドと 1 つのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="f895e-107">The **ResolverDictionary** class exposes one method and one property:</span></span>  
  
-   <span data-ttu-id="f895e-108">**項目 (** キー **)** です。</span><span class="sxs-lookup"><span data-stu-id="f895e-108">**Item(** key **)**.</span></span> <span data-ttu-id="f895e-109">このメソッドは、キー名を表す文字列値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f895e-109">This method takes a string value that contains a key name.</span></span> <span data-ttu-id="f895e-110">基になるアイテムが存在しない場合、対応する文字列値または空の文字列を返します、**ディクショナリ**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="f895e-110">It returns the corresponding string value or an empty string if the item does not exist in the underlying **Dictionary** instance.</span></span>  
  
-   <span data-ttu-id="f895e-111">**BaseDictionary**です。</span><span class="sxs-lookup"><span data-stu-id="f895e-111">**BaseDictionary**.</span></span> <span data-ttu-id="f895e-112">このプロパティは、基になるへの参照を返します**ディクショナリ**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="f895e-112">This property returns a reference to the underlying **Dictionary** instance.</span></span>