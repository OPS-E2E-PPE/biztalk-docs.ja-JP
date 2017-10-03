---
title: "SQL Server の最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb735b54-595e-4dd0-9e4d-9a5e7a007a78
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3783c09b1155202ac8fe5a964d16c24d33082c26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sql-server-optimizations"></a><span data-ttu-id="3e82f-102">SQL Server の最適化</span><span class="sxs-lookup"><span data-stu-id="3e82f-102">SQL Server Optimizations</span></span>
<span data-ttu-id="3e82f-103">BizTalk Server は非常に高くデータベース処理を要するアプリケーションの SQL Server での最大 13 個のデータベースの作成が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e82f-103">BizTalk Server is an extremely database intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="3e82f-104">をメッセージが失われないことを確認するには BizTalk Server の主な設計目標の 1 つあるため、BizTalk Server は優れた頻度でデータをディスクが引き続き発生して、さらに、MSDTC トランザクションのコンテキスト内で処理が実行します。</span><span class="sxs-lookup"><span data-stu-id="3e82f-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="3e82f-105">そのため、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="3e82f-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
 <span data-ttu-id="3e82f-106">このセクションでは、BizTalk Server 環境に固有のデータベースのパフォーマンスを最大化するためのメソッドと同様に SQL Server のパフォーマンスを最大化するための一般的な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e82f-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="3e82f-107">データベースのパフォーマンスを最適化する BizTalk の詳細については、BizTalk データベースの最適化の TechNet の記事を参照してください[http://go.microsoft.com/fwlink/?LinkId=118001](http://go.microsoft.com/fwlink/?LinkId=118001)です。</span><span class="sxs-lookup"><span data-stu-id="3e82f-107">For additional information on optimizing BizTalk database performance, see the BizTalk Database Optimization TechNet article at [http://go.microsoft.com/fwlink/?LinkId=118001](http://go.microsoft.com/fwlink/?LinkId=118001).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e82f-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3e82f-108">In This Section</span></span>  
  
-   [<span data-ttu-id="3e82f-109">事前構成データベース Optimizations1</span><span class="sxs-lookup"><span data-stu-id="3e82f-109">Pre-Configuration Database Optimizations1</span></span>](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="3e82f-110">インストール後の構成データベース Optimizations1</span><span class="sxs-lookup"><span data-stu-id="3e82f-110">Post-Configuration Database Optimizations1</span></span>](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="3e82f-111">ファイル グループを Databases1 の最適化</span><span class="sxs-lookup"><span data-stu-id="3e82f-111">Optimizing Filegroups for the Databases1</span></span>](../technical-guides/optimizing-filegroups-for-the-databases1.md)