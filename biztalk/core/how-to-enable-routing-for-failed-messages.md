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
ms.openlocfilehash: c00e49afa528bc0008d73272dca561d461660367
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008491"
---
# <a name="how-to-enable-routing-for-failed-messages"></a>失敗したメッセージのルーティングを有効にする方法
失敗したメッセージのルーティングは送受信ポートのプロパティの一種であり、ポートのプロパティ ページで [失敗したメッセージをルーティングする] を指定すると有効になります。  
  
> [!NOTE]
>  受信ポートの構成は、その受信ポートに関連付けられているすべての受信場所に適用されます。  
  
> [!NOTE]
>  送信ポートの構成は、プライマリ トランスポートとバックアップ トランスポートの両方に適用されます。  
  
### <a name="to-configure-failed-message-routing-for-a-receive-port-this-applies-to-both-one-way-and-request-response-receive-ports"></a>失敗したメッセージのルーティングを受信ポートに対して構成するには (一方向の受信ポートと要求 - 応答の受信ポートの両方に適用)  
  
1. BizTalk Server 管理コンソールを開きます。  
  
2. 展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、送信ポートが所属するアプリケーションを展開します。  
  
3. をクリックして、**受信ポート**フォルダー。  
  
4. 右ペインで、構成する受信ポートの名前をダブルクリックします。  
  
5. 左側のウィンドウで、受信ポートのプロパティ ページで選択、**全般**カテゴリ。  
  
6. 右側のウィンドウで、選択、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンにして**適用**します。  
  
### <a name="to-configure-failed-message-routing-for-a-send-port-this-applies-only-to-static-one-way-and-static-solicit-response-send-ports"></a>失敗したメッセージのルーティングを送信ポートに対して構成するには (静的な一方向の送信ポートと静的な送信請求 - 応答の送信ポートにのみ適用)  
  
1. BizTalk Server 管理コンソールを開きます。  
  
2. 展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、送信ポートが所属するアプリケーションを展開します。  
  
3. をクリックして、**送信ポート**フォルダー。  
  
4. 右ペインで、構成する送信ポートの名前をダブルクリックします。  
  
5. 送信ポートのプロパティ ページで、左側のウィンドウで選択、**トランスポートの詳細オプション**カテゴリ。  
  
6. 右側のウィンドウでの**トランスポート オプション**グループ ボックスで、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンにして**適用**。  
  
## <a name="see-also"></a>参照  
 [エラー処理](../core/error-handling.md)