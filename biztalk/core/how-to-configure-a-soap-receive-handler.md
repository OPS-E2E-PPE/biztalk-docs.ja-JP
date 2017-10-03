---
title: "SOAP 受信ハンドラを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], receive handlers
- SOAP adapters, receive handlers
- receive handlers, SOAP adapters
ms.assetid: e1174381-f36c-4131-83b7-26bfa879802e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4054635a8ffa4e019f7db9513e5e20e997f7e291
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-soap-receive-handler"></a>SOAP 受信ハンドラを構成する方法
BizTalk Server 管理コンソールを使用して、SOAP 受信ハンドラの設定を構成できます。 BizTalk Server 管理コンソールを使用してアダプタを構成する場合、ハンドラ上書きのプロパティを BizTalk エクスプローラで設定する必要はありません。  
  
### <a name="to-change-global-variables-for-the-soap-receive-handler"></a>SOAP 受信ハンドラのグローバル変数を変更するには  
  
1.  BizTalk Server 管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。  
  
2.  展開したアダプターの一覧でクリックして**SOAP**、右側のペインで、構成する受信ハンドラを右クリックしをクリック**プロパティ**です。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられているホストを選択し、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [SOAP アダプターの構成](../core/configuring-the-soap-adapter.md)   
 [Web サービスの使用](../core/consuming-web-services.md)