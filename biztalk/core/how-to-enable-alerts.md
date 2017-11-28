---
title: "アラートを有効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Enable-Alerts command [BAM]
- managing [BAM definitions], enabling alerts
- alerts, enabling
ms.assetid: 18f494b7-54fb-4aaf-89d1-7e3fe91f35c6
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22bb3610d489f02aa535b562057b4bb09e208983
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-alerts"></a><span data-ttu-id="4ffaa-102">警告を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="4ffaa-102">How to Enable Alerts</span></span>
<span data-ttu-id="4ffaa-103">管理者を使用して、**有効にするアラート**コマンドのすべての指定されたビューにアラートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ffaa-103">Administrators use the **enable-alerts** command to enable all of the alerts on the specified view.</span></span>  
  
### <a name="to-enable-an-alert"></a><span data-ttu-id="4ffaa-104">警告を有効にするには</span><span class="sxs-lookup"><span data-stu-id="4ffaa-104">To enable an alert</span></span>  
  
1.  <span data-ttu-id="4ffaa-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="4ffaa-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4ffaa-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="4ffaa-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="4ffaa-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4ffaa-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="4ffaa-108">型**bm 有効にするアラートの表示:\<ビュー名 >**です。</span><span class="sxs-lookup"><span data-stu-id="4ffaa-108">Type **bm enable-alerts -View:\<view name>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4ffaa-109">BAM 構成を XML としてエクスポートした場合は、警告に関連した XML を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="4ffaa-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="4ffaa-110">警告に関連した XML を変更し、その変更を配置した場合、bm.exe によって変更が検出され、BAM 警告が有効になります。</span><span class="sxs-lookup"><span data-stu-id="4ffaa-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4.  <span data-ttu-id="4ffaa-111">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4ffaa-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ffaa-112">参照</span><span class="sxs-lookup"><span data-stu-id="4ffaa-112">See Also</span></span>  
 <span data-ttu-id="4ffaa-113">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="4ffaa-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="4ffaa-114">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4ffaa-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="4ffaa-115">ここにリンクの説明を入力する</span><span class="sxs-lookup"><span data-stu-id="4ffaa-115">enter link description here</span></span>](../core/how-to-disable-alerts.md)