---
title: "Edifact トランザクション セットが UNT01 に一致しないカウントが |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2859274-78e8-4e16-92b7-c143da6da421
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 180abe338441917afa6691400a02a42e88026052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a>EDIFACT トランザクション セットの UNT01 に一致しないカウントがあります
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EfactUnhUntCountMismatch|  
|メッセージ テキスト|EDIFACT トランザクション セットの UNT01 に一致しないカウントがあります。 UNT01 {0} でした、一方 {1} されている必要があります。 問題の修正が完了しました。|  
  
## <a name="explanation"></a>説明  
 この警告は、セグメント カウントである UNT01 フィールドが、トランザクション セットのセグメント数に一致しなかったことを示します。 UNT01 の値が変更されたか壊れている、またはカウントの決定後にセグメントが追加あるいは削除されました。 送信パイプラインが UNT01 フィールドを正しいセグメント数にリセットし、インターチェンジを送信しました。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザーの操作は必要ありません。