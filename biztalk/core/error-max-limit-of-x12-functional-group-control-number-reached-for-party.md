---
title: パーティの機能グループ制御番号に達した許容される X12 上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a920a66c-1e38-4f4a-8113-cbad01940839
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5ba87e528063e8c4ba4159d9a0fbb299d55c236
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347457"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-party"></a>許容される X12 機能グループ制御番号に達してパーティの上限
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| 製品バージョン |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    イベント ID     |                                                                                              -                                                                                               |
|  イベント ソース   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                    |
|    コンポーネント    |                                                                                          EDI エンジン                                                                                          |
|  シンボル名  |                                                                                    PartyX12GsNumberError                                                                                     |
|  メッセージ テキスト   | パーティの機能グループ制御番号に達した許容される X12 上限{0}します。 パートナー アグリーメント マネージャーで、[Party in receiver role] の [GS 6] フィールドに移動して、カウンターをリセットしてください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティ設定で指定された GS06 フィールドのグループ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。 グループ制御番号の最大文字数は 9 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、グループ制御番号を次のようにリセットします。  
  
1.  インターチェンジに解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、インターチェンジの受信者のパーティに対する [GS および ST セグメントの定義] ページを開きます。  
  
2.  GS06 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  フィールドの桁数が 9 以下になるように、グループ制御番号に新しい値を設定します。