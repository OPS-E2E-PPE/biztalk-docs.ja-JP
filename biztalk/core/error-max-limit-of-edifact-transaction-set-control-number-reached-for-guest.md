---
title: 許容される Edifact トランザクション セット制御番号に達した Guest の設定の上限 |Microsoft ドキュメント
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
ms.openlocfilehash: 709d6069d143cea2271e6311fad571a0290133db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241154"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-guest-settings"></a>Guest の設定の EDIFACT トランザクション セット制御番号が、許容される上限に到達しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|GlobalEdifactUnhNumberError|  
|メッセージ テキスト|Guest の設定の EDIFACT トランザクション セット制御番号が、許容される上限に到達しました。 パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [UNH 1] フィールドに移動して、カウンターをリセットしてください。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、グローバル設定で指定された UNH1 フィールドのトランザクション セット制御番号 (具体的には、UNH1.2 フィールドの参照番号) が許容される最大値よりも大きかったため、送信パイプラインで送信インターチェンジを処理できなかったことを示します。 グループ制御番号の許容される上限値は、UNH1 の 3 つのフィールドの値によって決定します。 最大文字数は、フィールド UNH1.2、UNH1.1 のプレフィックスが 13 と 13、UNH1.3 のサフィックス、組み合わせるすべての 3 つのフィールドの 14 の参照番号の 14 です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように、トランザクション セット制御番号の参照番号フィールド (UNH1.2) をリセットします。  
  
1.  [EDI グローバル プロパティ] ダイアログ ボックスで、[UNH セグメントの定義] ページを開きます。  
  
2.  UNH1 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  グループ制御番号 (UNH1.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。