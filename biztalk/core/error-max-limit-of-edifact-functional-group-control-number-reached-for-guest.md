---
title: Guest の設定の Edifact 機能グループ制御番号を許容される上限に達して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93ea1bd6-8c39-4d11-81a5-75d4a861e041
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736b191628807bf7ed0af647e83fb3665d4f2d65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241794"
---
# <a name="max-limit-of-acceptable-edifact-functional-group-control-number-has-reached-for-guest-settings"></a>Guest の設定の EDIFACT 機能グループ制御番号が、許容される上限に到達しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|GlobalEdifactUngNumberError|  
|メッセージ テキスト|Guest の設定の EDIFACT 機能グループ制御番号が、許容される上限に到達しました。 パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [UNG 5] フィールドに移動して、カウンターをリセットしてください。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、グローバル設定に指定されている UNG5 フィールド内のグループ制御番号 (具体的には UNG5.2 フィールド内の参照番号) が許容される最大値より大きかったため、送信パイプラインで送信インターチェンジを処理できなかったことを示します。 グループ制御番号の最大許容値は UNG5 の 3 つのフィールドの値によって決まります。 最大文字数は、フィールド UNG5.2 の参照番号が 14 文字、UNG5.1 のプレフィックスと UNG5.3 のサフィックスでは 13 文字、これらすべてのフィールドの組み合わせで 14 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように、グループ制御番号の参照番号フィールド (UNG5.2) をリセットします。  
  
1.  [EDI グローバル プロパティ] ダイアログ ボックスで、[UNG および UNH セグメントの定義] ページを開きます。  
  
2.  UNG5 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  グループ制御番号 (UNG5.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。