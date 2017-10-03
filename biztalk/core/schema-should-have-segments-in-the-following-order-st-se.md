---
title: "スキーマには ST .... SE の順序でセグメントが記述されている必要がありますSE |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f4d1c6a-7d48-413a-9ef5-a0c49773dc16
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2563247dc6fc4c092fe2867c6b4d03239c4be7e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a>スキーマには ST .... SE の順序でセグメントが記述されている必要がありますSE
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|SchemaCode116ETransactionSetSchemaStSeOutOfOrder|  
|メッセージ テキスト|スキーマには ST .... SE の順序でセグメントが記述されている必要がありますSE|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ヘッダーとトレーラーが正しい順序で記述されていなかったため、カスタム ドキュメント スキーマが無効であることを示します。 スキーマが展開されると、BizTalk Server によってこの検証が実行されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、カスタマイズされたドキュメント スキーマを変更し、ヘッダーとトレーラーを正しい順序で記述して、スキーマを再展開します。