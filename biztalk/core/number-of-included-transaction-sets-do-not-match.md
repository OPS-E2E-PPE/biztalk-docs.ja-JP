---
title: "含まれているトランザクション セットの数が一致しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db958803-4667-4558-81a6-70c62d6fe8bf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16a28544757c3e9ae75dd7230673c4526fc2c8f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="number-of-included-transaction-sets-do-not-match"></a>含まれているトランザクション セットの数が一致しません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12FaNumberOfTsMismatchDescription|  
|メッセージ テキスト|含まれているトランザクション セットの数が一致しません|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、X12 インターチェンジのグループのトランザクション セット数が、グループ トレーラー (GE01 フィールド) の数と等しくないことを示します。 これは、インターチェンジが保存されて、インターチェンジがエラーで中断されている場合に発生します。 (インターチェンジが保存され、トランザクション セットがエラーで中断している場合、またはインターチェンジが分割されている場合、エラー メッセージは通知されません)。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、グループ トレーラーの GE01 フィールドの数が、インターチェンジのグループのトランザクション セット数と同じであることを確認し、インターチェンジを再送信します。