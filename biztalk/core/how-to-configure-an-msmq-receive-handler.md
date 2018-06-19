---
title: MSMQ 受信ハンドラーを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, MSMQ adapters
- configuring [MSMQ adapters], receive handlers
- MSMQ adapters, receive handlers
ms.assetid: d6d82098-3a73-44e2-80d5-143f77e919cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f34e1b3f399c93bd92aa9c4e07f6e0082d25204
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247874"
---
# <a name="how-to-configure-an-msmq-receive-handler"></a>MSMQ 受信ハンドラーを構成する方法 [BTS06]
次の手順を実行して、MSMQ 受信ハンドラーが関連付けられているホストを変更します。  
  
> [!NOTE]
>  各ホストに関連付けられる受信ハンドラーは 1 つだけです。  
  
### <a name="to-change-the-host-with-which-the-msmq-receive-handler-is-associated"></a>MSMQ 受信ハンドラーを関連付けるホストを変更するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。  
  
2.  展開したアダプターの一覧でクリックして**MSMQ**、右側のペインで、構成する受信ハンドラを右クリックしをクリック**プロパティ**です。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられる、ホストを選択します。  
  
4.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)