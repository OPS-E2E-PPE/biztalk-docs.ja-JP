---
title: 有効期限タイムアウトまでの時間が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2ddb6de-8c3b-4dee-a984-980e1caea95e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c984130ad3a85d6441a192506202489759b5bc9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330310"
---
# <a name="invalid-time-to-live-timeout"></a>有効期限タイムアウトが無効です
## <a name="details"></a>詳細  

|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  製品名   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| 製品バージョン |                   [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                   |
|    イベント ID     |                                               0                                                |
|  イベント ソース   |                                               0                                                |
|    コンポーネント    |                                               0                                                |
|  シンボル名  |                                               0                                                |
|  メッセージ テキスト   | 有効期限タイムアウト時間が無効です。 有効範囲:0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒 |

## <a name="explanation"></a>説明  

## <a name="user-action"></a>ユーザーの操作  
 タイムアウト範囲を構成するのにには、次の手順を使用します。  

#### <a name="to-configure-the-timeout-range"></a>タイムアウト範囲を構成するには  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを見つけて、トランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、 **Wcf-netmsmq**します。  

7. をクリックして**構成**です。  

8. **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  

9. **キューの設定**セクションを確認してください、**ライブ (dd:hh:mm:ss) までの時間をメッセージ**範囲が無効です。 指定できる値は、0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒です。
