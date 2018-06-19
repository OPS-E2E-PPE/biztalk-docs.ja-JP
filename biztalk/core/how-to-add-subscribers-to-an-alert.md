---
title: 警告にサブスクライバーを追加する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 6e86bde9f47e04c17f62c3cacff5d779cf0bed56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247250"
---
# <a name="how-to-add-subscribers-to-an-alert"></a><span data-ttu-id="b1d09-102">サブスクライバーを警告に追加する方法</span><span class="sxs-lookup"><span data-stu-id="b1d09-102">How to Add Subscribers to an Alert</span></span>
<span data-ttu-id="b1d09-103">管理者を使用して、**サブスクリプションの追加**コマンドを指定した警告にサブスクライバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b1d09-103">Administrators use the **add-subscription** command to add a subscriber to a specified alert.</span></span>  
  
### <a name="to-add-subscribers-to-an-alert"></a><span data-ttu-id="b1d09-104">サブスクライバーを警告に追加するには</span><span class="sxs-lookup"><span data-stu-id="b1d09-104">To add subscribers to an alert</span></span>  
  
1.  <span data-ttu-id="b1d09-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="b1d09-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="b1d09-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="b1d09-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="b1d09-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b1d09-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="b1d09-108">「`bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`.</span><span class="sxs-lookup"><span data-stu-id="b1d09-108">Type `bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b1d09-109">*型*BAM を使用して、アラートを配信する配信方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1d09-109">*Type* specifies the delivery method which BAM uses to deliver the alert.</span></span> <span data-ttu-id="b1d09-110">配信方法として電子メールを指定した場合は、警告の配信先となる電子メール アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1d09-110">If you specify a delivery type of e-mail you must supply an e-mail address to which the alert is delivered.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b1d09-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1d09-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="b1d09-112">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b1d09-112">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d09-113">参照</span><span class="sxs-lookup"><span data-stu-id="b1d09-113">See Also</span></span>  
 <span data-ttu-id="b1d09-114">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="b1d09-114">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="b1d09-115">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b1d09-115">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="b1d09-116">サブスクライバーを警告から削除する方法</span><span class="sxs-lookup"><span data-stu-id="b1d09-116">How to Remove Subscribers from an Alert</span></span>](../core/how-to-remove-subscribers-from-an-alert.md)