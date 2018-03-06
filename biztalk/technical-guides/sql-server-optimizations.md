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
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36317d99387fde1d7b5e1c56b45255129daedb25
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="sql-server-optimizations"></a><span data-ttu-id="51f11-102">SQL Server の最適化</span><span class="sxs-lookup"><span data-stu-id="51f11-102">SQL Server Optimizations</span></span>
<span data-ttu-id="51f11-103">BizTalk Server は非常に高くデータベース処理を要するアプリケーションの SQL Server での最大 13 個のデータベースの作成が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="51f11-103">BizTalk Server is an extremely database intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="51f11-104">をメッセージが失われないことを確認するには BizTalk Server の主な設計目標の 1 つあるため、BizTalk Server は優れた頻度でデータをディスクが引き続き発生して、さらに、MSDTC トランザクションのコンテキスト内で処理が実行します。</span><span class="sxs-lookup"><span data-stu-id="51f11-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="51f11-105">そのため、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="51f11-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
<span data-ttu-id="51f11-106">このセクションでは、BizTalk Server 環境に固有のデータベースのパフォーマンスを最大化するためのメソッドと同様に SQL Server のパフォーマンスを最大化するための一般的な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="51f11-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="51f11-107">次のリンクも優れたリソース。</span><span class="sxs-lookup"><span data-stu-id="51f11-107">The following links are also good resources:</span></span> 

- [<span data-ttu-id="51f11-108">インストール、サイズ変更、配置、およびソリューションを維持するための BizTalk サーバー: 推奨事項</span><span class="sxs-lookup"><span data-stu-id="51f11-108">BizTalk Server: Recommendations for Installing, Sizing, Deploying, and Maintaining a Solution</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/666.biztalk-server-recommendations-for-installing-sizing-deploying-and-maintaining-a-solution.aspx)

- [<span data-ttu-id="51f11-109">BizTalk Server Performance Optimization Guide</span><span class="sxs-lookup"><span data-stu-id="51f11-109">BizTalk Server Performance Optimization Guide</span></span>](biztalk-server-2013-performance-optimization-guide.md)

  
## <a name="next-steps"></a><span data-ttu-id="51f11-110">次の手順</span><span class="sxs-lookup"><span data-stu-id="51f11-110">Next steps</span></span>
  
-   [<span data-ttu-id="51f11-111">構成前のデータベースの最適化</span><span class="sxs-lookup"><span data-stu-id="51f11-111">Pre-Configuration Database Optimizations</span></span>](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="51f11-112">構成後のデータベースの最適化</span><span class="sxs-lookup"><span data-stu-id="51f11-112">Post-Configuration Database Optimizations</span></span>](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="51f11-113">データベースのファイルグループの最適化</span><span class="sxs-lookup"><span data-stu-id="51f11-113">Optimizing Filegroups for the Databases</span></span>](../technical-guides/optimizing-filegroups-for-the-databases1.md)