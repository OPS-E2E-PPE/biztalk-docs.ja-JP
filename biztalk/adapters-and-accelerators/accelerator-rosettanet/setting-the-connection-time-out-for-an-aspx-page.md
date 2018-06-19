---
title: ASPX ページの接続のタイムアウトの設定 |Microsoft ドキュメント
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
ms.openlocfilehash: 83e083b9f2f0262095e58b4ed9842627888773dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207194"
---
# <a name="setting-the-connection-time-out-for-an-aspx-page"></a>ASPX ページの接続のタイムアウトの設定
同期メッセージに ASPX ページを使用する場合は、着信メッセージを待機できるように、ASPX ページの接続タイムアウトを増やす必要があります。  
  
 ASPX ページの接続タイムアウトを増やすと、予期しない結果が生じる場合があります。 第一に、サービス拒否攻撃のリスクが増し、スレッド プールを使い果たすおそれがあります。 第二に、ASPX ページに同期接続が多すぎると、システムが動かなくなる可能性があります。 したがって、接続タイムアウトを増やす必要がありますが、増やしすぎないように注意してください。  
  
 接続タイムアウトは RosettaNet 組織が許容する最小限に設定してください。 Partner Interface Process (PIP) のタイミング パラメータの詳細については、RosettaNet PIP 仕様の「表 4-3: メッセージ交換コントロール」を参照してください。  
  
### <a name="to-set-the-connection-time-out-for-the-aspx-page"></a>ASPX ページの接続タイムアウトを設定するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  IIS マネージャーでは、ローカル コンピューターのノードを展開し、順に展開**Websites**です。  
  
3.  **[既定の Web サイト]** を右クリックし、 **[プロパティ]** をクリックします。  
  
4.  既定の Web サイトのプロパティ ダイアログ ボックスで、 **Web サイト** タブの 、**接続タイムアウト**ボックスで、適切な値を入力し、をクリックして**ok**です。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)