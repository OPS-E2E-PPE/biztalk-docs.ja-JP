---
title: シリアル化中に発生したエラーです。 X12 機能グループが、次のエラーがありました。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dad987c3-92f3-4a6b-ba1a-b60f6ea2fbe4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a461a5db58a2ca41fdd7e42211fbb798bc6e197
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394757"
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a>シリアル化中に発生したエラーです。 X12 機能グループが、次のエラーがありました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                |
| 製品バージョン |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                            |
|    イベント ID     |                                                                                        -                                                                                        |
|  イベント ソース   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                              |
|    コンポーネント    |                                                                                   EDI エンジン                                                                                    |
|  シンボル名  |                                                                           X12FunctionalGroupSendError                                                                           |
|  メッセージ テキスト   | シリアル化中に発生したエラーです。 X12 機能グループ id '{0}'、id を持つインターチェンジ内で'{1}'、送信者 id '{2}'、受信者 id'{3}' 次のエラーが発生しました。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI 送信パイプラインでは、X12 の送信をシリアル化するときに、エラーが発生したことを示しますインターチェンジで識別された機能グループ、示されたエラーが原因です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用して機能グループでエラーを特定し、製品のヘルプで問題の解決方法を決定します。