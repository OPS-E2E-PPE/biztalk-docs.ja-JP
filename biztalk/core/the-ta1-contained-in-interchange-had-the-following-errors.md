---
title: "インターチェンジに含まれている TA1 次のエラーが発生しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2d63fe9-63ef-44b3-8cb9-45a7abf8d0e4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03bd7486d25e2c94fc809e6dc50c43359c152b70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-ta1-contained-in-interchange-had-the-following-errors"></a>インターチェンジに含まれている TA1 で次のエラーが発生しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12TA1Error|  
|メッセージ テキスト|Id '{1}'、送信者 id '{2}' を持つインターチェンジに含まれている TA1 {0}、受信者 id '{3}' 次のエラーが発生しました。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、示されたエラー状態のため、受信パイプラインで受信 TA1 受信確認を処理できなかったことを示します。 これは、受信確認が TA1Schema に準拠していないことを示している可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、受信確認の送信者に対して、受信確認の問題を解決し、受信確認が TA1Schema に準拠していることを確認して、受信確認を再送信するように依頼します。