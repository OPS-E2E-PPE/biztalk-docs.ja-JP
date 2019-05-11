---
title: 送信ポートで Edifact メッセージの処理中にエラーが発生しました。名前のパーティは存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 678baacb-1f21-4081-b788-ef346c3598ca
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98884d7e3a2ab36faddb831ca2550120c345f1b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347186"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a>送信ポートで Edifact メッセージの処理中にエラーが発生しました。名前のパーティは存在しません
## <a name="details"></a>詳細  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  製品名   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| 製品バージョン |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    イベント ID     |                                                 -                                                 |
|  イベント ソース   |                                        BizTalk Server EDI                                         |
|    コンポーネント    |                                            EDI エンジン                                             |
|  シンボル名  |                                                 -                                                 |
|  メッセージ テキスト   | 送信ポートで Edifact メッセージの処理中にエラーが発生しました{0}します。 名前のパーティが存在しない{1}します。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server が BizTalk Server がパーティに関連付けられている送信ポートと、インターチェンジをサブスクライブした送信ポートを一致するようにできなかったため、EDIFACT インターチェンジのパーティを解決するのにはできなかったことを示します。 これは、DestinationPartyName プロパティも、送信者の修飾子および識別子と受信者の修飾子と識別子のプロパティが昇格される、そのため、送信側パーティの解決に使用できるもないかどうかに発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、インターチェンジをサブスクライブした送信ポートがパーティに関連付けられている送信ポートと一致することを確認します。