---
title: トランザクション セット制御番号シーケンスが終了パートナーと TPA の |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f194ca-3e0f-4ad4-8bc8-88aa7e5193a7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40d87b1f2681bb07816721971cfbd17d2c3a0b91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278338"
---
# <a name="transaction-set-control-number-sequence-exhausted-for-partner-and-tpa"></a>パートナーと TPA のトランザクション セット制御番号のシーケンスが終了しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EdiControlNumberExhaustedForParty|  
|メッセージ テキスト|トランザクション セット制御番号のシーケンスが終了 TPA '{2}' の 'パートナー '{1} です。 {2} - BizTalk Server 管理コンソールを使用して EDI プロパティでシーケンスをリセットします。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server がドキュメントのため、トランザクション セット制御の範囲が使い果たされた {2} でアグリーメントを処理することを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、チェックを {2} アグリーメントの制御番号をリセットまたは制御番号の範囲を増やすか、アグリーメントでは、制御番号範囲指定に対するリセット ボタンをクリックします。