---
title: パーティのトランザクション セット制御番号に達した許容される Edifact 上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a64cc5d3-a845-4044-9c6e-879ecda15fce
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58c2495b0e7eecf7c16ecdf067ed03d8e1a333d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347452"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-party"></a>パーティの許容の Edifact トランザクション セット制御番号の上限に達した
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| 製品バージョン |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    イベント ID     |                                                                                                -                                                                                                 |
|  イベント ソース   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                      |
|    コンポーネント    |                                                                                            EDI エンジン                                                                                            |
|  シンボル名  |                                                                                   GlobalEdifactUnhNumberError                                                                                    |
|  メッセージ テキスト   | パーティのトランザクション セット制御番号に達した許容される Edifact 上限{0}します。 Party in receiver role のパートナー アグリーメント マネージャーで UNH 1 フィールドに移動して、カウンターをリセットします。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、送信パイプラインがパーティ設定で、フィールド UNH1.2 の参照番号では具体的には指定された UNH1 フィールドのトランザクション セット制御番号があるために、送信インターチェンジを処理できませんでしたことを示します。許容される最大値より大きい。 トランザクション セット制御番号の最大許容値は UNH1 の 3 つのフィールドの値によって決まります。 最大文字数が、フィールド UNH1.2、unh1.1 のプレフィックスと、UNH1.3 のサフィックスの 13 および 14 を組み合わせた 3 つのフィールドの参照番号が 14 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように、トランザクション セット制御番号の参照番号フィールド (UNH1.2) をリセットします。  
  
1.  インターチェンジに対して解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、[UNG および UNH セグメントの定義] ページを開きます。  
  
2.  UNH1 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  トランザクション セット制御番号 (UNH1.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。