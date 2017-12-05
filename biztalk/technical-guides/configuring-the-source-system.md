---
title: "ソース システムの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 722dd52c-1eea-453c-9a36-9b8d9cf19350
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73f5d785c20d1390ae811d737e9169951e0270e7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-the-source-system"></a><span data-ttu-id="4a777-102">ソース システムを構成します。</span><span class="sxs-lookup"><span data-stu-id="4a777-102">Configuring the Source System</span></span>
<span data-ttu-id="4a777-103">BizTalk Server のログ配布のために、必要はありません、送信元システムは、1 つ上にある場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスまたはかどうかは、Windows Server クラスターでホストされている複数のインスタンス間で分散されます。</span><span class="sxs-lookup"><span data-stu-id="4a777-103">For the purposes of BizTalk Server log shipping, it does not matter if the source system is located on a single [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance or if it is distributed among multiple instances hosted in a Windows Server cluster.</span></span> <span data-ttu-id="4a777-104">BizTalk Server のバックアップ ジョブを正常に実行するために必要な追加の考慮事項はありません。</span><span class="sxs-lookup"><span data-stu-id="4a777-104">There are no additional considerations other than those required to successfully run the Backup BizTalk Server job.</span></span> <span data-ttu-id="4a777-105">このジョブを構成するのを参照してください。[を BizTalk Server のバックアップ ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=154072)(http://go.microsoft.com/fwlink/?LinkID=154072)、BizTalk Server のヘルプ。</span><span class="sxs-lookup"><span data-stu-id="4a777-105">To configure this job, see [How to Configure the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkID=154072) (http://go.microsoft.com/fwlink/?LinkID=154072) in BizTalk Server Help.</span></span> <span data-ttu-id="4a777-106">BizTalk Server のバックアップ ジョブを構成した後、トピックに進んで[を送信先システムを構成する方法](../technical-guides/how-to-configure-the-destination-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="4a777-106">After you have configured the Backup BizTalk Server Job, proceed to the topic [How to Configure the Destination System](../technical-guides/how-to-configure-the-destination-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a777-107">参照</span><span class="sxs-lookup"><span data-stu-id="4a777-107">See Also</span></span>  
 [<span data-ttu-id="4a777-108">BizTalk Server のログ配布の構成</span><span class="sxs-lookup"><span data-stu-id="4a777-108">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)