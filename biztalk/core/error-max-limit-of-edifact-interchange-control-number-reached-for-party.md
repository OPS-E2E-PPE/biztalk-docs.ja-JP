---
title: パーティの Edifact インターチェンジ制御番号を許容される上限に達した |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c00c357-4c7b-42ea-a031-15bad0195a75
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc41a3a7a9f128ee244a1f39fc13711f32a33666
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347602"
---
# <a name="max-limit-of-acceptable-edifact-interchange-control-number-has-reached-for-party"></a>パーティの Edifact インターチェンジ制御番号を許容される上限に達した
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| 製品バージョン |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    イベント ID     |                                                                                              -                                                                                               |
|  イベント ソース   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                    |
|    コンポーネント    |                                                                                          EDI エンジン                                                                                          |
|  シンボル名  |                                                                                  PartyEdifactUnbNumberError                                                                                  |
|  メッセージ テキスト   | パーティの Edifact インターチェンジ制御番号を許容される上限に達した{0}します。 パートナー アグリーメント マネージャーで、[Party in receiver role] の [UNB 5] フィールドに移動して、カウンターをリセットしてください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティ設定で指定された UNB5 フィールドのインターチェンジ制御番号 (具体的には、UNB5.2 フィールドの参照番号) が許容される最大値よりも大きかったため、送信パイプラインで送信インターチェンジを処理できなかったことを示します。 インターチェンジ制御番号の許容される上限値は、UNB5 の 3 つのフィールドの値によって決まります。 最大文字数は、フィールド UNB5.2 の参照番号が 14 文字、UNB5.1 のプレフィックスが 13 文字、UNB5.3 のサフィックスが 13 文字、3 つすべてのフィールドの組み合わせで 14 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように、インターチェンジ制御番号の参照番号フィールド (UNB5.2) をリセットします。  
  
1.  インターチェンジに対して解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、インターチェンジの受信者としてのパーティの [UNB セグメントの定義] ページを開きます。  
  
2.  UNB5 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  インターチェンジ制御番号 (UNB5.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。