---
title: 送信ポートで Edifact メッセージの処理中にエラーが発生しました。アグリーメント受信者および送信者 id 修飾子の組み合わせが存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cffc4705-164f-4779-8f04-c6a2a7f1bbda
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2937dc29be315ef5298b43a50ab95f52c4573a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348298"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a>送信ポートで Edifact メッセージの処理中にエラーが発生しました。アグリーメント受信者および送信者 id 修飾子の組み合わせが存在しません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
| 製品バージョン |                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                     |
|    イベント ID     |                                                                                 -                                                                                 |
|  イベント ソース   |                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                       |
|    コンポーネント    |                                                                            EDI エンジン                                                                             |
|  シンボル名  |                                                                                 -                                                                                 |
|  メッセージ テキスト   | 送信ポートで Edifact メッセージの処理中にエラーが発生しました{0}します。 受信者および送信者の識別子と修飾子の組み合わせのアグリーメントが存在しない{1}、 {2}、 {3}、{4}します。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server が EDIFACT インターチェンジのパーティを照合できなかったため、昇格の送信者の修飾子と識別子のプロパティを解決することができませんでしたと受信者の修飾子と識別子を昇格することを示します。プロパティでは、パーティの対応する値。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、一致するよう送信者の修飾子と識別子 (UNB2.1 と UNB2.2) および受信者の修飾子と識別子 (UNB3.1 と UNB3.2) が、EDI のプロパティ ダイアログ ボックスのパーティの UNB セグメントの定義 ページで定義されている、対応します。インターチェンジのコンテキストで昇格させたプロパティです。