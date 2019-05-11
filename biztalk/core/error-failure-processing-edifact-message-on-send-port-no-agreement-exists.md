---
title: 送信ポートで Edifact メッセージの処理中にエラーが発生しました。契約受信者および送信者 id 修飾子のペアと名前のパーティは存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11880c7c-6032-449b-b251-27fc2b2f0d72
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd3df9a2635864f0dcc884426816f1674c9284c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389302"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a>送信ポートで Edifact メッセージの処理中にエラーが発生しました。契約受信者および送信者 id 修飾子のペアと名前のパーティは存在しません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| 製品バージョン |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    イベント ID     |                                                                                                -                                                                                                 |
|  イベント ソース   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                      |
|    コンポーネント    |                                                                                            EDI エンジン                                                                                            |
|  シンボル名  |                                                                                                -                                                                                                 |
|  メッセージ テキスト   | 送信ポートで Edifact メッセージの処理中にエラーが発生しました{0}します。 受信者および送信者の識別子と修飾子の組み合わせのアグリーメントが存在しない{1}、 {2}、 {3}、{4}します。 名前のパーティが存在しない{5}します。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server が EDIFACT インターチェンジのパーティを照合できなかったため、昇格の送信者の修飾子と識別子のプロパティを解決することができませんでしたと受信者の修飾子と識別子を昇格することを示します。プロパティでは、パーティの対応する値。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、一致するよう送信者の修飾子と識別子 (UNB2.1 と UNB2.2) および受信者の修飾子と識別子 (UNB3.1 と UNB3.2) が、EDI のプロパティ ダイアログ ボックスのパーティの UNB セグメントの定義 ページで定義されている、対応します。インターチェンジのコンテキストで昇格させたプロパティです。