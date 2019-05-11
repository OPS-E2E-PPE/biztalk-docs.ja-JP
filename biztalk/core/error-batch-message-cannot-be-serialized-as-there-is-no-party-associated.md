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
ms.openlocfilehash: c50695adab39c40ba6d09876e7bc7b80fa4e8a4f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349101"
---
# <a name="batch-message-cannot-be-serialized-as-there-is-no-party-associated-with-send-port"></a>送信ポートに関連付けられたパーティが存在しないために、バッチ メッセージをシリアル化することはできません。
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