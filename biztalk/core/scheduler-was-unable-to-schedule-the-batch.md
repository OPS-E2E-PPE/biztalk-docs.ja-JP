---
title: スケジューラはバッチをスケジュールできませんでした。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ac6d79c-c995-4c95-a4da-ee2f50b9a13a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91a10ff141205e534f43bb437343408aed5fa386
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308022"
---
# <a name="scheduler-was-unable-to-schedule-the-batch"></a>スケジューラはバッチをスケジュールできませんでした。
## <a name="details"></a>詳細  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                    バッチ処理エンジン                                     |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |                       スケジューラはバッチをスケジュールできませんでした。                       |

## <a name="explanation"></a>説明  
 このエラーは、スケジューラはバッチのリリースの次の出現箇所を特定できませんでしたを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、バッチ リリース スケジュールが有効になっていることを確認します。  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、 をクリック**パーティ**します。  

3. 正しいパーティを右クリックします。  

4. **[プロパティ]** をクリックします。  

5. [*パーティ名*]**パーティ プロパティ** ダイアログ ボックスで、左側のウィンドウでクリックして**送信ポート**します。  

6. 送信ポート名を入力、**送信ポート**一覧。  

7. **[OK]** をクリックします。
