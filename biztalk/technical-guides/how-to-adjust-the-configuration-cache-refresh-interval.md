---
title: 構成キャッシュの更新間隔を調整する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: ad9459fadd65af220982ab31ae0e464cb7f1986e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297882"
---
# <a name="how-to-adjust-the-configuration-cache-refresh-interval"></a>構成キャッシュの更新間隔を調整する方法
構成キャッシュの更新間隔は、BizTalk Server が、エンドポイントの構成を更新するまでの時間を定義します。 BizTalk Server を起動すると、メッセージ ボックス データベース、サーバーのプロパティ、アダプター、および追跡データベースへの接続などの BizTalk Server 管理のすべての項目が構成キャッシュに格納されます。 キャッシュ内のすべてのアイテムは、構成の更新間隔で更新されます。 既定では、サーバー データベース接続とサーバーのプロパティを除く、60 秒ごとです。 これは、SMTP ホストなどの BizTalk グループの [全般] プロパティを変更する場合、変更が選択される 60 秒以内ことを意味します。 更新するまで、現在開いているインスタンス、BizTalk Server 管理コンソールの外部システムの変更は反映されません。  
  
 構成キャッシュの更新間隔は、BizTalk グループのプロパティの一部です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-adjust-the-cache-refresh-interval"></a>キャッシュ更新間隔を調整するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**を右クリックして**BizTalk グループ**、順にクリック**設定**です。  
  
3.  **BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、**全般**タブです。**構成の更新間隔**プロパティ、入力または時間 (秒単位) を選択するすべての項目、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理キャッシュが構成キャッシュの更新の間の待機する必要があります、クリックして**OK**.  
  
    > [!NOTE]  
    >  更新される項目には、メッセージ ボックス データベース、サーバーのプロパティ、アダプター、追跡データベースへの接続などがあります。  
  
    > [!NOTE]  
    >  既定では、構成キャッシュ内のすべてのオブジェクトは、サーバー データベース接続とサーバーのプロパティを除く、60 秒ごとに更新します。