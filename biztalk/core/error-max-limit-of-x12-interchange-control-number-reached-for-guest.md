---
title: インターチェンジ制御番号が Guest の設定に達すると、許容される X12 上限 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9737053d-6065-4c88-8dfa-5f69b48e0e82
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c72fc565367477d9dbd09f3c0d4c4f9d6ab686a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241674"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-guest-settings"></a>Guest の設定の X12 インターチェンジ制御番号が、許容される上限に到達しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|GlobalX12IsaNumberError|  
|メッセージ テキスト|Guest の設定の X12 インターチェンジ制御番号が、許容される上限に到達しました。 パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [ISA 13] フィールドに移動して、カウンターをリセットしてください。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、グローバル設定で指定された ISA13 フィールドのインターチェンジ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。 インターチェンジ制御番号の最大文字数は 9 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジ制御番号を次のようにリセットします。  
  
1.  [EDI グローバル プロパティ] ダイアログ ボックスで、[ISA セグメントの定義] ページを開きます。  
  
2.  ISA13 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  フィールドの桁数が許容値になるように、インターチェンジ制御番号に新しい値を設定します。