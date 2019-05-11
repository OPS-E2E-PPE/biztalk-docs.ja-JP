---
title: ソース システムの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 722dd52c-1eea-453c-9a36-9b8d9cf19350
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f24203978015577128f2c1159c8bf88697a22f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253521"
---
# <a name="configuring-the-source-system"></a><span data-ttu-id="ccb35-102">ソース システムの構成</span><span class="sxs-lookup"><span data-stu-id="ccb35-102">Configuring the Source System</span></span>
<span data-ttu-id="ccb35-103">BizTalk Server ログ配布のためには、関係ありませんが、ソース システムを 1 つにある場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスまたは Windows Server クラスターでホストされている複数のインスタンスが分散されてかどうか。</span><span class="sxs-lookup"><span data-stu-id="ccb35-103">For the purposes of BizTalk Server log shipping, it does not matter if the source system is located on a single [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance or if it is distributed among multiple instances hosted in a Windows Server cluster.</span></span> <span data-ttu-id="ccb35-104">BizTalk Server のバックアップ ジョブを正常に実行するために必要なもの以外の追加の考慮事項はありません。</span><span class="sxs-lookup"><span data-stu-id="ccb35-104">There are no additional considerations other than those required to successfully run the Backup BizTalk Server job.</span></span> <span data-ttu-id="ccb35-105">このジョブを構成するを参照してください。 [Backup BizTalk Server ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=154072)(<http://go.microsoft.com/fwlink/?LinkID=154072>) BizTalk Server のヘルプ。</span><span class="sxs-lookup"><span data-stu-id="ccb35-105">To configure this job, see [How to Configure the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkID=154072) (<http://go.microsoft.com/fwlink/?LinkID=154072>) in BizTalk Server Help.</span></span> <span data-ttu-id="ccb35-106">BizTalk Server のバックアップのジョブを構成した後は、トピックに進みます[送信先システムを構成する方法](../technical-guides/how-to-configure-the-destination-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="ccb35-106">After you have configured the Backup BizTalk Server Job, proceed to the topic [How to Configure the Destination System](../technical-guides/how-to-configure-the-destination-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb35-107">参照</span><span class="sxs-lookup"><span data-stu-id="ccb35-107">See Also</span></span>  
 [<span data-ttu-id="ccb35-108">BizTalk Server のログ配布の構成</span><span class="sxs-lookup"><span data-stu-id="ccb35-108">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)