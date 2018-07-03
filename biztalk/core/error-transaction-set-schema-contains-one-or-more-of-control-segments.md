---
title: 1 つのトランザクション セットのスキーマを格納またはコントロールの複数のセグメント ISA、IEA、GS、GE |Microsoft Docs
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
ms.openlocfilehash: 4f0ab50802cbb872d7ba884a8256824426fbe098
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008205"
---
# <a name="transaction-set-schema-contains-one-or-more-of-control-segments-isa-iea-gs-ge"></a>トランザクション セットのスキーマに制御セグメント ISA、IEA、GS、および GE のうち 1 つ以上のセグメントが含まれています
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                       SchemaCode114EOtherControlSegmentsPresent                        |
|  メッセージ テキスト   |    トランザクション セットのスキーマに制御セグメント ISA、IEA、GS、および GE のうち 1 つ以上のセグメントが含まれています    |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セットのドキュメント スキーマで、少なくとも 1 つの ISA、IEA、GS、または GE セグメントが定義されていたため、受信パイプラインで受信トランザクション セットを処理できなかったか、または送信パイプラインで送信トランザクション セットを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ドキュメント スキーマの展開を解除し、スキーマから ISA、IEA、GS、または GE セグメントを削除して、スキーマを再展開します。