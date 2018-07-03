---
title: AS2 が含まれていない AS2 メッセージを受信-ヘッダー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 343a9b41-fcd9-4508-ac65-9b6e05ec6496
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a2390406d202bebd74f45efd84fd3aae6db1137
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983467"
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-to-header"></a>AS2-To ヘッダーが含まれていない AS2 メッセージを受信しました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |           AS2-To ヘッダーが含まれていない AS2 メッセージを受信しました           |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージにメッセージの送信元を示す AS2-To ヘッダーが含まれていなかったため、BizTalk Server が受信 AS2 メッセージを処理できなかったことを表します。 AS2 メッセージには AS2-To ヘッダーが必要です。 メッセージに AS2-To ヘッダーがない場合、メッセージは中断されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
-   送信元パーティが AS2 メッセージを送信する前に、AS2 メッセージの HTTP、AS2、MIME の各ヘッダーに AS2-To ヘッダーを追加するようにしてください。