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
ms.openlocfilehash: c539b6a3380001927f02bf3d828b707a7807cf4f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388719"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-guest-settings"></a>許容される Edifact トランザクション セット制御番号の上限に達した Guest の設定
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
| 製品バージョン |                                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                             |
|    イベント ID     |                                                                                                         -                                                                                                          |
|  イベント ソース   |                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                               |
|    コンポーネント    |                                                                                                     EDI エンジン                                                                                                     |
|  シンボル名  |                                                                                            GlobalEdifactUnhNumberError                                                                                             |
|  メッセージ テキスト   | Guest の設定が、許容される Edifact トランザクション セット制御番号の上限に到達します。 Global configuration receiver role のパートナー アグリーメント マネージャーで UNH 1 フィールドに移動して、カウンターをリセットします。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、具体的には、フィールド UNH1.2 の参照番号に、グローバルの設定で指定された UNH1 フィールドのトランザクション セット制御番号のためで、送信インターチェンジが送信パイプラインでした処理することを示します許容される最大値を超えています。 グループ制御番号の最大許容値は UNH1 の 3 つのフィールドの値によって決まります。 最大文字数が、フィールド UNH1.2、unh1.1 のプレフィックスと、UNH1.3 のサフィックスの 13 および 14 を組み合わせた 3 つのフィールドの参照番号が 14 文字です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように、トランザクション セット制御番号の参照番号フィールド (UNH1.2) をリセットします。  
  
1.  EDI グローバル プロパティ ダイアログ ボックスでは、UNH セグメントの定義 ページを開きます。  
  
2.  UNH1 フィールドに関連付けられている [編集] フィールドをクリックします。  
  
3.  フィールドがある数字の許容数になるように、新しい値に中央のフィールドのグループ制御番号 (UNH1.2 の参照番号) を設定します。