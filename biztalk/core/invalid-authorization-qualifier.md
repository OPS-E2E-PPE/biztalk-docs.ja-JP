---
title: "無効な認証修飾子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc2a9f83-833f-4ea0-9421-7382ee1b1a54
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbf33e8bd42b18134bd31f02f791b306ece97272
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-authorization-qualifier"></a>認証修飾子が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12Ta1InvalidAuthorizationQualifierDescription|  
|メッセージ テキスト|認証修飾子が無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ISA01 の認証修飾子の値が、スキーマで指定されているいずれの列挙値とも一致しなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。 スキーマは、BaseArtifacts.dll 内の X12ServiceSchema です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ISA01 ヘッダーの値が X12ServiceSchema で指定されている列挙値の 1 つに一致することを確認し、インターチェンジを再送信してもらいます。