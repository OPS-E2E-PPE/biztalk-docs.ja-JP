---
title: アプリケーション展開中にアイテムの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, deploying
- deploying [artifacts]
ms.assetid: afd77251-c3bd-454b-907f-a841911abe47
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa1bf277a482e6504af6d791c87b76d9bc878653
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302313"
---
# <a name="what-happens-to-artifacts-during-application-deployment"></a><span data-ttu-id="2efcc-102">アプリケーション展開時のアイテムの処理</span><span class="sxs-lookup"><span data-stu-id="2efcc-102">What Happens to Artifacts During Application Deployment</span></span>
<span data-ttu-id="2efcc-103">このセクションのトピックでは、アイテムの追加と削除、アプリケーションやアイテムのエクスポートとインポート、およびアプリケーションのインストールとアンインストールを行う場合に、アプリケーションに関連付けられたアイテムに対して行われる処理について説明します。</span><span class="sxs-lookup"><span data-stu-id="2efcc-103">The topics in this section describe what happens to the artifacts associated with an application when you add and remove artifacts, export and import applications and artifacts, and install and uninstall applications.</span></span> <span data-ttu-id="2efcc-104">説明の内容として、次の項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2efcc-104">It covers subjects such as the following:</span></span>  
  
-   <span data-ttu-id="2efcc-105">BizTalk Server データベースに対するアイテムの追加および削除の方法</span><span class="sxs-lookup"><span data-stu-id="2efcc-105">How artifacts are added to and removed from the BizTalk Server databases</span></span>  
  
-   <span data-ttu-id="2efcc-106">ローカル ファイル システムに対するアイテムのコピーおよび削除の方法</span><span class="sxs-lookup"><span data-stu-id="2efcc-106">How artifacts are copied to and deleted from the local file system</span></span>  
  
-   <span data-ttu-id="2efcc-107">Windows レジストリに対するアイテム (.NET アセンブリおよび COM コンポーネント) の追加または削除の方法</span><span class="sxs-lookup"><span data-stu-id="2efcc-107">How artifacts (.NET assemblies and COM components) are added to or removed from the Windows Registry</span></span>  
  
-   <span data-ttu-id="2efcc-108">グローバル アセンブリ キャッシュに対するアイテム (BizTalk アセンブリおよび .NET アセンブリ) のインストールまたはアンインストールの方法</span><span class="sxs-lookup"><span data-stu-id="2efcc-108">How artifacts (BizTalk assemblies and .NET assemblies) are installed or uninstalled in the global assembly cache</span></span>  
  
-   <span data-ttu-id="2efcc-109">ローカル証明書ストアへの証明書追加の方法</span><span class="sxs-lookup"><span data-stu-id="2efcc-109">How certificates are added to the local certificate store</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2efcc-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2efcc-110">In This Section</span></span>  
  
-   [<span data-ttu-id="2efcc-111">アイテムを追加または削除した場合の動作</span><span class="sxs-lookup"><span data-stu-id="2efcc-111">What Happens When Artifacts Are Added and Removed</span></span>](../core/what-happens-when-artifacts-are-added-and-removed.md)  
  
-   [<span data-ttu-id="2efcc-112">アイテムのエクスポート時の動作</span><span class="sxs-lookup"><span data-stu-id="2efcc-112">What Happens When Artifacts Are Exported</span></span>](../core/what-happens-when-artifacts-are-exported.md)  
  
-   [<span data-ttu-id="2efcc-113">アイテムのインポート時の動作</span><span class="sxs-lookup"><span data-stu-id="2efcc-113">What Happens When Artifacts Are Imported</span></span>](../core/what-happens-when-artifacts-are-imported.md)  
  
-   [<span data-ttu-id="2efcc-114">インストールおよびアンインストール時のアイテムの処理</span><span class="sxs-lookup"><span data-stu-id="2efcc-114">What Happens to Artifacts During Installation and Uninstallation</span></span>](../core/what-happens-to-artifacts-during-installation-and-uninstallation.md)