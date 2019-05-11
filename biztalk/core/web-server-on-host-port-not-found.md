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
ms.openlocfilehash: adad9ab9e2e5bbe3a23401a4c893a8d581b6c742
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250147"
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
 World Wide Web サービスを開始するのにには、次の手順を使用します。  
  
#### <a name="to-start-the-world-wide-web-service"></a>World Wide Web サービスを開始するには  
  
1.  クリックして**開始**、 をクリックして**コントロール パネルの **、 をダブルクリックします**管理ツール**、 をダブルクリックします**サービス。**  
  
2.  [名前] 列で検索**World Wide Web 発行**します。 状態があることを確認**開始**します。  
  
3.  戻り、**管理ツール**ウィンドウ。 ダブルクリック**インターネット インフォメーション サービス**します。  
  
4.  フォルダーの領域を展開し、web サイトを探します。  
  
5.  状態があることを確認**開始**します。