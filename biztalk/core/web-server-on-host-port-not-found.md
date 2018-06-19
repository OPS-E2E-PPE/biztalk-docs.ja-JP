---
title: Web ポートでサーバーにホストが見つかりません |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c253fd5e-b815-4697-a06d-67af65a35589
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dce09ce00a169ad14bbc8ae2ab28fe70c039c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288562"
---
# <a name="web-server-on-host-port-not-found"></a>ホスト ポートの Web サーバーが見つかりません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|見つかりません。"{0}"ホスト ポート {1} 上の web サーバー|  
  
## <a name="explanation"></a>説明  
 このエラーは、World Wide Web (WWW) サービスが実行されていないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 World Wide Web サービスを開始するには、次の手順に従います。  
  
#### <a name="to-start-the-world-wide-web-service"></a>World Wide Web サービスを開始するには  
  
1.  をクリックして**開始**、 をクリックして**コントロール パネル**をダブルクリックして**管理ツール**、 をダブルクリック**サービス。**  
  
2.  [名前] 列で探します**World Wide Web Publishing**です。 状態があることを確認してください。 **Started**です。  
  
3.  戻り、**管理ツール**ウィンドウです。 ダブルクリックして**インターネット インフォメーション サービス**です。  
  
4.  フォルダー領域を展開し、Web サイトを探します。  
  
5.  状態があることを確認してください。 **Started**です。