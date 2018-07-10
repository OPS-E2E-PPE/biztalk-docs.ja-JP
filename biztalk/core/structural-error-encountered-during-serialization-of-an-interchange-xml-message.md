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
ms.openlocfilehash: 7e5ce0694b60afcb743c138d3059a78f63f6fcb5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994299"
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
|  メッセージ テキスト   |    インターチェンジ XML メッセージのシリアル化中に構造エラーが発生しました     |

## <a name="explanation"></a>説明  
 このエラーは、インターチェンジ XML メッセージのシリアル化中に構造エラーが発生したことを示します。 BTS は XML StartElement または EndElement を探していましたが、異なる XML ノードの種類が見つかりました。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、メッセージ構造が正しいことを確認して、やり直します。  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、] をクリック**BizTalk グループ**します。  

3. 右側のウィンドウでをクリックして、**グループ ハブ**タブ。  

4. クリックして**中断されたサービス インスタンス**します。  

5. メッセージをダブルクリックします。  

6. **サービスの詳細**ウィンドウで、をクリックして、**メッセージ**タブ。  

7. メッセージを再びダブルクリックします。  

8. 左側のウィンドウで次のようにクリックします。**メッセージ部分/Body**します。  

9. メッセージ構造が正しいかどうか確認します。
