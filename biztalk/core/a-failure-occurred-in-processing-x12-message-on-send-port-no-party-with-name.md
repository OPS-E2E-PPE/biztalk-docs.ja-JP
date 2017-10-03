---
title: "X12 の処理中にエラーが発生した送信ポートでメッセージ: いいえパーティ名 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af059a04-3b7c-48e2-a3bf-48ad62deb139
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0e620797d45fb0b3d2ef929865a4b8bb98d2d90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-party-with-name"></a>X12 の処理中にエラーが発生した送信ポートでメッセージ: いいえパーティ名
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|送信ポート {0} で X12 メッセージの処理中にエラーが発生しました。 名前 {1} のパーティが存在しません。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティに関連付けられている送信ポートと、インターチェンジをサブスクライブした送信ポートが一致しなかったため、BizTalk Server が X12 インターチェンジのパーティを解決できなかったことを示します。 このイベントが発生するのは、DestinationPartyName プロパティと、送信者の修飾子、送信者の識別子、受信者の修飾子、および受信者の識別子の各プロパティが昇格されないため、送信側パーティの解決にそれらのプロパティを利用できない場合です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジをサブクライブした送信ポートが、パーティに関連付けられている送信ポートに一致することを確認します。