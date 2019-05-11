---
title: X12 の処理でエラーが発生しました。 送信ポートでメッセージ。アグリーメント受信者および送信者 id 修飾子の組み合わせが存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72ae7926-f5c1-42f4-8c29-11f34c138dd4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9989a9d5e3c7568e8c02dbc52cfbec23aa0272c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347254"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a>X12 の処理でエラーが発生しました。 送信ポートでメッセージ。アグリーメント受信者および送信者 id 修飾子の組み合わせが存在しません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                       |
| 製品バージョン |                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                   |
|    イベント ID     |                                                                               -                                                                               |
|  イベント ソース   |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                     |
|    コンポーネント    |                                                                          EDI エンジン                                                                           |
|  シンボル名  |                                                                               -                                                                               |
|  メッセージ テキスト   | X12 の処理でエラーが発生しました。 送信ポートでメッセージ{0}します。 受信者および送信者の識別子と修飾子の組み合わせのアグリーメントが存在しない{1}、 {2}、 {3}、{4}します。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server が EDIFACT インターチェンジに BizTalk Server が一致するようにできなかったためには、送信者の修飾子と識別子のプロパティを昇格のパーティを解決できなかったし、受信者の修飾子を昇格することを示します、。パーティの対応する値の識別子プロパティ。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、一致するよう送信者の修飾子と識別子 (ISA5 および ISA6) および受信者の修飾子と識別子 (ISA7 と ISA8) が、EDI のプロパティ ダイアログ ボックスのパーティの ISA セグメントの定義 ページで定義されている、対応する昇格インターチェンジのコンテキスト内のプロパティ。