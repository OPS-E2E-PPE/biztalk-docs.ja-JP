---
title: 'インターチェンジで構造エラーが。 最後の構造上有効な機能グループ ID が: |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23055c421a847835ceac3ea96286794e73cb5dcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346220"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a>インターチェンジで構造エラーが。 最後の機能グループの構造上有効な ID は次のとおりでした。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                 |
| 製品バージョン |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                             |
|    イベント ID     |                                                                         -                                                                          |
|  イベント ソース   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                               |
|    コンポーネント    |                                                                     EDI エンジン                                                                     |
|  シンボル名  |                                                     X12InterchangeStructuralErrorAfter1stGroup                                                     |
|  メッセージ テキスト   | Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' 構造エラーが発生します。 最後の構造上有効な機能グループ ID が '{3}' |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインで受信を処理できなかったことを示します X12 インターチェンジで構造エラーが表示された機能グループの後に、インターチェンジで発生したためです。 これは、エラーで中断されたトランザクション セットを持つ、保持されているインターチェンジで発生した可能性があります。 このエラーをトランザクション セット (またはセット) の結果であり、エラーが含まれているが中断されたが、トランザクションの残りの部分の設定は、保存されたバッチの一部として処理されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、構造のエラーでは、インターチェンジの送信者し、インターチェンジを再送信します。