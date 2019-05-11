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
ms.openlocfilehash: c2dfa36a5814b270da64eb95dc8e082a91674003
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325023"
---
# <a name="message-part-missing-element"></a>メッセージ部分の要素が見つかりません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  製品名   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| 製品バージョン |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    イベント ID     |                                                         0                                                          |
|  イベント ソース   |                                                         0                                                          |
|    コンポーネント    |                                                         0                                                          |
|  シンボル名  |                                                         0                                                          |
|  メッセージ テキスト   | メッセージ部分に不足している要素。 サービスの説明を修正"{0}「メッセージの種類」{1}「パーツ」{2}"し、ウィザードを再実行 |
  
## <a name="explanation"></a>説明  
 このエラーは、使用しようとするサービスがメッセージの種類を識別する要素タグを持たないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 適切なメッセージの種類、サービスを修正して、(使用しようとしている WCF サービスを所有) 場合に使用する再試行してください。 それ以外の場合、サービス プロバイダーに問い合わせてください。  
  
 メッセージの詳細についてで、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [Web メッセージの構築](../core/constructing-web-messages.md)