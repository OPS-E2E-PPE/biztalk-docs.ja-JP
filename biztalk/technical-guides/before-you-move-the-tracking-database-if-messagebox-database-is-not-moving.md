---
title: メッセージ ボックス データベースが移動されていない場合に、追跡データベースを移動する際の考慮事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee4066cb-da5b-4d04-a3b8-23fbf2d0c92a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecb2fcb6ad9ead42bd3e09c84a8895758d82293f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299922"
---
# <a name="considerations-when-moving-the-tracking-database-if-the-messagebox-database-is-not-being-moved"></a><span data-ttu-id="86279-102">メッセージ ボックス データベースが移動されていない場合に、追跡データベースを移動する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="86279-102">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>
<span data-ttu-id="86279-103">追跡データベース、メッセージ ボックス データベースではなく、SampleUpdateInfo.xml ファイルを編集するときに、以下のことを確認を移動する場合は、メッセージ ボックス データベースが移動されていない場合でも同様に、メッセージ ボックス データベースのエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="86279-103">If you are moving the Tracking database but not the MessageBox database, when you edit the SampleUpdateInfo.xml file, make sure that you include an entry for the MessageBox database as well, even though the MessageBox database is not being moved.</span></span> <span data-ttu-id="86279-104">これが行うことを確認する必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ TrackedMessages_Copy_BizTalkMsgBoxDb は新しい追跡データベースの場所で更新します。</span><span class="sxs-lookup"><span data-stu-id="86279-104">This must be done to ensure that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job TrackedMessages_Copy_BizTalkMsgBoxDb is updated with the location of the new Tracking database.</span></span>  
  
 <span data-ttu-id="86279-105">たとえば、SampleUpdateInfo.xml ファイルを追跡データベースのみがから移動中 OldServer NewServer にします。</span><span class="sxs-lookup"><span data-stu-id="86279-105">For example, in the following SampleUpdateInfo.xml file, only the Tracking database is being moved from OldServer to NewServer.</span></span> <span data-ttu-id="86279-106">メッセージ ボックス データベースは OldServer 上に保持しました。</span><span class="sxs-lookup"><span data-stu-id="86279-106">The MessageBox database is staying on OldServer:</span></span>  
  
```  
<UpdateConfiguration>  
     <MessageBoxDB oldDBName="BizTalkMgmtDb" oldDBServer="OldServer" newDBName="BizTalkMgmtDb" newDBServer="OldServer" IsMaster="1"/>  
     <TrackingDB oldDBName="BizTalkDTADB" oldDBServer="OldServer" newDBName="BizTalkDTADB" newDBServer="NewServer"/>  
     <OtherDatabases>  
     </OtherDatabases>  
</UpdateConfiguration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86279-107">参照</span><span class="sxs-lookup"><span data-stu-id="86279-107">See Also</span></span>  
 [<span data-ttu-id="86279-108">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="86279-108">Moving Databases</span></span>](../technical-guides/moving-databases.md)