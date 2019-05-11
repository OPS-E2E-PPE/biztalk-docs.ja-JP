---
title: シリアル化中に発生したエラーです。 X12 インターチェンジで次のエラーが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9ca3314-6c66-4400-816a-f9c7c7915122
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12ddd3879581387e776728a35b045ae1ac36a2b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388905"
---
# <a name="error-encountered-during-serialization-the-x12-interchange-had-the-following-errors"></a>シリアル化中に発生したエラーです。 X12 インターチェンジで次のエラーが見つかりました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| 製品バージョン |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    イベント ID     |                                                                      -                                                                      |
|  イベント ソース   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                            |
|    コンポーネント    |                                                                 EDI エンジン                                                                  |
|  シンボル名  |                                                           X12InterchangeSendError                                                           |
|  メッセージ テキスト   | シリアル化中に発生したエラーです。 X12 インターチェンジ id '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI 送信パイプラインでは、X12 の送信をシリアル化するときに、エラーが発生したことを示します、示されたエラーのために交換します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用して、インターチェンジでエラーを特定し、製品のヘルプで問題の解決方法を確認します。