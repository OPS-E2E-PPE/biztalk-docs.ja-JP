---
title: BAM イベント バス サービスのストアド プロシージャ |Microsoft Docs
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
ms.openlocfilehash: 138ca26becc8b35207219dd050e13c8557066301
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358523"
---
# <a name="bam-event-bus-service-stored-procedures"></a><span data-ttu-id="77b42-102">BAM イベント バス サービスのストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="77b42-102">BAM Event Bus Service Stored Procedures</span></span>
<span data-ttu-id="77b42-103">BAM イベント バス サービスを管理するのにには、次のストアド プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="77b42-103">You use the following stored procedures to manage the BAM Event Bus service:</span></span>  
  
-   <span data-ttu-id="77b42-104">BAM イベント バス サービスを一時停止するには、BAM データベースで (トランザクションのコミット) なしのトランザクション内でに対して TDDS_BlockTDDS ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="77b42-104">To pause the BAM Event Bus service, execute the TDDS_BlockTDDS stored procedure within a transaction (without committing the transaction) on the BAM database.</span></span> <span data-ttu-id="77b42-105">BAM イベント バス サービスを再開するには、TDDS_BlockTDDS トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="77b42-105">To resume the BAM Event Bus service, commit the TDDS_BlockTDDS transaction.</span></span>  
  
-   <span data-ttu-id="77b42-106">複数のコンピューターで BAM イベント バス サービスを有効にするには、追跡に使用するホストを特定し、追跡ホストにこれらのコンピューターを参加します。</span><span class="sxs-lookup"><span data-stu-id="77b42-106">To enable the BAM Event Bus service on multiple computers, identify which host(s) to use for tracking, and then join those computers to the tracking host.</span></span>  
  
-   <span data-ttu-id="77b42-107">セッション タイムアウトと heartbeat 間隔を設定するには、TDDS_UpdateSettings ストアド プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="77b42-107">To set up a session time-out and heartbeat interval, use the TDDS_UpdateSettings stored procedure.</span></span> <span data-ttu-id="77b42-108">BTS_ADMIN_USERS グループのメンバーだけでは、このストアド プロシージャを実行する権限があります。</span><span class="sxs-lookup"><span data-stu-id="77b42-108">Only members of the BTS_ADMIN_USERS group have permission to execute this stored procedure.</span></span>  
  
     <span data-ttu-id="77b42-109">TDDS_UpdateSettings ストアド プロシージャでは、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="77b42-109">The TDDS_UpdateSettings stored procedure has the following parameters:</span></span>  
  
    -   <span data-ttu-id="77b42-110">@RefreshInterval int です。60 秒以上に設定します。</span><span class="sxs-lookup"><span data-stu-id="77b42-110">@RefreshInterval int. Set to greater than 60 seconds.</span></span>  
  
    -   <span data-ttu-id="77b42-111">@SqlCommandTimeout int です。RefreshInterval よりも小さくを設定します。</span><span class="sxs-lookup"><span data-stu-id="77b42-111">@SqlCommandTimeout int. Set to less than RefreshInterval.</span></span>  
  
    -   <span data-ttu-id="77b42-112">@SessionTimeout int です。RefreshInterval の 2 倍よりも大きい値に設定します。</span><span class="sxs-lookup"><span data-stu-id="77b42-112">@SessionTimeout int. Set to greater than two times the RefreshInterval.</span></span>  
  
    -   <span data-ttu-id="77b42-113">@EventLoggingInterval nvarchar (16)。</span><span class="sxs-lookup"><span data-stu-id="77b42-113">@EventLoggingInterval nvarchar(16).</span></span> <span data-ttu-id="77b42-114">60 秒以上に設定します。</span><span class="sxs-lookup"><span data-stu-id="77b42-114">Set to greater than 60 seconds.</span></span>  
  
    -   <span data-ttu-id="77b42-115">@RetryCount int です。60 秒以上に設定します。</span><span class="sxs-lookup"><span data-stu-id="77b42-115">@RetryCount int. Set to greater than 60 seconds</span></span>  
  
    -   <span data-ttu-id="77b42-116">@ThreadPerSession int です。このパラメーターは廃止されています。</span><span class="sxs-lookup"><span data-stu-id="77b42-116">@ThreadPerSession int. This parameter is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77b42-117">参照</span><span class="sxs-lookup"><span data-stu-id="77b42-117">See Also</span></span>  
 [<span data-ttu-id="77b42-118">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="77b42-118">Managing BAM</span></span>](../core/managing-bam.md)