---
title: Web サーバーが見つかりませんホスト ポート |。Microsoft Docs
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
ms.openlocfilehash: 62f9260f477669debf709ba592568a15fbaf7194
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987147"
---
# <a name="web-server-on-host-port-not-found"></a>ホスト ポートの Web サーバーが見つかりません
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                    ホスト上の web サーバー"{0}"ポート{1}が見つかりません。                     |
  
## <a name="explanation"></a>説明  
 このエラーは、World Wide Web (WWW) サービスが実行されていないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 World Wide Web サービスを開始するには、次の手順に従います。  
  
#### <a name="to-start-the-world-wide-web-service"></a>World Wide Web サービスを開始するには  
  
1.  クリックして**開始**、 をクリックして**コントロール パネルの **、 をダブルクリックします**管理ツール**、 をダブルクリックします**サービス。**  
  
2.  [名前] 列で検索**World Wide Web 発行**します。 状態があることを確認**開始**します。  
  
3.  戻り、**管理ツール**ウィンドウ。 ダブルクリック**インターネット インフォメーション サービス**します。  
  
4.  フォルダー領域を展開し、Web サイトを探します。  
  
5.  状態があることを確認**開始**します。