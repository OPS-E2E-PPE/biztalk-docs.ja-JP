---
title: 失敗したメッセージのルーティングを有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d33beed4-1ae2-4282-95ac-5d68aab7fb5d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e524f96114e887569c10294be0e665f1aa711a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337940"
---
# <a name="how-to-enable-routing-for-failed-messages"></a>失敗したメッセージのルーティングを有効にする方法
失敗したメッセージのルーティング送信のプロパティであると受信ポート、および「有効化が失敗したメッセージをルーティングする」を示すポートのプロパティ ページで有効です。  
  
> [!NOTE]
>  受信ポートの構成は、その受信ポートに関連付けられているすべての受信場所に適用されます。  
  
> [!NOTE]
>  送信ポートの構成は、プライマリおよびバックアップ トランスポートの両方に適用されます。  
  
### <a name="to-configure-failed-message-routing-for-a-receive-port-this-applies-to-both-one-way-and-request-response-receive-ports"></a>失敗したメッセージのルーティングを受信ポートを構成する (一方向の両方に適用し、要求-応答受信ポート)  
  
1. BizTalk Server 管理コンソールを開きます。  
  
2. 展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、送信ポートが所属するアプリケーションを展開します。  
  
3. をクリックして、**受信ポート**フォルダー。  
  
4. 右側のウィンドウで、構成する受信ポートの名前をダブルクリックします。  
  
5. 左側のウィンドウで、受信ポートのプロパティ ページで選択、**全般**カテゴリ。  
  
6. 右側のウィンドウで、選択、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンにして**適用**します。  
  
### <a name="to-configure-failed-message-routing-for-a-send-port-this-applies-only-to-static-one-way-and-static-solicit-response-send-ports"></a>失敗した (これは静的な一方向と静的な送信請求-応答送信ポートにのみ適用されます)、送信ポートのメッセージのルーティングを構成するには  
  
1. BizTalk Server 管理コンソールを開きます。  
  
2. 展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、送信ポートが所属するアプリケーションを展開します。  
  
3. をクリックして、**送信ポート**フォルダー。  
  
4. 右側のウィンドウで、構成する送信ポートの名前をダブルクリックします。  
  
5. 送信ポートのプロパティ ページで、左側のウィンドウで選択、**トランスポートの詳細オプション**カテゴリ。  
  
6. 右側のウィンドウでの**トランスポート オプション**グループ ボックスで、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンにして**適用**。  
  
## <a name="see-also"></a>参照  
 [エラー処理](../core/error-handling.md)