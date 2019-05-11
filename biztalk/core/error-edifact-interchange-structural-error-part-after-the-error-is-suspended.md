---
title: インターチェンジで構造エラーが。 中断されていますが、エラー後の部分 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9071825d-7b90-42bf-bcf9-2a15ae36086d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ebfeec80fb9775fbb99c07fc1c694f38f6b11c7
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530754"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a>インターチェンジで構造エラーが。 中断されていますが、エラー後の部分
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| 製品バージョン |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    イベント ID     |                                                                                       -                                                                                        |
|  イベント ソース   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                             |
|    コンポーネント    |                                                                                   EDI エンジン                                                                                   |
|  シンボル名  |                                                                        EfactInterchangeStructuralError                                                                         |
|  メッセージ テキスト   | Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' 構造エラーが発生します。 詳細については、エラーが中断されていますが後の部分が保留キューを参照します。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジで構造エラーが発生したために、受信パイプラインが受信 EDIFACT インターチェンジを処理しないことを示します。 エラーで中断されたトランザクション セットを持つ、保持されているインターチェンジでこれが発生しました。 このエラーをトランザクション セット (またはセット) の結果であり、エラーが含まれているが中断されたが、トランザクションの残りの部分の設定は、保存されたバッチの一部として処理されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、構造のエラーでは、インターチェンジの送信者し、インターチェンジを再送信します。