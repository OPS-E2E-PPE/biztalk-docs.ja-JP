---
title: '手順 6: BizTalk オーケストレーション サーバーの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51ca589433d945dfdc5acac0602151b9f7cf6374
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991723"
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a>手順 6: BizTalk オーケストレーション サーバーの構成
このセクションでは、BizTalk オーケストレーション サーバーの構成のガイドラインを提供します。  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a>BizTalk オーケストレーション サーバーを構成するには  
  
1. 追加/削除 から選択して、ネットワーク分散トランザクション コーディネーター (DTC) アクセスを有効にする[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバーのカテゴリの下にあるコンポーネント。 ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。 DTC の問題のトラブルシューティングについては、Microsoft ヘルプとサポート Web サイトでは、次のサポート技術情報の記事を参照してください。  
  
   - MS DTC ファイアウォールの問題のトラブルシューティングにあるどの[ http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870)します。  
  
   - 使用 DTCTester ツールには、ある[ http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871)します。  
  
   - DTC をファイアウォールの背後にある場合は、構成する Microsoft 分散トランザクション コーディネーター (DTC) をファイアウォール経由で動作にあるを参照してください。 [ http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872)します。  
  
2. 追加のソフトウェアの前提条件、BizTalk Server のインストールをインストールして、BizTalk Server を構成する」の説明に従って[オーケストレーション サーバーに BizTalk Server の構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)します。  
  
3. インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール」の説明に従って、 [BizTalk Accelerator for SWIFT のメッセージング サーバーに構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)します。  
  
   このセクションには、次のトピックが含まれています。  
  
-   [オーケストレーション サーバーに BizTalk Server をインストールして構成する](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [オーケストレーション サーバーに BizTalk Accelerator for SWIFT をインストールして構成する](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)