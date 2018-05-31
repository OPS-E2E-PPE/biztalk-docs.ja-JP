---
title: 競合回避モジュール クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9ebd6c2-fd86-471a-bc50-b1b89f701fab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1359bcbb9c6c918fc0ee6d5e67bacb8e3559c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294850"
---
# <a name="the-resolver-class"></a><span data-ttu-id="71c51-102">競合回避モジュール クラス</span><span class="sxs-lookup"><span data-stu-id="71c51-102">The Resolver Class</span></span>
<span data-ttu-id="71c51-103">**リゾルバー**クラスは、名前/値ペアを公開する単純な構造体。</span><span class="sxs-lookup"><span data-stu-id="71c51-103">The **Resolver** class is a simple structure that exposes a name/value pair.</span></span> <span data-ttu-id="71c51-104">競合回避モジュールの Web サービスは、そのメソッドからこのクラスのインスタンスのジェネリック コレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="71c51-104">The Resolver Web service returns a generic collection of instances of this class from its methods.</span></span>  
  
 <span data-ttu-id="71c51-105">ESB コア インストーラーがインストールおよび登録され、 **Microsoft.Practices.ESB.Resolver.dll**アセンブリをグローバル アセンブリ キャッシュに競合回避モジュールのクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="71c51-105">The ESB Core installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with Resolver class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="71c51-106">ディクショナリ ベースの名前/値の使用により、解放後で新しい項目の追加に簡単になり、解決方法および現在の競合回避モジュールの種類に依存する関連のないプロパティを含めることを回避することで解決の結果のサイズを最小化に近づいています。</span><span class="sxs-lookup"><span data-stu-id="71c51-106">The use of a dictionary-based name/value approach makes it easier to add new items in future releases and minimizes the size of the resolution result by avoiding inclusion of non-relevant properties that depend on the resolution method and the current resolver type.</span></span>  
  
 <span data-ttu-id="71c51-107">**リゾルバー**クラスは 2 つのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="71c51-107">The **Resolver** class exposes two properties:</span></span>  
  
-   <span data-ttu-id="71c51-108">**名前**です。</span><span class="sxs-lookup"><span data-stu-id="71c51-108">**Name**.</span></span> <span data-ttu-id="71c51-109">これは、接続文字列が解決された後に返される情報が含まれる名前/値ペアの名前です。</span><span class="sxs-lookup"><span data-stu-id="71c51-109">This is the name of a name/value pair that contains information that is returned after a connection string is resolved.</span></span>  
  
-   <span data-ttu-id="71c51-110">**値**。</span><span class="sxs-lookup"><span data-stu-id="71c51-110">**Value**.</span></span> <span data-ttu-id="71c51-111">これは、名前/値ペアの名前に対応する値です。</span><span class="sxs-lookup"><span data-stu-id="71c51-111">This is the value that corresponds to the name of the name/value pair.</span></span>