---
title: シリアル化中に発生したエラーです。 Edifact インターチェンジで次のエラーが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc933ac-161a-41e5-b67d-9f15e569d5c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346135947ea0b0f154178d67f29335a13a95526a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350022"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-had-the-following-errors"></a>シリアル化中に発生したエラーです。 Edifact インターチェンジには、次のエラーが発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                |
| 製品バージョン |                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                            |
|    イベント ID     |                                                                        -                                                                         |
|  イベント ソース   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                              |
|    コンポーネント    |                                                                    EDI エンジン                                                                    |
|  シンボル名  |                                                            EfactInterchangeSendError                                                             |
|  メッセージ テキスト   | シリアル化中に発生したエラーです。 Edifact インターチェンジ id '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI 送信パイプラインでは、識別されたインターチェンジで示されたエラーのため送信 EDIFACT インターチェンジをシリアル化するときに、エラーが発生したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用して、インターチェンジでエラーを特定し、製品のヘルプで問題の解決方法を確認します。