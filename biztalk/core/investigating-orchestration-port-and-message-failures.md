---
title: オーケストレーション、ポート、およびメッセージのエラーを調査 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Administration Console [BizTalk Server], Group Hub page
- orchestrations, errors
- errors, ports
- errors, orchestrations
- Group Hub page [Administration Console]
- ports, errors
- MessageBox database, accessing data
- errors, messages
- messages, errors
- data, MessageBox database
ms.assetid: 50b0d272-2d48-4e0f-82ce-6ecc7a65b064
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94417135f707d77377686745e35e6fb1f02087b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262306"
---
# <a name="investigating-orchestration-port-and-message-failures"></a><span data-ttu-id="d224e-102">オーケストレーション、ポート、およびメッセージのエラーの調査</span><span class="sxs-lookup"><span data-stu-id="d224e-102">Investigating Orchestration, Port, and Message Failures</span></span>
<span data-ttu-id="d224e-103">オーケストレーション、ポート、およびメッセージのエラーを調査するには、BizTalk Server 2006 管理コンソールのグループ ハブ ページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d224e-103">You can use the Group Hub page in the BizTalk Server Administration Console to investigate orchestration, port, and message failures.</span></span> <span data-ttu-id="d224e-104">グループ ハブ ページでは、メッセージ ボックス データベース内のデータにアクセスすることで、現在のシステムのリアルタイムの状態にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d224e-104">The Group Hub page provides access to the current real-time state of the system, accessing data in the MessageBox database.</span></span> <span data-ttu-id="d224e-105">オーケストレーション、ポート、メッセージングなどのすべてのサービス インスタンスと、それに関連するメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d224e-105">You can view all service instances such as orchestrations, ports, and messaging, along with their associated messages.</span></span> <span data-ttu-id="d224e-106">グループ ハブ ページでは、次の操作を行えます。</span><span class="sxs-lookup"><span data-stu-id="d224e-106">Using the Group Hub page you can:</span></span>  
  
-   <span data-ttu-id="d224e-107">オーケストレーションやメッセージングなどの現在実行中のサービス インスタンス、およびそれに関連するメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="d224e-107">See currently running service instances such as orchestrations and messaging, and their associated messages.</span></span>  
  
-   <span data-ttu-id="d224e-108">現在のデータおよびシステムのリアルタイムの状態について、メッセージ ボックス データベースを調べます。</span><span class="sxs-lookup"><span data-stu-id="d224e-108">Look into the MessageBox database for a view of the current data and the real-time state of the system.</span></span>  
  
-   <span data-ttu-id="d224e-109">サービス インスタンスを中断、終了、および再開します。</span><span class="sxs-lookup"><span data-stu-id="d224e-109">Suspend, terminate, and resume service instances.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d224e-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d224e-110">In This Section</span></span>  
  
-   [<span data-ttu-id="d224e-111">オーケストレーション エラー</span><span class="sxs-lookup"><span data-stu-id="d224e-111">Orchestration Failures</span></span>](../core/orchestration-failures.md)  
  
-   [<span data-ttu-id="d224e-112">メッセージ エラーの種類</span><span class="sxs-lookup"><span data-stu-id="d224e-112">Types of Message Failures</span></span>](../core/types-of-message-failures.md)  
  
-   [<span data-ttu-id="d224e-113">オーケストレーションのインスタンスまたはポートを中断する方法</span><span class="sxs-lookup"><span data-stu-id="d224e-113">How to Suspend Orchestration Instances or Ports</span></span>](../core/how-to-suspend-orchestration-instances-or-ports.md)  
  
-   [<span data-ttu-id="d224e-114">中断したオーケストレーション インスタンスを終了する方法</span><span class="sxs-lookup"><span data-stu-id="d224e-114">How to Terminate Suspended Orchestration Instances</span></span>](../core/how-to-terminate-suspended-orchestration-instances.md)  
  
-   [<span data-ttu-id="d224e-115">中断したオーケストレーション インスタンスを再開する方法</span><span class="sxs-lookup"><span data-stu-id="d224e-115">How to Resume Suspended Orchestration Instances</span></span>](../core/how-to-resume-suspended-orchestration-instances.md)