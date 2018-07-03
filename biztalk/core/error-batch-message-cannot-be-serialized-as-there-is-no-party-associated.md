---
title: 送信ポートに関連付けられているパーティがバッチ メッセージをシリアル化することはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d697ff9c-a6d1-4a3c-9ec3-4cd496f7eec2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84915c3544ed6e4222dd7fb035808617b51e5280
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969563"
---
# <a name="batch-message-cannot-be-serialized-as-there-is-no-party-associated-with-send-port"></a>送信ポートに関連付けられたパーティが存在しないため、バッチ メッセージをシリアル化できません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| 製品バージョン |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                         |
|    イベント ID     |                                                                     -                                                                      |
|  イベント ソース   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                           |
|    コンポーネント    |                                                              バッチ処理エンジン                                                               |
|  シンボル名  |                                             BatchMessageSerializationFailureDueToMissingParty                                              |
|  メッセージ テキスト   | 送信ポートに関連付けられているパーティがバッチのメッセージはシリアライズできません{0}します。 パーティがポートに関連付けられていることを確認してください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージの送信先となるパーティを特定できなかったため、送信パイプラインが、保存されたインターチェンジを処理できなかったことを示します。 パーティを特定できなかったのは、DestinationPartyName コンテキスト プロパティが設定されていなかったためです。 その結果、送信パイプラインはエンベロープの設定を特定できませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、パススルー送信パイプライン経由でメッセージを渡し、メッセージの DestinationPartyName コンテキスト プロパティを決定します。 そのパーティが存在することを確認します。 存在しない場合は、パーティを作成し、メッセージを再送信します。