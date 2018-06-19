---
title: 存在しないか無効なトランザクション セット識別子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 282c8128-7d23-44e2-bf44-e90e52cb5fb1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f23f44587abf67e608cff79150d9633f1707ff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263010"
---
# <a name="missing-or-invalid-transaction-set-identifier"></a>トランザクション セット識別子が見つからないか無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EfactTsMissingOrInvalidTsIdentiferDescription|  
|メッセージ テキスト|トランザクション セット識別子が見つからないか無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セット ID の値 (UNH2.1 フィールド) がないか、値が無効であったため、受信または送信パイプラインで EDIFACT インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの UNH2.1 フィールドに値が設定されていることを確認します。 UNH2.1 の値が、ドキュメントの種類を示す有効な 1 桁から 6 桁の指定子であることを確認します。