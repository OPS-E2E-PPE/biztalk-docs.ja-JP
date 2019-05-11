---
title: パーティの Edifact 機能グループ制御番号を許容される上限に達した |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fde516b-59f1-49a1-8456-127469df0e02
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0677d4c3ba2e99d1c5734f9f373fedc950fe127
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347595"
---
# <a name="max-limit-of-acceptable-edifact-functional-group-control-number-has-reached-for-party"></a>パーティの Edifact 機能グループ制御番号を許容される上限に達した
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                         |
| 製品バージョン |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                     |
|    イベント ID     |                                                                                                 -                                                                                                 |
|  イベント ソース   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                       |
|    コンポーネント    |                                                                                            EDI エンジン                                                                                             |
|  シンボル名  |                                                                                    PartyEdifactUngNumberError                                                                                     |
|  メッセージ テキスト   | パーティの Edifact 機能グループ制御番号を許容される上限に達した{0}します。 パートナー アグリーメント マネージャーで、[Party in receiver role] の [UNG 5] フィールドに移動して、カウンターをリセットしてください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティ設定で指定された UNG5 フィールド内のグループ制御番号 (具体的には UNG5.2 フィールド内の参照番号) が許容される最大値より大きかったため、送信パイプラインで送信 EDIFACT インターチェンジを処理できなかったことを示します。 グループ制御番号の最大許容値は UNG5 の 3 つのフィールドの値によって決まります。 最大文字数は、フィールド UNG5.2 の参照番号が 14 文字、UNG5.1 のプレフィックスと UNG5.3 のサフィックスでは 13 文字、これらすべてのフィールドの組み合わせで 14 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように、グループ制御番号の参照番号フィールド (UNG5.2) をリセットします。  
  
1.  インターチェンジに対して解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、インターチェンジの受信者であるパーティの [UNG および UNH セグメントの定義] ページを開きます。  
  
2.  UNG5 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  グループ制御番号 (UNG5.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。