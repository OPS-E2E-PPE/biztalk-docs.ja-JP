---
title: "トランザクション セット制御番号の不一致 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c4b0c3f-f3be-4c2c-8719-8e40aa7122b9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd80bac6a5c58306a8d9ca64748ddbb8cb2bc81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-control-number-mismatch"></a>トランザクション セット制御番号が一致していません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12TsControlNumberMismatchDescription|  
|メッセージ テキスト|トランザクション セット制御番号が一致していません|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セットの SE02 フィールドに含まれている制御番号と ST02 フィールド内の制御番号が一致しなかったため、EDI 受信パイプラインで受信トランザクション セットが拒否されたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、トランザクション セットの送信者に、拒否されたトランザクション セットの SE02 フィールド内の制御番号を ST02 フィールド内の制御番号と同じになるように変更してもらい、インターチェンジを再送信します。