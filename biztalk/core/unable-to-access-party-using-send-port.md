---
title: "パーティにアクセスできませんを使用して送信ポート |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffacba77-76e8-4f03-be26-134a9999d6c1
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aa582319226b114720ef234b8e3f65e416a94d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-access-party-using-send-port"></a>送信ポートを使用してパーティにアクセスできません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|UnableToLocateAS2PartyBySendPortNameError|  
|メッセージ テキスト|パーティにアクセスできませんを使用して送信ポート: {0}。|  
  
## <a name="explanation"></a>説明  
 このエラーは、送信パイプラインが、送信 AS2 メッセージに対して指定された送信ポートに関連付けられたパーティを見つけられなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、指定された送信ポートにパーティを関連付けます。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで [ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、] をクリック**パーティ**です。  
  
3.  適切なパーティを右クリックします。  
  
4.  **[プロパティ]**をクリックします。  
  
5.  [*パーティ名*]**パーティ プロパティ**ダイアログ ボックスで、左側のウィンドウでをクリックして**送信ポート**です。  
  
6.  [送信ポートの名前を入力、**送信ポート**] ボックスの一覧です。  
  
7.  **[OK]**をクリックします。