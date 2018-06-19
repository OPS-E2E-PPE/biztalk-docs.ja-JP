---
title: '送信ポートで Edifact メッセージの処理中にエラーが発生しました: 受信者および送信者 id 修飾子の組み合わせと名前のないパーティのアグリーメントがありません |。Microsoft ドキュメント'
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
ms.openlocfilehash: 7df88a39d9ccbbcd94fd4498c5847c5104bb40cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240098"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a>送信ポートで Edifact メッセージの処理中にエラーが発生しました: 受信者および送信者 id 修飾子の組み合わせと名前のないパーティのアグリーメントがありません。
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|送信ポート {0} で Edifact メッセージの処理中にエラーが発生しました。 {1}、{2}、{3}、{4} 受信者および送信者の id と修飾子の組み合わせのアグリーメントが存在しません。 名 \\ 5 \\ のパーティが存在しません。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server が、送信者の修飾子と識別子の昇格させたプロパティおよび受信者の修飾子と識別子の昇格させたプロパティを、パーティの対応する値に照合できなかったため、BizTalk Server が EDIFACT インターチェンジのパーティを解決できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスのパーティの [UNB セグメントの定義] ページで定義されている、送信者の修飾子と識別子 (UNB2.1 と UNB2.2) および受信者の修飾子と識別子 (UNB3.1 と UNB3.2) が、インターチェンジのコンテキストで昇格させた対応するプロパティに一致することを確認します。