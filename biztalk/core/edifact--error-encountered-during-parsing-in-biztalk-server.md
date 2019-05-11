---
title: 解析中に発生したエラーです。 Edifact インターチェンジ、グループが含まれていませんでしたが、次のエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6b324fd-f365-41b9-81aa-b6c5c5d3f673
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ace43a641e08265852212d25750977ba5f95398c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350194"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a>解析中に発生したエラーです。 グループを含まない Edifact インターチェンジには、次のエラーがありました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| 製品バージョン |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    イベント ID     |                                                                                           -                                                                                           |
|  イベント ソース   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                 |
|    コンポーネント    |                                                                                      EDI エンジン                                                                                       |
|  シンボル名  |                                                                     EfactFunctionalGroupReceiveErrorWithoutGroup                                                                      |
|  メッセージ テキスト   | 解析中に発生したエラーです。 Edifact インターチェンジのインターチェンジ id を持つ、グループを含まない '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントを示します、EDI 受信パイプラインでは、示されたエラーのため、グループを含まない受信 EDIFACT インターチェンジの解析中にエラーが発生しました。 グループは、EDIFACT インターチェンジで省略可能なことに注意してください。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してエラーを特定し、製品のヘルプで問題の解決方法を決定します。