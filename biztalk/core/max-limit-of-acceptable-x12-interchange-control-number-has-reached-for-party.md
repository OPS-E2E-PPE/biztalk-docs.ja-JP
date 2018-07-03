---
title: パーティのインターチェンジ制御番号に到達する許容される X12 上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc49089-3c7b-4ce2-9fbc-68e582c3a822
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de22f059a720fdec999f495f38a6b21009469158
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986307"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-party"></a>パーティの X12 インターチェンジ制御番号が、許容される上限に到達しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| 製品バージョン |                                                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    イベント ID     |                                                                                             -                                                                                             |
|  イベント ソース   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                   |
|    コンポーネント    |                                                                                        EDI エンジン                                                                                         |
|  シンボル名  |                                                                                  PartyX12IsaNumberError                                                                                   |
|  メッセージ テキスト   | パーティのインターチェンジ制御番号に到達する許容される X12 上限{0}します。 パートナー アグリーメント マネージャーで、[Party in receiver role] の [ISA 13] フィールドに移動して、カウンターをリセットしてください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティ設定で指定された ISA13 フィールドのインターチェンジ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。 インターチェンジ制御番号の最大文字数は 9 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジ制御番号を次のようにリセットします。  
  
1.  インターチェンジに対して解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、インターチェンジの受信者としてのパーティの [ISA セグメントの定義] ページを開きます。  
  
2.  ISA13 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  フィールドの桁数が許容値になるように、インターチェンジ制御番号に新しい値を設定します。