---
title: AS2 デコーダーが廃棄通知-オプションの HTTP ヘッダーを見つけられませんでした |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6de4b9a6-17b2-4455-9dbd-a6bb69fac1d5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ef3f6f9e571f3469c2bd0de163f7ada90d0be7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388972"
---
# <a name="the-as2-decoder-was-unable-to-locate-the-disposition-notification-options-http-header"></a>AS2 デコーダーが廃棄通知-オプションの HTTP ヘッダーを見つけられませんでした。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                      |
| 製品バージョン |                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                  |
|    イベント ID     |                                                              -                                                              |
|  イベント ソース   |                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                    |
|    コンポーネント    |                                                         AS2 エンジン                                                          |
|  シンボル名  |                               AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError                                |
|  メッセージ テキスト   | AS2 デコーダは、MDN の生成に必要な Disposition-Notification-Options HTTP ヘッダーを見つけられませんでした。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信 AS2 メッセージに、MDN が署名されている必要があるかどうかと、使用する必要がある MIC アルゴリズムを示す Disposition-Notification-Options ヘッダーが含まれていなかったため、受信パイプラインで MDN を生成できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、AS2 メッセージの送信者に対して、メッセージに Disposition-Notification-Options ヘッダーを含め、メッセージを再送信するように依頼します。