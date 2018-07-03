---
title: メッセージ部分の要素がありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b519315f-d51d-4ca3-a0e6-d08bb920c6c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 412b25d2f7ea027de53818b032b50562faab9865
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009443"
---
# <a name="message-part-missing-element"></a>メッセージ部分に要素が見つかりません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  製品名   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| 製品バージョン |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    イベント ID     |                                                         0                                                          |
|  イベント ソース   |                                                         0                                                          |
|    コンポーネント    |                                                         0                                                          |
|  シンボル名  |                                                         0                                                          |
|  メッセージ テキスト   | メッセージ部分に要素が見つかりません。 サービスの説明を修正"{0}「メッセージの種類」{1}「パーツ」{2}"し、ウィザードを再実行 |
  
## <a name="explanation"></a>説明  
 このエラーは、使用するサービスに、メッセージの種類を識別する要素タグがないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 サービスを適切なメッセージの種類に修正し、使用します (使用しようとしている WCF サービスを所有している場合)。 それ以外の場合、サービス プロバイダーに問い合わせてください。  
  
 メッセージの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [Web メッセージの構築](../core/constructing-web-messages.md)