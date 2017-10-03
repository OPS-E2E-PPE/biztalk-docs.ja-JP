---
title: "シングル サインオン: イベント 10612 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9d9e6f5-06b8-4989-a0dc-6e2e5980443b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a85361bf9946efc283683d41ed0d08187e4d8754
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10612"></a>シングル サインオン: イベント 10612
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10612|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_TRANSACTION_TIMEOUT|  
|メッセージ テキスト|トランザクションのタイムアウト値が、この操作で推奨される最大値を超えています。 Details.%r のマニュアルを参照してください。<br /><br /> トランザクション ID: %1 %r<br /><br /> トランザクションのタイムアウト: %2 分 (0 は、無限のタイムアウトを示します) %r<br /><br /> 推奨される最大値: %3 分|  
  
## <a name="explanation"></a>説明  
 非常に大きなタイムアウト値が設定されたトランザクションがシステムで処理されています。 実行時間の長いトランザクションによってロックされているときに ENTSSO システムが SSO データベースをポーリングした場合、システムは最終的にはオフラインになります。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザーによる操作は不要です。