---
title: "深いレベルで、終了要素が見つかりませんでした |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1edb60a-122a-4fe9-8d73-96521fe7326b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a90265b4348e4d35b66099f426b6f6177851ccc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="an-end-element-could-not-be-found-at-depth"></a>深さの終了要素が見つかりませんでした
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EndElementNotFoundAtDepth|  
|メッセージ テキスト|深さ {0} の終了要素が見つかりませんでした|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、XML メッセージの検証に失敗したため、BizTalk Server が送信インターチェンジを処理できなかったことを示します。 XML メッセージに、ヘッダーまたはデータ要素の終了タグが含まれていませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、XML メッセージに適切な終了タグまたはトレーラーを追加し、再送信します。