---
title: "必要なよりも小さいを繰り返す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5bebc13-0e70-4f73-99c0-fed917d79fba
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d88fe1868a91bce7208c0da557f20211cde23109
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="repeats-less-than-required"></a>繰り返しが必要な回数を下回っています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12FeRepeatsLessThanRequiredDescription|  
|メッセージ テキスト|繰り返しが必要な回数を下回っています|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、X12 インターチェンジのループ内またはループ外にあるセグメントの繰り返しが、ドキュメント スキーマで必要な回数を下回っていたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのループの内側または外側にあるセグメントがスキーマで指定された回数繰り返されることを確認し、インターチェンジを再送信します。