---
title: 送信するバッチ要素がないと、パーティが構成されていないので、空のメッセージを送信できません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0752079a-173e-4de3-96f4-e5de01b799b5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a224625122fa498410dc9aed9036fe875e4b739
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346318"
---
# <a name="there-are-no-batch-elements-to-send-and-an-empty-message-cannot-be-sent-as-it-is-not-configured-for-party"></a>送信するバッチ要素がないと、パーティが構成されていないので、空のメッセージを送信できません。
## <a name="details"></a>詳細  
  
|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  製品名   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| 製品バージョン |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    イベント ID     |                                                       -                                                       |
|  イベント ソース   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI             |
|    コンポーネント    |                                                バッチ処理エンジン                                                |
|  シンボル名  |                                            EmptyMessageNotAllowed                                             |
|  メッセージ テキスト   | 送信するバッチ要素がないと、パーティが構成されていないので、空のメッセージを送信できません。 {0} |
  
## <a name="explanation"></a>説明  
 この警告は、バッチ リリースのスケジュールが設定されているもののバッチ要素が受信されておらず、空のバッチ通知が有効化されていなかったため、スケジュールに基づくバッチ処理プロセスでバッチ メッセージが送信されなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告が表示されないようにするには、次の操作を実行して空のバッチ通知を構成します。  
  
1.  BizTalk Server 管理コンソールを開きます。  
  
2.  [パーティ] ノードに移動します。  
  
3.  パーティの [EDI のプロパティ] ダイアログ ボックスを開きます。  
  
4.  [インターチェンジのバッチ作成用の設定] ノード (適切なエンコード用) をクリックします。  
  
5.  スケジューラをクリックします。  
  
6.  [空のバッチ通知を送信する] プロパティをクリックします。