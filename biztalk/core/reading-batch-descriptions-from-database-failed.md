---
title: "Database が失敗しましたからの読み取りバッチの説明 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f959aa35-d957-45b0-bfac-1134b5087d0c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66a9049c9f3964b231d7c1370784bccd78fd0836
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="reading-batch-descriptions-from-database-failed"></a>データベースからのバッチの説明の読み取りが失敗しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|LoadBatchFiltersFailed|  
|メッセージ テキスト|データベースからのバッチの説明の読み取りが失敗しました。 エラー: {0}。 スタック トレース: {1} です。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server が、受信メッセージのコンテキスト プロパティを比較するために構成されたバッチ用に指定されたフィルターを読み込めなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、管理データベースが起動していて、接続できることを確認します。