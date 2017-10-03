---
title: "検証が失敗したバッチ要素が中断されています |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea5e19e8-4592-40f4-bffe-85ab27653fd5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7022041d8d47e1bfa52eb7ef45764c17ed1a2d8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-batch-element-is-being-suspended-as-it-failed-validation"></a>検証に失敗したため、バッチ要素を中断しています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|バッチ処理エンジン|  
|シンボル名|BatchElementSuspended|  
|メッセージ テキスト|検証に失敗したため、バッチ要素を中断しています。 エラー: {0}|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セットが、バッチ処理オーケストレーションによって実行された検証に失敗したため、バッチ処理オーケストレーションが、バッチ化されたインターチェンジにトランザクション セットを追加できなかったことを示します。 インターチェンジは、検証に失敗したトランザクション セットなしで生成されます。 バッチ処理オーケストレーションは EDI.BatchElementValidationFailure コンテキスト プロパティを "True" に設定します。 BatchSuspend オーケストレーションは、そのコンテキスト プロパティに基づいてメッセージを取得し、エラー情報を送信してから中断します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージに示されているように、発生したエラーをトランザクション セットの送信者に示します。 送信者に対して、検証に失敗する理由となった問題を解決し、トランザクション セットを再送信するように依頼します。