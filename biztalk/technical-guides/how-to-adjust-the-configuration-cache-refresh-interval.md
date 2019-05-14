---
title: 構成キャッシュ更新間隔を調整する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63c6c998-e9c0-48f1-a36a-f1fcb916321b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99cffcba5181f62267ca9eeed9c9c3610ea7ee1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277168"
---
# <a name="how-to-adjust-the-configuration-cache-refresh-interval"></a>構成キャッシュ更新間隔を調整する方法
構成のキャッシュ更新間隔は、BizTalk Server が、エンドポイントの構成を更新する期間を定義します。 BizTalk Server を起動すると、メッセージ ボックス データベース、サーバーのプロパティ、アダプター、および追跡データベースへの接続などの BizTalk Server 管理のすべての項目が構成キャッシュに格納されます。 キャッシュ内のすべての項目は、構成の更新間隔で更新されます。 既定では、サーバー データベースの接続とサーバーのプロパティを除く、60 秒ごとです。 これは、こと、SMTP ホストなどの BizTalk グループの [全般] プロパティを変更する場合、変更は選択 60 秒以内ことを意味します。 更新するまで、BizTalk Server 管理コンソールの現在開いているインスタンスの外部システムの変更は反映されません。  
  
 構成のキャッシュ更新間隔は、BizTalk グループのプロパティの一部です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-adjust-the-cache-refresh-interval"></a>キャッシュ更新間隔を調整するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。  
  
3. **BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、**全般**タブ。**構成の更新間隔**プロパティでは、入力または選択時間 (秒) 内の項目をすべて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理キャッシュの構成キャッシュの更新の間の待機をクリックする必要があります **[ok]**.  
  
   > [!NOTE]  
   >  更新に関連する項目には、メッセージ ボックス データベース、サーバーのプロパティ、アダプター、および追跡データベースへの接続が含まれます。  
  
   > [!NOTE]  
   >  既定では、構成キャッシュ内のすべてのオブジェクトは、サーバー データベースの接続とサーバーのプロパティを除く、60 秒ごとに更新されます。