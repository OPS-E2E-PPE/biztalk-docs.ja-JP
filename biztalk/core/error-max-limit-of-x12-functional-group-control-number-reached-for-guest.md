---
title: 許容される X12 機能グループ制御番号に達した Guest の設定の上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05cba774-fa35-4694-aa34-d7151f8cd75c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a8fed734f07b8d55a349a8b20498e1c9238c8ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388691"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-guest-settings"></a>許容される X12 機能グループ制御番号に達した Guest の設定の上限
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                               |
| 製品バージョン |                                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                           |
|    イベント ID     |                                                                                                       -                                                                                                       |
|  イベント ソース   |                                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                             |
|    コンポーネント    |                                                                                                  EDI エンジン                                                                                                   |
|  シンボル名  |                                                                                          GlobalEdifactUnhNumberError                                                                                          |
|  メッセージ テキスト   | Guest の設定の X12 機能グループ制御番号が、許容される上限に到達しました。 パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [GS 6] フィールドに移動して、カウンターをリセットしてください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、グローバル設定で指定された GS06 フィールドのグループ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。 グループ制御番号の最大文字数は 9 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、グループ制御番号を次のようにリセットします。  
  
1.  [EDI グローバル プロパティ] ダイアログ ボックスで、[GS および ST セグメントの定義] ページを開きます。  
  
2.  GS06 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  フィールドの桁数が 9 以下になるように、グループ制御番号に新しい値を設定します。