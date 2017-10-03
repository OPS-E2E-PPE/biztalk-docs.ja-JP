---
title: "バッチが見つかりませんでした |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e967e1a-b87f-4c87-a157-a6f63ba96d78
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73c3e65a806f02faeb81baa6a5263019079b0c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-batch-was-not-found"></a>バッチが見つかりませんでした
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|Err_BatchNotFound|  
|メッセージ テキスト|バッチが見つかりませんでした。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、バッチの開始/停止中、またはバッチ オーケストレーションがメッセージのバッチ処理を試行中に、BizTalk Server がバッチを見つけられなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、各バッチが親アグリーメントの [アグリーメントのプロパティ] に存在することを確認します。