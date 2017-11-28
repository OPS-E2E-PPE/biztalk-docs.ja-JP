---
title: "アラートを無効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- alerts, disabling
- managing [BAM definitions], disabling alerts
- Disable-Alerts command [BAM]
ms.assetid: c5938bc2-1043-4633-8cad-02caf442f2e8
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0252fc98cdf792626094ffee75fae95c1cab3b00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-alerts"></a><span data-ttu-id="b9c3e-102">警告を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="b9c3e-102">How to Disable Alerts</span></span>
<span data-ttu-id="b9c3e-103">管理者を使用して、**無効にするアラート**のすべての指定されたビューにアラートを無効にするコマンド。</span><span class="sxs-lookup"><span data-stu-id="b9c3e-103">Administrators use the **disable-alerts** command to disable all of the alerts on the specified view.</span></span>  
  
### <a name="to-disable-an-alert"></a><span data-ttu-id="b9c3e-104">警告を無効にするには</span><span class="sxs-lookup"><span data-stu-id="b9c3e-104">To disable an alert</span></span>  
  
1.  <span data-ttu-id="b9c3e-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="b9c3e-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="b9c3e-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="b9c3e-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="b9c3e-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b9c3e-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="b9c3e-108">型**bm 無効にするアラートの表示:\<ビュー名 >**です。</span><span class="sxs-lookup"><span data-stu-id="b9c3e-108">Type **bm disable-alerts -View:\<view name>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b9c3e-109">BAM 構成を XML としてエクスポートした場合は、警告に関連した XML を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="b9c3e-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="b9c3e-110">警告に関連した XML を変更し、その変更を配置した場合、bm.exe によって変更が検出され、BAM 警告が有効になります。</span><span class="sxs-lookup"><span data-stu-id="b9c3e-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4.  <span data-ttu-id="b9c3e-111">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b9c3e-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c3e-112">参照</span><span class="sxs-lookup"><span data-stu-id="b9c3e-112">See Also</span></span>  
 <span data-ttu-id="b9c3e-113">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="b9c3e-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="b9c3e-114">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b9c3e-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="b9c3e-115">アラートを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="b9c3e-115">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md)