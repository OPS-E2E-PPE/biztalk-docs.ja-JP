---
title: X12 の処理でエラーが発生しました。 送信ポートでメッセージ。名前のパーティは存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af059a04-3b7c-48e2-a3bf-48ad62deb139
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efebb75a8d7b4989382f7c4855aab9b981c38c2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362436"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-party-with-name"></a>X12 の処理でエラーが発生しました。 送信ポートでメッセージ。名前のパーティは存在しません
## <a name="details"></a>詳細  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  製品名   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| 製品バージョン |                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                   |
|    イベント ID     |                                               -                                               |
|  イベント ソース   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI     |
|    コンポーネント    |                                          EDI エンジン                                           |
|  シンボル名  |                                               -                                               |
|  メッセージ テキスト   | X12 の処理でエラーが発生しました。 送信ポートでメッセージ{0}します。 名前のパーティが存在しない{1}します。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server で x12 の場合、パーティを解決できなかったことを示しますインターチェンジの BizTalk Server がパーティに関連付けられている送信ポートと、インターチェンジをサブスクライブした送信ポートを一致するようにできなかったためです。 これは、DestinationPartyName プロパティも、送信者の修飾子、送信者の識別子、受信者の修飾子、および受信者の識別子のプロパティが昇格される、そのため、送信側パーティの解決に使用できるもないかどうかに発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、インターチェンジをサブスクライブした送信ポートがパーティに関連付けられている送信ポートと一致することを確認します。