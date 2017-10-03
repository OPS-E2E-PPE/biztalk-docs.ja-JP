---
title: "バッチ ID と関連付けられているアグリーメントが有効ではないか、または期限切れです。 バッチ処理を続行できません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d92cb07-7646-42b3-90a8-18acbcd145cd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e68e91fe1cd2d91c20c84a32afd37212769a4736
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-agreement-associated-with-batchid-is-not-enabled-or-has-expired-batching-cannot-continue"></a>バッチ ID と関連付けられているアグリーメントが有効ではないか、または期限切れです。 バッチ処理を続行できません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|ErrorBatchAgreementDisabled|  
|メッセージ テキスト|バッチ ID {0} と関連付けられているアグリーメントが有効ではないか、または期限切れです。 バッチ処理を続行できません。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、アグリーメントが期限切れのために、BizTalk Server がバッチを開始できなかったか、またはバッチ メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、指定された ID のバッチが、親アグリーメントの [アグリーメント] プロパティに存在し、その開始日と終了日がアグリーメントの開始日と終了日の範囲内であることを確認します。 また、アグリーメントが有効になっていることを確認します。