---
title: MSMQ 受信ハンドラーを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 61741921363caa96acc2cb1a1e787ad1fbd41120
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386422"
---
# <a name="how-to-configure-an-msmq-receive-handler"></a>MSMQ 受信ハンドラーを構成する方法
次の手順に従って、MSMQ 受信ハンドラーを使用するホストを変更するのには、関連付けられています。  
  
> [!NOTE]
>  各ホストに関連付けられる受信ハンドラーは 1 つだけです。  
  
### <a name="to-change-the-host-with-which-the-msmq-receive-handler-is-associated"></a>MSMQ 受信ハンドラーを使用するホストを変更するのには、関連付けられています。  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。  
  
2.  展開したアダプターの一覧でクリックして**MSMQ**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。  
  
4.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)