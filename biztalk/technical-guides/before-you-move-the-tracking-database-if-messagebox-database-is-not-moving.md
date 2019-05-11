---
title: メッセージ ボックス データベースが移動されていない場合は、追跡データベースを移動する場合の考慮事項 |Microsoft Docs
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
ms.openlocfilehash: e7ff06df85f70168f3811910c0fab94c8bd772c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401285"
---
# <a name="considerations-when-moving-the-tracking-database-if-the-messagebox-database-is-not-being-moved"></a><span data-ttu-id="dd29e-102">メッセージ ボックス データベースが移動されていない場合は、追跡データベースを移動する場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="dd29e-102">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>
<span data-ttu-id="dd29e-103">追跡データベース、メッセージ ボックス データベースではなく、SampleUpdateInfo.xml ファイルを編集するときに、以下のことを確認を移動する場合、メッセージ ボックス データベースが移動されていない場合でも、同様に、メッセージ ボックス データベースのエントリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd29e-103">If you are moving the Tracking database but not the MessageBox database, when you edit the SampleUpdateInfo.xml file, make sure that you include an entry for the MessageBox database as well, even though the MessageBox database is not being moved.</span></span> <span data-ttu-id="dd29e-104">これが行うことを確認する必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェントのジョブ TrackedMessages_Copy_BizTalkMsgBoxDb は新しい追跡データベースの場所で更新されます。</span><span class="sxs-lookup"><span data-stu-id="dd29e-104">This must be done to ensure that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job TrackedMessages_Copy_BizTalkMsgBoxDb is updated with the location of the new Tracking database.</span></span>  
  
 <span data-ttu-id="dd29e-105">たとえば、SampleUpdateInfo.xml ファイル追跡データベースのみが中 OldServer からに移動 NewServer。</span><span class="sxs-lookup"><span data-stu-id="dd29e-105">For example, in the following SampleUpdateInfo.xml file, only the Tracking database is being moved from OldServer to NewServer.</span></span> <span data-ttu-id="dd29e-106">メッセージ ボックス データベースは、OldServer を使い続けます。</span><span class="sxs-lookup"><span data-stu-id="dd29e-106">The MessageBox database is staying on OldServer:</span></span>  
  
```  
<UpdateConfiguration>  
     <MessageBoxDB oldDBName="BizTalkMgmtDb" oldDBServer="OldServer" newDBName="BizTalkMgmtDb" newDBServer="OldServer" IsMaster="1"/>  
     <TrackingDB oldDBName="BizTalkDTADB" oldDBServer="OldServer" newDBName="BizTalkDTADB" newDBServer="NewServer"/>  
     <OtherDatabases>  
     </OtherDatabases>  
</UpdateConfiguration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd29e-107">参照</span><span class="sxs-lookup"><span data-stu-id="dd29e-107">See Also</span></span>  
 [<span data-ttu-id="dd29e-108">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="dd29e-108">Moving Databases</span></span>](../technical-guides/moving-databases.md)