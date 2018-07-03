---
title: 警告にサブスクライバーを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- subscriptions
- managing [BAM], adding alert subscribers
ms.assetid: c76a117d-4516-4f48-995c-7e018dbba755
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0174d5f37bc34b6c882d82cb58192ce9f1d634d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972619"
---
# <a name="how-to-add-subscribers-to-an-alert"></a><span data-ttu-id="5af42-102">サブスクライバーを警告に追加する方法</span><span class="sxs-lookup"><span data-stu-id="5af42-102">How to Add Subscribers to an Alert</span></span>
<span data-ttu-id="5af42-103">管理者を使用して、**サブスクリプションの追加**コマンドを指定した警告にサブスクライバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5af42-103">Administrators use the **add-subscription** command to add a subscriber to a specified alert.</span></span>  
  
### <a name="to-add-subscribers-to-an-alert"></a><span data-ttu-id="5af42-104">サブスクライバーを警告に追加するには</span><span class="sxs-lookup"><span data-stu-id="5af42-104">To add subscribers to an alert</span></span>  
  
1. <span data-ttu-id="5af42-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="5af42-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="5af42-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="5af42-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="5af42-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5af42-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="5af42-108">「`bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`.</span><span class="sxs-lookup"><span data-stu-id="5af42-108">Type `bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5af42-109">*型*BAM を使用して警告を配信する配信方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="5af42-109">*Type* specifies the delivery method which BAM uses to deliver the alert.</span></span> <span data-ttu-id="5af42-110">配信方法として電子メールを指定した場合は、警告の配信先となる電子メール アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5af42-110">If you specify a delivery type of e-mail you must supply an e-mail address to which the alert is delivered.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5af42-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5af42-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="5af42-112">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5af42-112">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af42-113">参照</span><span class="sxs-lookup"><span data-stu-id="5af42-113">See Also</span></span>  
 <span data-ttu-id="5af42-114">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="5af42-114">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="5af42-115">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="5af42-115">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="5af42-116">サブスクライバーを警告から削除する方法</span><span class="sxs-lookup"><span data-stu-id="5af42-116">How to Remove Subscribers from an Alert</span></span>](../core/how-to-remove-subscribers-from-an-alert.md)