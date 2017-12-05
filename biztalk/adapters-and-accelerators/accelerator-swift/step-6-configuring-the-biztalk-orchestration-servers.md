---
title: "手順 6: オーケストレーションの BizTalk Server の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e495be91cc80e072f58a1e8149feb64773f1e51
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a>手順 6: オーケストレーションの BizTalk Server を構成します。
このセクションでは、BizTalk オーケストレーション サーバーの構成のガイドラインを示します。  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a>BizTalk オーケストレーション サーバーを構成するには  
  
1.  追加/削除 から選択して、ネットワーク分散トランザクション コーディネーター (DTC) アクセスを有効にする[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバー カテゴリの下にあるコンポーネント。 ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。 次のサポート技術情報記事を参照してください、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] DTC の問題のトラブルシューティングについては、ヘルプとサポート Web サイト。  
  
    -   MS DTC ファイアウォールの問題のトラブルシューティングにあるどの[http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870)です。  
  
    -   DTCTester ツールの使用にあるどの[http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871)です。  
  
    -   DTC が、ファイアウォールの内側にある場合は、構成を参照してください。[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]分散トランザクション コーディネーター (DTC) に「ファイアウォール経由の作業がある[http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872)です。  
  
2.  BizTalk Server の追加のソフトウェアの前提条件のインストール、インストールして」の説明に従って、BizTalk Server を構成する[オーケストレーション サーバー上の BizTalk Server の構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)です。  
  
3.  インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール」の説明に従って、[のインストールと BizTalk Accelerator for SWIFT メッセージング サーバー上を構成する](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)です。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [オーケストレーション サーバーに BizTalk Server をインストールして構成する](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [オーケストレーション サーバーに BizTalk Accelerator for SWIFT をインストールして構成する](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)