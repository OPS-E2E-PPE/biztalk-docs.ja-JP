---
title: 許容の X12 トランザクション セット制御番号が Guest の設定に到達上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5a4aa5c-13a7-4234-916e-562b52644c51
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f35efea65a1ee4741c86679797f5f218a1cbaf0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347442"
---
# <a name="max-limit-of-acceptable-x12-transaction-set-control-number-has-reached-for-guest-settings"></a>許容される X12 トランザクション セット制御番号に達した Guest の設定の上限
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| 製品バージョン |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    イベント ID     |                                                                                                     -                                                                                                      |
|  イベント ソース   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                           |
|    コンポーネント    |                                                                                                 EDI エンジン                                                                                                 |
|  シンボル名  |                                                                                           GlobalX12TsNumberError                                                                                           |
|  メッセージ テキスト   | Guest の設定の X12 トランザクション セット制御番号が、許容される上限に到達しました。 パートナー アグリーメント マネージャーで、[Global configuration sender role] の [ST 2] フィールドに移動して、カウンターをリセットしてください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、グローバル設定で指定された ST02 フィールドのトランザクション セット制御番号 (具体的には ST02.2 フィールドの参照番号) が、許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。 トランザクション セット制御番号の最大許容値は ST02 の 3 つのフィールドの値によって決まります。 最大文字数は、フィールド UNH1.2 の参照番号が 9 文字、UNH1.1 のプレフィックスが 8 文字、UNH1.3 のサフィックスが 8 文字、3 つすべてのフィールドの組み合わせで 9 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のようにして、トランザクション セット制御番号の参照番号フィールド (ST02.2) をリセットします。  
  
1.  [EDI グローバル プロパティ] ダイアログ ボックスで、[GS および ST セグメントの定義] ページを開きます。  
  
2.  ST02 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  グループ制御番号 (ST02.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。