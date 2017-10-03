---
title: "インターチェンジで構造エラーが見つかりました。 エラーが中断された後の部分 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9071825d-7b90-42bf-bcf9-2a15ae36086d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a028608e9843ee40c26bc7e8b158d97552a58163
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a>インターチェンジで構造エラーが見つかりました。 エラー発生後の部分は中断されています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EfactInterchangeStructuralError|  
|メッセージ テキスト|Id '{0}'、送信者 id '{1}' で、インターチェンジ受信者 id '{2}' には、構造エラーが必要があります。 エラー発生後の部分は中断されています。詳細については、保留キューを参照してください。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジで構造エラーが発生したため、受信パイプラインで受信 EDIFACT インターチェンジを処理できなかったことを示します。 このイベントは保存中のインターチェンジで発生し、トランザクション セットはエラー時に中断されました。 このエラーにより、このエラーを含むトランザクション セット (複数可) は中断されましたが、それ以外のトランザクション セットは保存されたバッチの一部として処理されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者が構造上のエラーを修正した上で、インターチェンジを再送信してもらいます。