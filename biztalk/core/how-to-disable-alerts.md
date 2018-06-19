---
title: アラートを無効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- alerts, disabling
- managing [BAM definitions], disabling alerts
- Disable-Alerts command [BAM]
ms.assetid: c5938bc2-1043-4633-8cad-02caf442f2e8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4279030b9c3bcc7913bf64cc870b0d82d618dff8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969264"
---
# <a name="how-to-disable-alerts"></a><span data-ttu-id="4a5a0-102">警告を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="4a5a0-102">How to Disable Alerts</span></span>
<span data-ttu-id="4a5a0-103">管理者を使用して、**無効にするアラート**のすべての指定されたビューにアラートを無効にするコマンド。</span><span class="sxs-lookup"><span data-stu-id="4a5a0-103">Administrators use the **disable-alerts** command to disable all of the alerts on the specified view.</span></span>  
  
### <a name="to-disable-an-alert"></a><span data-ttu-id="4a5a0-104">警告を無効にするには</span><span class="sxs-lookup"><span data-stu-id="4a5a0-104">To disable an alert</span></span>  
  
1.  <span data-ttu-id="4a5a0-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="4a5a0-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4a5a0-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="4a5a0-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="4a5a0-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4a5a0-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="4a5a0-108">型**bm 無効にするアラートの表示:\<ビュー名\>** です。</span><span class="sxs-lookup"><span data-stu-id="4a5a0-108">Type **bm disable-alerts -View:\<view name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4a5a0-109">BAM 構成を XML としてエクスポートした場合は、警告に関連した XML を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="4a5a0-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="4a5a0-110">警告に関連した XML を変更し、その変更を配置した場合、bm.exe によって変更が検出され、BAM 警告が有効になります。</span><span class="sxs-lookup"><span data-stu-id="4a5a0-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4.  <span data-ttu-id="4a5a0-111">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4a5a0-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a5a0-112">参照</span><span class="sxs-lookup"><span data-stu-id="4a5a0-112">See Also</span></span>  
 <span data-ttu-id="4a5a0-113">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="4a5a0-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="4a5a0-114">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4a5a0-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="4a5a0-115">アラートを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="4a5a0-115">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md)