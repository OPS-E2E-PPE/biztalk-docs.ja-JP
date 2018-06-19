---
title: インターチェンジ XML メッセージのシリアル化中に発生した構造のエラー |Microsoft ドキュメント
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
ms.openlocfilehash: 44b56cce9fdd3704f7e6ddc2ba5b5bebb62d36e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278594"
---
# <a name="structural-error-encountered-during-serialization-of-an-interchange-xml-message"></a>インターチェンジ XML メッセージのシリアル化中に発生した構造のエラー
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|InvalidXmlNodeFound|  
|メッセージ テキスト|インターチェンジ XML メッセージのシリアル化中に構造エラーが発生しました|  
  
## <a name="explanation"></a>説明  
 このエラーは、インターチェンジ XML メッセージのシリアル化中に構造エラーが発生したことを示します。 BTS は XML StartElement または EndElement を探していましたが、異なる XML ノードの種類が見つかりました。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、メッセージ構造が正しいことを確認して、やり直します。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで [ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、] をクリック**BizTalk グループ**です。  
  
3.  右側のウィンドウでをクリックして、**グループ ハブ**タブです。  
  
4.  をクリックして**中断されたサービス インスタンス**です。  
  
5.  メッセージをダブルクリックします。  
  
6.  **サービスの詳細**ウィンドウで、をクリックして、**メッセージ**タブです。  
  
7.  メッセージを再びダブルクリックします。  
  
8.  左側のウィンドウでをクリックして**メッセージ部分/Body**です。  
  
9. メッセージ構造が正しいかどうか確認します。