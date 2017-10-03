---
title: "不足しているか、無効または重複したトランザクション セット識別子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8580aab2-9fa4-43fb-b643-10621926591e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75251d0210be4ed34a74ba0f3f5cadf84d9941b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="missing-or-invalid-or-duplicate-transaction-set-identifier"></a>トランザクション セット識別子が見つからないか、無効か、重複しています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12TsMissingOrInvalidTsIdentiferDescription2|  
|メッセージ テキスト|重複するトランザクション セット識別子 '{0}' が見つからないか無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セット ID の値 (ST01 フィールド) がないか、重複していたか、値が無効であったため、受信または送信パイプラインで X12 インターチェンジを処理できなかったことを示します。 このエラーが発生する場合は、ドキュメント スキーマに ST ヘッダーと SE トレーラーがない可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジに ST01 フィールドの値があり、スキーマに ST ヘッダーと SE トレーラーのエントリがあることを確認します。 ST01 の値が、3 桁の有効なドキュメント型の識別子であることを確認します。 ST01 フィールドが、別のトランザクション セットの ST01 フィールドと重複していないことを確認します。