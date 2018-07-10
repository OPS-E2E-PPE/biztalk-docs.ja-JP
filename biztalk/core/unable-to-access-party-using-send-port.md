---
title: パーティにアクセスできませんを使用してポートの送信 |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffacba77-76e8-4f03-be26-134a9999d6c1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdff3eed53ae042be064bd2e02ff5cecf68c6021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976417"
---
# <a name="unable-to-access-party-using-send-port"></a>送信ポートを使用してパーティにアクセスできません
## <a name="details"></a>詳細  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                       UnableToLocateAS2PartyBySendPortNameError                        |
|  メッセージ テキスト   |                      パーティにアクセスできません。 を使用してポートを送信します。 {0}                       |

## <a name="explanation"></a>説明  
 このエラーは、送信パイプラインが、送信 AS2 メッセージに対して指定された送信ポートに関連付けられたパーティを見つけられなかったことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、指定された送信ポートにパーティを関連付けます。  

1. クリックして**開始**、] をクリックして**すべてのプログラム**、] をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. [コンソール ルートで [ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、] をクリック**パーティ**します。  

3. 適切なパーティを右クリックします。  

4. **[プロパティ]** をクリックします。  

5. [*パーティ名*]**パーティ プロパティ**] ダイアログ ボックスで、左側のウィンドウでクリックして**送信ポート**します。  

6. 送信ポート名を入力、**送信ポート**一覧。  

7. [**OK**] をクリックします。
