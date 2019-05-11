---
title: オープン タイムアウトが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0047cf43-fcc3-40b4-abeb-bf1b6e7a422b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9522e7bf4f5624494504a9ab9f4d25d48ecb7530
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381307"
---
# <a name="invalid-open-timeout"></a>オープン タイムアウトが無効です
## <a name="details"></a>詳細  

|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| 製品バージョン |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                |
|    イベント ID     |                                            0                                            |
|  イベント ソース   |                                            0                                            |
|    コンポーネント    |                                            0                                            |
|  シンボル名  |                                            0                                            |
|  メッセージ テキスト   | オープン タイムアウトが無効です。 有効範囲:0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒。 |

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
