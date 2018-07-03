---
title: SOAP 受信ハンドラを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], receive handlers
- SOAP adapters, receive handlers
- receive handlers, SOAP adapters
ms.assetid: e1174381-f36c-4131-83b7-26bfa879802e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15c4f9e63b1b41592cdda3dd984e85f20373fd2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968347"
---
# <a name="how-to-configure-a-soap-receive-handler"></a>SOAP 受信ハンドラを構成する方法
BizTalk Server 管理コンソールを使用して、SOAP 受信ハンドラの設定を構成できます。 BizTalk Server 管理コンソールを使用してアダプターを構成する場合、ハンドラー オーバーライド プロパティを BizTalk エクスプローラで設定する必要はありません。  
  
### <a name="to-change-global-variables-for-the-soap-receive-handler"></a>SOAP 受信ハンドラのグローバル変数を変更するには  
  
1. BizTalk Server 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。  
  
2. 展開したアダプターの一覧でクリックして**SOAP**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。  
  
3. **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられている場合、あるホストを選択し、クリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [SOAP アダプターの構成](../core/configuring-the-soap-adapter.md)   
 [Web サービスの利用](../core/consuming-web-services.md)