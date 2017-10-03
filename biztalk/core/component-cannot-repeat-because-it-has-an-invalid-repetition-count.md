---
title: "無効な繰り返し回数があるために、コンポーネントは繰り返すことはできません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 040d7ea4-60a9-495f-91d7-b5b868957e2d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d535d72b5f265f07e6ae3fb468ed56efdc7975b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="component-cannot-repeat-because-it-has-an-invalid-repetition-count"></a>コンポーネントを繰り返すことはできません。無効な繰り返し回数が指定されています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|SchemaCode118EInvalidRepetition|  
|メッセージ テキスト|コンポーネントを繰り返すことはできません。無効な繰り返し回数 {0} が指定されています。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、スキーマで繰り返しが許可されていないにもかかわらず、インターチェンジで要素コンポーネント、要素、セグメント、またはループが繰り返されていたため、受信パイプラインで受信インターチェンジを処理できなかったか、送信パイプラインで送信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジに要素コンポーネント、要素、セグメント、またはループの繰り返しがなく、スキーマの要件どおりであることを確認し、メッセージを再送信します。