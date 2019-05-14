---
title: インターチェンジ XML メッセージのシリアル化中に発生した構造のエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97939bfd-d1ee-455a-9952-4f25db020e7c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d2b57fb3c520b283fa8d0fbb160efb87d3378e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244150"
---
# <a name="structural-error-encountered-during-serialization-of-an-interchange-xml-message"></a>インターチェンジ XML メッセージのシリアル化中に発生した構造のエラー
## <a name="details"></a>詳細  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                  InvalidXmlNodeFound                                   |
|  メッセージ テキスト   |    インターチェンジ Xml メッセージのシリアル化中に発生した構造のエラー     |

## <a name="explanation"></a>説明  
 このエラーは、インターチェンジ XML メッセージのシリアル化中に構造エラーが発生したことを示します。 BTS は XML StartElement または EndElement が検索しますが、代わりにさまざまな XML ノード型が発生しました。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、メッセージの構造が正しいこと、もう一度やり直してを確認します。  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、 をクリック**BizTalk グループ**します。  

3. 右側のウィンドウでをクリックして、**グループ ハブ**タブ。  

4. クリックして**中断されたサービス インスタンス**します。  

5. メッセージをダブルクリックします。  

6. **サービスの詳細**ウィンドウで、をクリックして、**メッセージ**タブ。  

7. メッセージをもう一度ダブルクリックします。  

8. 左側のウィンドウで次のようにクリックします。**メッセージ部分/Body**します。  

9. メッセージの構造が正しいかどうかを決定します。
