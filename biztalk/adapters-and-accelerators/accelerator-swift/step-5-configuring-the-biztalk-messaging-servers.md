---
title: '手順 5: メッセージング サーバー BizTalk の構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, BizTalk Messaging servers
- BizTalk Messaging servers, configuring
ms.assetid: 598d336d-b006-4d02-9249-e9d6d9b6b7b5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e1aea1187417b77071f0821547869a5b84549c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214010"
---
# <a name="step-5-configuring-the-biztalk-messaging-servers"></a>手順 5: 構成の BizTalk メッセージング サーバー
このセクションでは、BizTalk メッセージングのサーバーの構成のガイドラインを示します。  
  
### <a name="to-configure-the-biztalk-messaging-servers"></a>BizTalk メッセージング サーバーを構成するには  
  
1.  追加/削除 から選択して、ネットワーク分散トランザクション コーディネーター (DTC) アクセスを有効にする[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバー カテゴリの下にあるコンポーネント。 ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。 次のサポート技術情報記事を参照してください、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] DTC の問題のトラブルシューティングについては、ヘルプとサポート Web サイト。  
  
    -   MS DTC ファイアウォールの問題のトラブルシューティングにあるどの[http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870)です。  
  
    -   DTCTester ツールの使用にあるどの[http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871)です。  
  
    -   DTC が、ファイアウォールの内側にある場合を参照してください"構成[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ファイアウォール経由で動作する分散トランザクション コーディネーター (DTC)"に配置されている[http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872)です。  
  
2.  構成し、BizTalk のネットワーク負荷分散の確認」の説明に従って、サーバーを受信[手順 2: サーバー上の NLB の構成](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)です。  
  
3.  インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]」の説明に従って[のインストールと BizTalk Accelerator for SWIFT メッセージング サーバー上を構成する](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)です。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [インストールして、メッセージング サーバー上の BizTalk Server の構成](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-messaging-server.md)  
  
-   [インストールと構成 BizTalk Accelerator for SWIFT のメッセージング サーバー](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)