---
title: "BizTalk メッセージ本文の要素が指定されていない |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af5d63c0-af96-4e34-828f-d29638cdf46d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf79c8896169a06df66a8484377816c9897531e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-message-body-element-not-specified"></a>BizTalk メッセージ本文要素が指定されていません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|BizTalk メッセージ本文要素が指定されていません|  
  
## <a name="explanation"></a>説明  
 このエラーは、送信 WCF メッセージにテンプレート オプションが使用されていることを示します。 一方で、テンプレート式には BizTalk メッセージ本文要素が含まれません。  
  
## <a name="user-action"></a>ユーザーの操作  
 テンプレート式に次の要素が含まれていることを確認します\< **bts メッセージ本文の xmlns ="http://www.microsoft.com/schemas/bts2007"encoding ="[xml (&) #124; base64 &#124; 16 進数 (&) #124; 文字列]"/** 。>。