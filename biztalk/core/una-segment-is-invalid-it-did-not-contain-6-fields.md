---
title: "UNA セグメントが無効です。 6 個のフィールドがありませんでした |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c939d8d3-e6fb-4505-836d-31559fc5f1a3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00d2a66e414bfe41e03c1e096034a620369064b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="una-segment-is-invalid-it-did-not-contain-6-fields"></a>UNA セグメントが無効です。 6 個のフィールドが含まれていませんでした
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|UnaDidNotContainSixDelimiters|  
|メッセージ テキスト|UNA セグメントが無効です。 6 個のフィールドが含まれていませんでした|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、UNA セグメントに含まれているデータ要素が 6 個未満だったため、受信パイプラインで受信 EDIFACT インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者に対して、UNA セグメントに 6 個のデータ要素を含めるよう依頼し、インターチェンジを再送信します。