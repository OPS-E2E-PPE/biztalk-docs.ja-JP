---
title: "送信ポートで Edifact メッセージの処理中にエラーが発生しました: 名前のないパーティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 678baacb-1f21-4081-b788-ef346c3598ca
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8acf93c1d1ec23e0c695bf2bfcf1ad105f9e10d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a>送信ポートで Edifact メッセージの処理中にエラーが発生しました: 名前のないパーティ
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|送信ポート {0} で Edifact メッセージの処理中にエラーが発生しました。 名前 {1} のパーティが存在しません。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティに関連付けられている送信ポートと、インターチェンジをサブスクライブした送信ポートが一致しなかったため、BizTalk Server が EDIFACT インターチェンジのパーティを解決できなかったことを示します。 このイベントが発生するのは、DestinationPartyName プロパティと、送信者の修飾子と識別子のプロパティおよび受信者の修飾子と識別子のプロパティのどちらも昇格されないため、送信側パーティの解決にそれらのプロパティを利用できない場合です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、インターチェンジをサブスクライブした送信ポートがパーティに関連付けられている送信ポートと一致していることを確認します。