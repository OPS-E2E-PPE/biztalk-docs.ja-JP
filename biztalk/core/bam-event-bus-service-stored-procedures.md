---
title: BAM イベント バス サービスのストアド プロシージャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- stored procedures, Even Bus Service [BAM]
- Event Bus Service [BAM], stored procedures
ms.assetid: 18a7bd40-50ce-44f2-88ae-45a2e3c8d3f4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44dce10113b8a3a85b7c1dd177f637933b582ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230338"
---
# <a name="bam-event-bus-service-stored-procedures"></a><span data-ttu-id="61b98-102">BAM イベント バス サービスのストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="61b98-102">BAM Event Bus Service Stored Procedures</span></span>
<span data-ttu-id="61b98-103">BAM イベント バス サービスの管理には、次のストアド プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="61b98-103">You use the following stored procedures to manage the BAM Event Bus service:</span></span>  
  
-   <span data-ttu-id="61b98-104">BAM イベント バス サービスを一時停止するには、(トランザクションをコミットせずに) トランザクション内で BAM データベースに対して TDDS_BlockTDDS ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="61b98-104">To pause the BAM Event Bus service, execute the TDDS_BlockTDDS stored procedure within a transaction (without committing the transaction) on the BAM database.</span></span> <span data-ttu-id="61b98-105">BAM イベント バス サービスを再開するには、TDDS_BlockTDDS トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="61b98-105">To resume the BAM Event Bus service, commit the TDDS_BlockTDDS transaction.</span></span>  
  
-   <span data-ttu-id="61b98-106">複数のコンピューターで BAM イベント バス サービスを有効にするには、追跡に使用するホストを特定し、有効にする複数のコンピューターを追跡ホストに参加させます。</span><span class="sxs-lookup"><span data-stu-id="61b98-106">To enable the BAM Event Bus service on multiple computers, identify which host(s) to use for tracking, and then join those computers to the tracking host.</span></span>  
  
-   <span data-ttu-id="61b98-107">セッションのタイムアウトと Heartbeat 間隔を設定するには、TDDS_UpdateSettings ストアド プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="61b98-107">To set up a session time-out and heartbeat interval, use the TDDS_UpdateSettings stored procedure.</span></span> <span data-ttu-id="61b98-108">このストアド プロシージャの実行権限は、BTS_ADMIN_USERS グループのメンバーのみに与えられています。</span><span class="sxs-lookup"><span data-stu-id="61b98-108">Only members of the BTS_ADMIN_USERS group have permission to execute this stored procedure.</span></span>  
  
     <span data-ttu-id="61b98-109">TDDS_UpdateSettings ストアド プロシージャには、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="61b98-109">The TDDS_UpdateSettings stored procedure has the following parameters:</span></span>  
  
    -   <span data-ttu-id="61b98-110">@RefreshIntervalint です。60 秒を超える値を設定します。</span><span class="sxs-lookup"><span data-stu-id="61b98-110">@RefreshInterval int. Set to greater than 60 seconds.</span></span>  
  
    -   <span data-ttu-id="61b98-111">@SqlCommandTimeoutint です。RefreshInterval よりも低くを設定します。</span><span class="sxs-lookup"><span data-stu-id="61b98-111">@SqlCommandTimeout int. Set to less than RefreshInterval.</span></span>  
  
    -   <span data-ttu-id="61b98-112">@SessionTimeoutint です。RefreshInterval の 2 倍よりも大きい値に設定します。</span><span class="sxs-lookup"><span data-stu-id="61b98-112">@SessionTimeout int. Set to greater than two times the RefreshInterval.</span></span>  
  
    -   <span data-ttu-id="61b98-113">@EventLoggingIntervalnvarchar (16)。</span><span class="sxs-lookup"><span data-stu-id="61b98-113">@EventLoggingInterval nvarchar(16).</span></span> <span data-ttu-id="61b98-114">60 秒を超える値を設定します。</span><span class="sxs-lookup"><span data-stu-id="61b98-114">Set to greater than 60 seconds.</span></span>  
  
    -   <span data-ttu-id="61b98-115">@RetryCountint です。60 秒より大きい値に設定します。</span><span class="sxs-lookup"><span data-stu-id="61b98-115">@RetryCount int. Set to greater than 60 seconds</span></span>  
  
    -   <span data-ttu-id="61b98-116">@ThreadPerSessionint です。このパラメーターは今後使用しません。</span><span class="sxs-lookup"><span data-stu-id="61b98-116">@ThreadPerSession int. This parameter is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b98-117">参照</span><span class="sxs-lookup"><span data-stu-id="61b98-117">See Also</span></span>  
 [<span data-ttu-id="61b98-118">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="61b98-118">Managing BAM</span></span>](../core/managing-bam.md)