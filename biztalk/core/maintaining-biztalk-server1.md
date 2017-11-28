---
title: "BizTalk Server1 を維持する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: BizTalk Server, maintaining
ms.assetid: dd1e4497-839a-4686-b213-da100b6b5226
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56d1cb915a91136058a6c1d4a670416903e8aef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="maintaining-biztalk-server1"></a><span data-ttu-id="8225a-102">BizTalk Server1 を維持します。</span><span class="sxs-lookup"><span data-stu-id="8225a-102">Maintaining BizTalk Server1</span></span>
<span data-ttu-id="8225a-103">ここでは、BizTalk Server および Microsoft BizTalk Server データベースのバックアップおよび復元を行う方法、BizTalk 追跡 (BizTalkDTADb) データベースでのアーカイブおよび削除の方法、および移動することの多いいくつかの BizTalk Server データベースの移動方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8225a-103">This section provides information about how to back up and restore BizTalk Server and the Microsoft BizTalk Server databases, how to archive and purge data from the BizTalk Tracking (BizTalkDTADb) database, and how to move some of the more commonly moved BizTalk Server databases.</span></span> <span data-ttu-id="8225a-104">バックアップおよび復元のプロセスの概要および BizTalk 追跡データベース管理の推奨事項が示されています。</span><span class="sxs-lookup"><span data-stu-id="8225a-104">It provides an overview of the backup and restoration process, as well as recommendations for maintaining the BizTalk Tracking database.</span></span> <span data-ttu-id="8225a-105">テスト環境における BizTalk メッセージ ボックス データベースからの手動でのデータの削除について説明します。</span><span class="sxs-lookup"><span data-stu-id="8225a-105">It provides information on manually purging data from the BizTalk MessageBox database in a test environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8225a-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8225a-106">In This Section</span></span>  
  
-   [<span data-ttu-id="8225a-107">バックアップおよび BizTalk Server を復元します。</span><span class="sxs-lookup"><span data-stu-id="8225a-107">Backing Up and Restoring BizTalk Server</span></span>](../core/backing-up-and-restoring-biztalk-server.md)  
  
-   [<span data-ttu-id="8225a-108">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="8225a-108">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="8225a-109">BizTalk Server データベースの移動</span><span class="sxs-lookup"><span data-stu-id="8225a-109">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="8225a-110">テスト環境でメッセージ ボックス データベースからデータを手動で削除する方法</span><span class="sxs-lookup"><span data-stu-id="8225a-110">How to Manually Purge Data from the MessageBox Database in a Test Environment</span></span>](../core/how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment.md)