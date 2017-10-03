---
title: "アプリケーションの展開時の成果物の処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- artifacts, deploying
- deploying [artifacts]
ms.assetid: afd77251-c3bd-454b-907f-a841911abe47
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5b16266d90c0119a6dd5217319a697efbc365c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-happens-to-artifacts-during-application-deployment"></a><span data-ttu-id="c331b-102">アプリケーション展開時のアイテムの処理</span><span class="sxs-lookup"><span data-stu-id="c331b-102">What Happens to Artifacts During Application Deployment</span></span>
<span data-ttu-id="c331b-103">このセクションのトピックでは、アイテムの追加と削除、アプリケーションやアイテムのエクスポートとインポート、およびアプリケーションのインストールとアンインストールを行う場合に、アプリケーションに関連付けられたアイテムに対して行われる処理について説明します。</span><span class="sxs-lookup"><span data-stu-id="c331b-103">The topics in this section describe what happens to the artifacts associated with an application when you add and remove artifacts, export and import applications and artifacts, and install and uninstall applications.</span></span> <span data-ttu-id="c331b-104">説明の内容として、次の項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c331b-104">It covers subjects such as the following:</span></span>  
  
-   <span data-ttu-id="c331b-105">BizTalk Server データベースに対するアイテムの追加および削除の方法</span><span class="sxs-lookup"><span data-stu-id="c331b-105">How artifacts are added to and removed from the BizTalk Server databases</span></span>  
  
-   <span data-ttu-id="c331b-106">ローカル ファイル システムに対するアイテムのコピーおよび削除の方法</span><span class="sxs-lookup"><span data-stu-id="c331b-106">How artifacts are copied to and deleted from the local file system</span></span>  
  
-   <span data-ttu-id="c331b-107">Windows レジストリに対するアイテム (.NET アセンブリおよび COM コンポーネント) の追加または削除の方法</span><span class="sxs-lookup"><span data-stu-id="c331b-107">How artifacts (.NET assemblies and COM components) are added to or removed from the Windows Registry</span></span>  
  
-   <span data-ttu-id="c331b-108">グローバル アセンブリ キャッシュに対するアイテム (BizTalk アセンブリおよび .NET アセンブリ) のインストールまたはアンインストールの方法</span><span class="sxs-lookup"><span data-stu-id="c331b-108">How artifacts (BizTalk assemblies and .NET assemblies) are installed or uninstalled in the global assembly cache</span></span>  
  
-   <span data-ttu-id="c331b-109">ローカル証明書ストアへの証明書追加の方法</span><span class="sxs-lookup"><span data-stu-id="c331b-109">How certificates are added to the local certificate store</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c331b-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c331b-110">In This Section</span></span>  
  
-   [<span data-ttu-id="c331b-111">成果物の追加または削除されるときの動作します。</span><span class="sxs-lookup"><span data-stu-id="c331b-111">What Happens When Artifacts Are Added and Removed</span></span>](../core/what-happens-when-artifacts-are-added-and-removed.md)  
  
-   [<span data-ttu-id="c331b-112">アイテムのエクスポート時の動作します。</span><span class="sxs-lookup"><span data-stu-id="c331b-112">What Happens When Artifacts Are Exported</span></span>](../core/what-happens-when-artifacts-are-exported.md)  
  
-   [<span data-ttu-id="c331b-113">アイテムのインポート時の動作します。</span><span class="sxs-lookup"><span data-stu-id="c331b-113">What Happens When Artifacts Are Imported</span></span>](../core/what-happens-when-artifacts-are-imported.md)  
  
-   [<span data-ttu-id="c331b-114">インストールおよびアンインストール中にアイテムを処理します。</span><span class="sxs-lookup"><span data-stu-id="c331b-114">What Happens to Artifacts During Installation and Uninstallation</span></span>](../core/what-happens-to-artifacts-during-installation-and-uninstallation.md)