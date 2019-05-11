---
title: BizTalk メッセージ本文要素のエンコードが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b407e5c3-4655-4b2f-8ecc-30eb080ec47c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c468679853f450695f6fa2194c303be5438a4e90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357985"
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a>BizTalk メッセージ本文要素のエンコードは無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  製品名   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| 製品バージョン |                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                           |
|    イベント ID     |                                                       0                                                        |
|  イベント ソース   |                                                       0                                                        |
|    コンポーネント    |                                                       0                                                        |
|  シンボル名  |                                                       0                                                        |
|  メッセージ テキスト   | BizTalk メッセージ本文要素のエンコード"{0}"が無効です。 エンコードが必要です"xml"、"base64"、"hex"、または"string"。 |
  
## <a name="explanation"></a>説明  
 このエラーは、送信メッセージは BizTalk 本文テンプレート オプションの使用を示します。ただし、BizTalk 本文に指定したエンコードの種類が無効です。  
  
## <a name="user-action"></a>ユーザーの操作  
 エンコードの種類を構成するのにには、次の手順を使用します。  
  
#### <a name="to-configure-the-encoding-type"></a>エンコードの種類を構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブ。  
  
9. **送信 WCF メッセージ本文**セクションで、、**テンプレート--テンプレートで指定されたコンテンツ**ラジオ ボタンをクリックします。 **XML**テキスト ボックスに、BizTalk 本文の形式である必要があります   
    \<**bts-msg-body xmlns="<http://www.microsoft.com/schemas/bts2007>" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>  (valid values, which are case-sensitive, for encoding are xml&#124;base64&#124;hex&#124;string)