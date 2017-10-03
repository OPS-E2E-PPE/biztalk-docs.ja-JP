---
title: "X12 の処理中にエラーが発生した送信ポートでメッセージ: 受信者および送信者 id 修飾子の組み合わせのアグリーメントがありません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72ae7926-f5c1-42f4-8c29-11f34c138dd4
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 637cd174b2c9723f4391417392700e3a4f079b79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a>X12 の処理中にエラーが発生した送信ポートでメッセージ: 受信者および送信者 id 修飾子の組み合わせのアグリーメントがありません。
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|送信ポート {0} で X12 メッセージの処理中にエラーが発生しました。 {1}、{2}、{3}、{4} 受信者および送信者の id と修飾子の組み合わせのアグリーメントが存在しません。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server で、昇格した送信者の修飾子と識別子のプロパティ、および昇格した受信者の修飾子と識別子のプロパティが、パーティの対応する値と一致しなかったために、BizTalk Server で EDIFACT インターチェンジのパーティを解決できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスのパーティの [ISA セグメントの定義] ページで定義されている、送信者の修飾子と識別子 (ISA5 と ISA6) および受信者の修飾子と識別子 (ISA7 と ISA8) が、インターチェンジのコンテキストで昇格させた対応するプロパティに一致することを確認します。