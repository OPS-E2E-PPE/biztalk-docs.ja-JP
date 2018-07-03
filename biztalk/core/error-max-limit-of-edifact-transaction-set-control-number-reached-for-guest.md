---
title: 許容される Edifact トランザクション セット制御番号に達した Guest の設定の上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3924a18c-87bc-4727-b7cd-598d3e5ade2a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0de9240d2fd5ea701f701e34698b645b272b904b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978963"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-guest-settings"></a>Guest の設定の EDIFACT トランザクション セット制御番号が、許容される上限に到達しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
| 製品バージョン |                                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                             |
|    イベント ID     |                                                                                                         -                                                                                                          |
|  イベント ソース   |                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                               |
|    コンポーネント    |                                                                                                     EDI エンジン                                                                                                     |
|  シンボル名  |                                                                                            GlobalEdifactUnhNumberError                                                                                             |
|  メッセージ テキスト   | Guest の設定の EDIFACT トランザクション セット制御番号が、許容される上限に到達しました。 パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [UNH 1] フィールドに移動して、カウンターをリセットしてください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、グローバル設定で指定された UNH1 フィールドのトランザクション セット制御番号 (具体的には、UNH1.2 フィールドの参照番号) が許容される最大値よりも大きかったため、送信パイプラインで送信インターチェンジを処理できなかったことを示します。 グループ制御番号の許容される上限値は、UNH1 の 3 つのフィールドの値によって決定します。 最大文字数が、フィールド UNH1.2、unh1.1 のプレフィックスと、UNH1.3 のサフィックスの 13 および 14 を組み合わせた 3 つのフィールドの参照番号が 14 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように、トランザクション セット制御番号の参照番号フィールド (UNH1.2) をリセットします。  
  
1.  [EDI グローバル プロパティ] ダイアログ ボックスで、[UNH セグメントの定義] ページを開きます。  
  
2.  UNH1 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  グループ制御番号 (UNH1.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。