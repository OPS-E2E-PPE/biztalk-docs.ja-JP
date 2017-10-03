---
title: "データベースのパフォーマンスの最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a95caf60-f1f5-458f-8a81-0aead88f07be
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe9148c5b14c5c915de9a8d16699856922e051a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-database-performance"></a><span data-ttu-id="c4a21-102">データベースのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="c4a21-102">Optimizing Database Performance</span></span>
<span data-ttu-id="c4a21-103">BizTalk Server は、SQL Server で最大 13 個のデータベースの作成を必要とするデータベースを非常に大量に消費するアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c4a21-103">BizTalk Server is an extremely database-intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="c4a21-104">をメッセージが失われないことを確認するには BizTalk Server の主な設計目標の 1 つあるため、BizTalk Server は優れた頻度でデータをディスクが引き続き発生して、さらに、MSDTC トランザクションのコンテキスト内で処理が実行します。</span><span class="sxs-lookup"><span data-stu-id="c4a21-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="c4a21-105">そのため、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="c4a21-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
 <span data-ttu-id="c4a21-106">このセクションでは、BizTalk Server 環境に固有のデータベースのパフォーマンスを最大化するためのメソッドと同様に SQL Server のパフォーマンスを最大化するための一般的な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4a21-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="c4a21-107">BizTalk データベースのパフォーマンスの最適化に関する詳細については、次を参照してください。、 [BizTalk データベースの最適化に関するホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578)。</span><span class="sxs-lookup"><span data-stu-id="c4a21-107">For additional information about optimizing BizTalk database performance, see the [BizTalk Database Optimization whitepaper](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4a21-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c4a21-108">In This Section</span></span>  
  
-   [<span data-ttu-id="c4a21-109">事前構成データベース Optimizations2</span><span class="sxs-lookup"><span data-stu-id="c4a21-109">Pre-Configuration Database Optimizations2</span></span>](../technical-guides/pre-configuration-database-optimizations2.md)  
  
-   [<span data-ttu-id="c4a21-110">インストール後の構成データベース Optimizations2</span><span class="sxs-lookup"><span data-stu-id="c4a21-110">Post-Configuration Database Optimizations2</span></span>](../technical-guides/post-configuration-database-optimizations2.md)  
  
-   [<span data-ttu-id="c4a21-111">ファイル グループを Databases2 の最適化</span><span class="sxs-lookup"><span data-stu-id="c4a21-111">Optimizing Filegroups for the Databases2</span></span>](../technical-guides/optimizing-filegroups-for-the-databases2.md)  
  
-   [<span data-ttu-id="c4a21-112">BizTalk Server メッセージ ボックス データベースのファイル グループの SQL スクリプト</span><span class="sxs-lookup"><span data-stu-id="c4a21-112">BizTalk Server MessageBox Database Filegroups SQL Script</span></span>](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)  
  
-   [<span data-ttu-id="c4a21-113">SQL Server のパフォーマンスの監視</span><span class="sxs-lookup"><span data-stu-id="c4a21-113">Monitoring SQL Server Performance</span></span>](../technical-guides/monitoring-sql-server-performance.md)