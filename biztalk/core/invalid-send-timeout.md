---
title: 無効な送信タイムアウト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01c63cd8-e978-4dd6-ba12-d0c0ad07b8c7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efffea81d4216b942a9e08600065152c25140e72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381206"
---
# <a name="invalid-send-timeout"></a>送信タイムアウトが無効です
## <a name="details"></a>詳細  

|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| 製品バージョン |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                |
|    イベント ID     |                                            0                                            |
|  イベント ソース   |                                            0                                            |
|    コンポーネント    |                                            0                                            |
|  シンボル名  |                                            0                                            |
|  メッセージ テキスト   | タイムアウトの送信が無効です。 有効範囲:0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒。 |

## <a name="explanation"></a>説明  

## <a name="user-action"></a>ユーザーの操作  
 タイムアウト範囲を構成するのにには、次の手順を使用します。  

#### <a name="to-configure-the-timeout-range"></a>タイムアウト範囲を構成するには  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを見つけて、トランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、適切なポートを選択します。  

7. をクリックして**構成**です。  

8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  

9. タイムアウト範囲が有効なことを確認します。 指定できる値は、0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒です。
