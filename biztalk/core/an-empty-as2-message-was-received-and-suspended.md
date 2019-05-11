---
title: 空の AS2 メッセージが受信され、中断 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 349f7134-d039-44ab-b2b3-d378d38dfd38
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1c99776d350f556855b541290fac1f6a65f5921
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360256"
---
# <a name="an-empty-as2-message-was-received-and-suspended"></a>空の AS2 メッセージが受信され、中断
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |           空の AS2 メッセージを受信しました。  メッセージは中断されます。           |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージに本文が含まれていないため、BizTalk Server が受信 AS2 メッセージを処理できなかったことを示します。 本文は 2 回の復帰/改行によってヘッダーと区切られている必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
-   AS2 メッセージの送信前に、送信元のパーティによってメッセージに必ず本文 (2 回の復帰/改行によってヘッダーと区切られている) が追加されるようにします。