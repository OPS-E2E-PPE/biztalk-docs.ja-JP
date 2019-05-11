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
# <a name="considerations-when-moving-the-tracking-database-if-the-messagebox-database-is-not-being-moved"></a>メッセージ ボックス データベースが移動されていない場合は、追跡データベースを移動する場合の考慮事項
追跡データベース、メッセージ ボックス データベースではなく、SampleUpdateInfo.xml ファイルを編集するときに、以下のことを確認を移動する場合、メッセージ ボックス データベースが移動されていない場合でも、同様に、メッセージ ボックス データベースのエントリが含まれます。 これが行うことを確認する必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェントのジョブ TrackedMessages_Copy_BizTalkMsgBoxDb は新しい追跡データベースの場所で更新されます。  
  
 たとえば、SampleUpdateInfo.xml ファイル追跡データベースのみが中 OldServer からに移動 NewServer。 メッセージ ボックス データベースは、OldServer を使い続けます。  
  
```  
<UpdateConfiguration>  
     <MessageBoxDB oldDBName="BizTalkMgmtDb" oldDBServer="OldServer" newDBName="BizTalkMgmtDb" newDBServer="OldServer" IsMaster="1"/>  
     <TrackingDB oldDBName="BizTalkDTADB" oldDBServer="OldServer" newDBName="BizTalkDTADB" newDBServer="NewServer"/>  
     <OtherDatabases>  
     </OtherDatabases>  
</UpdateConfiguration>  
```  
  
## <a name="see-also"></a>参照  
 [データベースの移動](../technical-guides/moving-databases.md)