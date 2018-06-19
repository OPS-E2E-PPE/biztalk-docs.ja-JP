---
title: パーティのバッチ設定が有効期限が切れて、バッチ処理オーケストレーションが終了しています |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f272b6-4da2-4736-8d61-ce48359f36dd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d56e06766a980c1ce293b211d2956a86c093726
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241306"
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a>パーティのバッチの設定が期限切れになったため、バッチ処理オーケストレーションが終了しています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|バッチ処理エンジン|  
|シンボル名|BatchSettingsExpired|  
|メッセージ テキスト|パーティ {0} のバッチの設定が期限切れになったため、バッチ処理オーケストレーションが終了しています。 このパーティのバッチ処理がアクティブになるまで、これ以上バッチは生成されません。|  
  
## <a name="explanation"></a>説明  
 この警告は、アクティベーションの範囲の終点に達したため、バッチ処理オーケストレーション インスタンスが非アクティブになったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行ってバッチ処理プロセスを再開します。  
  
1.  BizTalk Server 管理コンソールを開き、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジのバッチ作成用の設定] ページに移動します。  
  
2.  終了条件をリセットしをクリックして、オーケストレーションを再起動**開始**です。  
  
3.  クリックした日時より前の開始 日時が場合**開始**、 をクリックして**はい**開始日時を現在の日時に更新します。