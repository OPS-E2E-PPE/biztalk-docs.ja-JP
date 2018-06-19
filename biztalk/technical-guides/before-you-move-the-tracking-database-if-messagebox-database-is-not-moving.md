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
# <a name="considerations-when-moving-the-tracking-database-if-the-messagebox-database-is-not-being-moved"></a>メッセージ ボックス データベースが移動されていない場合に、追跡データベースを移動する際の考慮事項
追跡データベース、メッセージ ボックス データベースではなく、SampleUpdateInfo.xml ファイルを編集するときに、以下のことを確認を移動する場合は、メッセージ ボックス データベースが移動されていない場合でも同様に、メッセージ ボックス データベースのエントリがあります。 これが行うことを確認する必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ TrackedMessages_Copy_BizTalkMsgBoxDb は新しい追跡データベースの場所で更新します。  
  
 たとえば、SampleUpdateInfo.xml ファイルを追跡データベースのみがから移動中 OldServer NewServer にします。 メッセージ ボックス データベースは OldServer 上に保持しました。  
  
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