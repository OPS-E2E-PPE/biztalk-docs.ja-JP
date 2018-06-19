---
title: 制御スキーマが正しい順序でヘッダー セグメントを持つ必要があります |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f38e8f-243a-467f-84bd-a232ef148b4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3362bce20e1e7d31fa870a5376128d2d721c11f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237858"
---
# <a name="control-schema-should-have-header-segments-in-the-correct-order"></a>制御スキーマにはヘッダー セグメントが正しい順序で記述されている必要があります
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|制御スキーマでは、次の順序でセグメントがあります: ISA GS ST.SE GE IEA|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジ、グループ、およびトランザクション セットのヘッダーとトレーラーが、インターチェンジに正しい順序で記述されていなかったため、EDI 受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ISA、GS、および ST ヘッダーと、SE、GE、および IEA トレーラーが、インターチェンジに正しい順序で記述されていることを確認してから、インターチェンジを再送信します。