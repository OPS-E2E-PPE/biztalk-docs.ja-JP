---
title: トランザクション セットのスキーマを 1 つまたは複数のコントロールのセグメント ISA、IEA、GS、GE |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7589d8f0-c727-47df-afbc-77b0f190f3e2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff90a7ea80208f0a69ee8aca5c7593c7b6253c53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241826"
---
# <a name="transaction-set-schema-contains-one-or-more-of-control-segments-isa-iea-gs-ge"></a>トランザクション セットのスキーマに制御セグメント ISA、IEA、GS、および GE のうち 1 つ以上のセグメントが含まれています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|SchemaCode114EOtherControlSegmentsPresent|  
|メッセージ テキスト|トランザクション セットのスキーマに制御セグメント ISA、IEA、GS、および GE のうち 1 つ以上のセグメントが含まれています|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セットのドキュメント スキーマで、少なくとも 1 つの ISA、IEA、GS、または GE セグメントが定義されていたため、受信パイプラインで受信トランザクション セットを処理できなかったか、または送信パイプラインで送信トランザクション セットを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ドキュメント スキーマの展開を解除し、スキーマから ISA、IEA、GS、または GE セグメントを削除して、スキーマを再展開します。