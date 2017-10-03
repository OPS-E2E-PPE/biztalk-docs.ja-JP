---
title: "無効な AS2-パーティ用に構成名 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a203e5f2-d1d9-433f-b2bb-d679bb8fea58
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c06adc5a459f7dfd05508312494555fb2651114
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-as2-to-name-configured-for-party"></a>パーティに対して無効な AS2-To 名が構成されました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|InvalidAS2ToNameConfiguredError|  
|メッセージ テキスト|無効な AS2-名前のパーティに構成する: {0} 値: {1}|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、識別されたパーティに対して構成された AS2-To ヘッダーの値が、AS2 RFC 4130 の仕様に準拠していなかったため、AS2 エンコーダーまたはデコーダーが AS2 メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、パーティに対して構成された AS2-To ヘッダーが、AS2 RFC 4130 のセクション 6.2 の仕様に準拠していることを確認します。