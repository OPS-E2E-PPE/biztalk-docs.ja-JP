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
ms.openlocfilehash: 023cf9829d71155fec439f040bb526fd82572ac8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011611"
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
|  メッセージ テキスト   | 有効期限のタイムアウトが無効です。 有効な範囲: 0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒 |

## <a name="explanation"></a>説明  

## <a name="user-action"></a>ユーザーの操作  
 タイムアウト範囲を構成するには、次の手順に従います。  

#### <a name="to-configure-the-timeout-range"></a>タイムアウト範囲を構成するには  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを特定し、次にトランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、 **Wcf-netmsmq**します。  

7. クリックして**構成**します。  

8. **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  

9. **キューの設定**セクションを確認してください、**ライブ (dd:hh:mm:ss) までの時間をメッセージ**範囲が無効です。 使用可能な値は、0 ～ 23 時間、0 ～ 59 分、0 ～ 59 秒です。
