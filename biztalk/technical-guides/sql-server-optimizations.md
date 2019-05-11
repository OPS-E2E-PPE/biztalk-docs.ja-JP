---
title: SQL Server の最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb735b54-595e-4dd0-9e4d-9a5e7a007a78
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a84b6ec1a2c5febb4f0aafdde3f82f8c4afe1962
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313255"
---
# <a name="sql-server-optimizations"></a><span data-ttu-id="ed0ae-102">SQL Server の最適化</span><span class="sxs-lookup"><span data-stu-id="ed0ae-102">SQL Server Optimizations</span></span>
<span data-ttu-id="ed0ae-103">BizTalk Server は、非常にデータベース処理を要するアプリケーションで SQL Server の最大 13 個のデータベースを作成することがあります。</span><span class="sxs-lookup"><span data-stu-id="ed0ae-103">BizTalk Server is an extremely database intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="ed0ae-104">メッセージが失われたしないことを確認します。 BizTalk Server の主な設計目標の 1 つは、BizTalk Server は優れた頻度でデータをディスクが引き続き発生して、さらに、MSDTC トランザクションのコンテキスト内では。</span><span class="sxs-lookup"><span data-stu-id="ed0ae-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="ed0ae-105">したがって、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="ed0ae-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
<span data-ttu-id="ed0ae-106">このセクションでは、BizTalk Server 環境に固有のデータベースのパフォーマンスを最大化するためのメソッドと同様に SQL Server のパフォーマンスを最大化するための一般的な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed0ae-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="ed0ae-107">次のリンクも優れたリソース。</span><span class="sxs-lookup"><span data-stu-id="ed0ae-107">The following links are also good resources:</span></span> 

- [<span data-ttu-id="ed0ae-108">BizTalk Server:インストール、サイズ変更、展開、およびソリューションを維持するための推奨事項</span><span class="sxs-lookup"><span data-stu-id="ed0ae-108">BizTalk Server: Recommendations for Installing, Sizing, Deploying, and Maintaining a Solution</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/666.biztalk-server-recommendations-for-installing-sizing-deploying-and-maintaining-a-solution.aspx)

- [<span data-ttu-id="ed0ae-109">BizTalk Server のパフォーマンス最適化ガイド</span><span class="sxs-lookup"><span data-stu-id="ed0ae-109">BizTalk Server Performance Optimization Guide</span></span>](biztalk-server-2013-performance-optimization-guide.md)

  
## <a name="next-steps"></a><span data-ttu-id="ed0ae-110">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ed0ae-110">Next steps</span></span>
  
-   [<span data-ttu-id="ed0ae-111">構成前のデータベースの最適化</span><span class="sxs-lookup"><span data-stu-id="ed0ae-111">Pre-Configuration Database Optimizations</span></span>](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="ed0ae-112">構成後のデータベースの最適化</span><span class="sxs-lookup"><span data-stu-id="ed0ae-112">Post-Configuration Database Optimizations</span></span>](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="ed0ae-113">データベースのファイルグループの最適化</span><span class="sxs-lookup"><span data-stu-id="ed0ae-113">Optimizing Filegroups for the Databases</span></span>](../technical-guides/optimizing-filegroups-for-the-databases1.md)