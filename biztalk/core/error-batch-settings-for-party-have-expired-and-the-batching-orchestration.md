---
title: パーティのバッチ設定の期限が切れているし、バッチ処理オーケストレーションが終了しています |Microsoft Docs
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
ms.openlocfilehash: 896eb6325aa2bac076908643e582d286f2b5febe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389403"
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a>パーティのバッチ設定の期限が切れているし、バッチ処理オーケストレーションが終了しています
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| 製品バージョン |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    イベント ID     |                                                                                           -                                                                                           |
|  イベント ソース   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                 |
|    コンポーネント    |                                                                                    バッチ処理エンジン                                                                                    |
|  シンボル名  |                                                                                 BatchSettingsExpired                                                                                  |
|  メッセージ テキスト   | パーティのバッチ設定{0}期限が切れていると、バッチ処理オーケストレーションが終了しています。 このパーティのバッチ処理がアクティブ化されるまで、これ以上バッチは生成されません。 |
  
## <a name="explanation"></a>説明  
 この警告は、アクティベーションの範囲の末尾に達しているため、バッチ処理オーケストレーション インスタンスはアクティブすることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の手順に従ってバッチ処理のプロセスを再起動します。  
  
1.  BizTalk Server 管理コンソールを開き、インターチェンジのバッチ作成の設定 ページの EDI のプロパティ ダイアログ ボックスに移動します。  
  
2.  最後の条件をリセットしをクリックして、オーケストレーションを再起動**開始**します。  
  
3.  クリックした日時より前の開始 日時が場合**開始**、 をクリックして**はい**開始日時を現在の日時に更新します。