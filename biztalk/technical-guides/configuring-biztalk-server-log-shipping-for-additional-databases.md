---
title: BizTalk ログの配布を他のデータベースの構成 |Microsoft ドキュメント
description: BizTalk Server のバックアップ ジョブ、および BizTalk Server でのログ配布にカスタム データベースを追加します。
ms.custom: ''
ms.date: 11/01/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fc2ae67-5cb9-4d53-9bf7-c88f84914960
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b1ceb760a5f842f8c24a372d793e0074114b81f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976536"
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a><span data-ttu-id="29634-103">BizTalk Server に対してログ配布を他のデータベースを構成します。</span><span class="sxs-lookup"><span data-stu-id="29634-103">Configuring BizTalk Server Log Shipping for Additional Databases</span></span>

## <a name="overview"></a><span data-ttu-id="29634-104">概要</span><span class="sxs-lookup"><span data-stu-id="29634-104">Overview</span></span>
<span data-ttu-id="29634-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、BizTalk Server のバックアップ ジョブに追加するジョブは自動的に追加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布します。</span><span class="sxs-lookup"><span data-stu-id="29634-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], jobs added to the Backup BizTalk Server job are automatically added to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="29634-106">BizTalk Server のバックアップ ジョブに追加される新しいデータベースのログ配布を構成する追加の手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="29634-106">You do not have to take additional steps to configure log shipping for new databases added to the Backup BizTalk Server job.</span></span> <span data-ttu-id="29634-107">ただし、下にある適切なカスタム データベースを追加するようにして、 \<OtherDatabases\> SampleUpdateInfo.xml ファイルのセクションです。</span><span class="sxs-lookup"><span data-stu-id="29634-107">However, be sure to add custom databases as appropriate under the \<OtherDatabases\> section of the SampleUpdateInfo.xml file.</span></span> <span data-ttu-id="29634-108">[ログ配布の送信先システムを構成する](../core/how-to-configure-the-destination-system-for-log-shipping.md)と[カスタム データベースを戻す](../core/how-to-back-up-custom-databases.md)のガイダンスを紹介します。</span><span class="sxs-lookup"><span data-stu-id="29634-108">[Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) and [Back Up Custom Databases](../core/how-to-back-up-custom-databases.md) provides some guidance.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="29634-109">参照</span><span class="sxs-lookup"><span data-stu-id="29634-109">See Also</span></span>  
 [<span data-ttu-id="29634-110">BizTalk Server のログ配布の構成</span><span class="sxs-lookup"><span data-stu-id="29634-110">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)