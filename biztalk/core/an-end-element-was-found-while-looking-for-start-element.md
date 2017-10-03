---
title: "開始要素を検索中に、終了要素が見つかりました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7690744-a795-47cc-bc66-a0314a4cc320
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dacaa096b15a6f2969ed56b5bac2138876a6095
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a>StartElement の検索中に EndElement が見つかりました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EndElementFoundWhenLookingForStartElement|  
|メッセージ テキスト|{0} という名前の EndElement が見つかりましたが、StartElement 名前 {1}、深さ {2} での検索中には|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、XML メッセージが検証に失敗したため、BizTalk Server が受信 XML メッセージ (解析後) または送信 XML メッセージ (シリアル化前) を処理できなかったことを示します。 XML メッセージに、ヘッダーまたはデータ要素の終了タグが含まれていませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、XML メッセージに適切な終了タグまたはトレーラーを追加し、メッセージを再送信します。