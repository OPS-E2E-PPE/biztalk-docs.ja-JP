---
title: トランザクション セットの重複する制御番号が見つかりました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b2779a0-b365-4c4b-81c7-8f9284748b6e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f273d7e66f4ebe942044e30adccbc7994720a99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279720"
---
# <a name="transaction-set-duplicate-control-number-found"></a>トランザクション セットの重複する制御番号が見つかりました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                          X12TsDuplicateNumberFoundDescription                          |
|  メッセージ テキスト   |                     トランザクション セットの重複する制御番号が見つかりました                     |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインで受信を処理できなかったことを示します X12 インターチェンジのトランザクション セット制御番号のトランザクション セットのグループのため、インターチェンジは別の制御番号と同じです。トランザクションは、そのグループに設定します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   グループの変更をトランザクション セットのトランザクションの重複した制御番号がないため、受信インターチェンジのトランザクションの数を設定するコントロールを設定します。  
  
-   次のように、重複するトランザクション セット制御番号のチェックを無効にします。  
  
    1.  BizTalk Server 管理コンソールを開きます。  
  
    2.  インターチェンジの送信元パーティの EDI のプロパティ ダイアログ ボックスを開きます。  
  
    3.  X12 インターチェンジのチェック ボックスをオフの場合、"重複している St2 (トランザクション セット制御番号) グループで"x12 EDI のプロパティ ダイアログ ボックスの処理のプロパティ ページをインターチェンジします。  
  
    4.  EDIFACT インターチェンジの場合、オフ、"チェックが重複している unh1 (トランザクション セット参照番号) グループで"EDIFACT インターチェンジ処理プロパティ ページで、[EDI のプロパティ] ダイアログ ボックスのプロパティ。