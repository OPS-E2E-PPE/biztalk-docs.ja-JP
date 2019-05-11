---
title: ASPX ページの接続のタイムアウトの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ASPX pages, connection time-out
- connections, time-out
ms.assetid: 61d9c996-caf4-48bd-bda7-52f2797a941b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d28867e323a3fb7c3b50ab787b31b19c32c36e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281838"
---
# <a name="setting-the-connection-time-out-for-an-aspx-page"></a>ASPX ページの接続のタイムアウトの設定
同期メッセージに ASPX ページを使用するときに、予期されるメッセージを待機できるように、ASPX ページの接続のタイムアウトを増やす必要があります。  
  
 ASPX ページを指定することは、接続のタイムアウトを増やすと意図しない結果。 最初に、サービス拒否攻撃のリスクと、スレッド プールを使い果たすおそれが増加します。 次に、ASPX ページで同期接続が多すぎますがある場合、システムが動かなくなります。 そのため、接続のタイムアウトを増やす必要があります、中には、増やしすぎないしないように注意します。  
  
 RosettaNet 組織で許容される最小の接続のタイムアウトを設定します。 詳細については、タイミング パラメーター パートナー インターフェイス プロセス (PIP) の表 4-3 を参照してください。RosettaNet PIP 仕様のメッセージ交換コントロール。  
  
### <a name="to-set-the-connection-time-out-for-the-aspx-page"></a>ASPX ページの接続タイムアウトを設定するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  IIS マネージャーでは、ローカルのコンピューターのノードを展開し、順に展開**Websites**します。  
  
3.  **[既定の Web サイト]** を右クリックし、 **[プロパティ]** をクリックします。  
  
4.  既定の Web サイトのプロパティ ダイアログ ボックスで、 **Web サイト** タブで、**接続タイムアウト**ボックスで、適切な値を入力し、をクリックし、 **ok**。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)