---
title: アラートを有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enable-Alerts command [BAM]
- managing [BAM definitions], enabling alerts
- alerts, enabling
ms.assetid: 18f494b7-54fb-4aaf-89d1-7e3fe91f35c6
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75242921113152b45c17f139c24a4afc87ac7451
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338002"
---
# <a name="how-to-enable-alerts"></a><span data-ttu-id="73552-102">警告を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="73552-102">How to Enable Alerts</span></span>
<span data-ttu-id="73552-103">管理者を使用して、**有効にするアラート**コマンドを指定されたビューにアラートをすべて有効にします。</span><span class="sxs-lookup"><span data-stu-id="73552-103">Administrators use the **enable-alerts** command to enable all of the alerts on the specified view.</span></span>  
  
### <a name="to-enable-an-alert"></a><span data-ttu-id="73552-104">アラートを有効にするには</span><span class="sxs-lookup"><span data-stu-id="73552-104">To enable an alert</span></span>  
  
1. <span data-ttu-id="73552-105">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="73552-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="73552-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="73552-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="73552-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="73552-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="73552-108">型**bm 有効にするアラートの表示:\<ビュー名\>** します。</span><span class="sxs-lookup"><span data-stu-id="73552-108">Type **bm enable-alerts -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="73552-109">BAM 構成を XML としてエクスポートしている場合は、アラートに関連する XML を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="73552-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="73552-110">アラートに関連する XML を変更し、変更を配置する場合、bm.exe は変更が検出され、BAM 警告を有効にします。</span><span class="sxs-lookup"><span data-stu-id="73552-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4. <span data-ttu-id="73552-111">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="73552-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73552-112">参照</span><span class="sxs-lookup"><span data-stu-id="73552-112">See Also</span></span>  
 <span data-ttu-id="73552-113">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="73552-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="73552-114">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="73552-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="73552-115">ここにリンクの説明を入力する</span><span class="sxs-lookup"><span data-stu-id="73552-115">enter link description here</span></span>](../core/how-to-disable-alerts.md)