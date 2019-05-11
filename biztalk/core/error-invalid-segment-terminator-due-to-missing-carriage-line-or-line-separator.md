---
title: インターチェンジで構造エラーが。 可能性の高い原因は復帰がないため、無効なセグメントの終端記号と、または改行区切り |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035e37d5-d4a8-49d0-8d75-3bcf2426cac7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49281421130fad2a28f829efda2b8be14adededc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388745"
---
# <a name="the-interchange-had-structural-error-a-likely-cause-is-invalid-segment-terminator-due-to-missing-carriage-line-and-or-line-feed-seperators"></a>インターチェンジで構造エラーが。 可能性の高い原因は復帰がないため、無効なセグメントの終端記号と、または改行区切り
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                   |
| 製品バージョン |                                                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                                               |
|    イベント ID     |                                                                                                                                           -                                                                                                                                           |
|  イベント ソース   |                                                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                                                 |
|    コンポーネント    |                                                                                                                                      EDI エンジン                                                                                                                                       |
|  シンボル名  |                                                                                                                        EfactInterchangeStructuralErrorAfterUnb                                                                                                                        |
|  メッセージ テキスト   | Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' 構造エラーが発生します。 可能性の高い原因は、復帰や改行の区切りがないため、無効なセグメント終端記号です。 詳細については、エラーが中断されていますが後の部分が保留キューを参照します。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインのことを示します、インターチェンジ内のセグメントに必要なセグメント終端記号がないため、パイプライン、またはバッチ処理オーケストレーション、EDIFACT インターチェンジを処理できなかったを送信します。 受信インターチェンジの区切り記号は UNA セグメントで識別されます。 または UNA セグメントが存在しない場合は、EfactDelimiters パイプライン プロパティ。 送信インターチェンジの場合は、区切り記号は、EDI のプロパティ ダイアログ ボックスの UNA セグメントの定義 ページで識別されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、インターチェンジ内のすべてのセグメントが必要なセグメント終端記号があるし、インターチェンジを再送信があるを確認します。