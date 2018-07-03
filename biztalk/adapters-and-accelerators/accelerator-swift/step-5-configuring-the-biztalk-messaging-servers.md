---
title: '手順 5: BizTalk メッセージング サーバーの構成 |Microsoft Docs'
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
ms.openlocfilehash: 9baea2c567148ead98abf6b3aca3f5cad8258e60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980003"
---
# <a name="step-5-configuring-the-biztalk-messaging-servers"></a>手順 5: BizTalk メッセージング サーバーを構成します。
このセクションでは、BizTalk メッセージング サーバーの構成のガイドラインを示します。  
  
### <a name="to-configure-the-biztalk-messaging-servers"></a>BizTalk メッセージング サーバーを構成するには  
  
1. 追加/削除 から選択して、ネットワーク分散トランザクション コーディネーター (DTC) アクセスを有効にする[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバーのカテゴリの下にあるコンポーネント。 ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。 DTC の問題のトラブルシューティングについては、Microsoft ヘルプとサポート Web サイトでは、次のサポート技術情報の記事を参照してください。  
  
   - MS DTC ファイアウォールの問題のトラブルシューティングにあるどの[ http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870)します。  
  
   - 使用 DTCTester ツールには、ある[ http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871)します。  
  
   - DTC をファイアウォールの背後にある場合は、「を構成する Microsoft 分散トランザクション コーディネーター (DTC) をファイアウォール経由で動作」にあるを参照してください。 [ http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872)します。  
  
2. 構成し、BizTalk のネットワーク負荷分散の確認」の説明に従ってサーバーが表示される[手順 2: サーバー上の NLB の構成](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)。  
  
3. インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]」の説明に従って[BizTalk Accelerator for SWIFT のメッセージング サーバーに構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)します。  
  
   このセクションには、次のトピックが含まれています。  
  
-   [メッセージング サーバーに BizTalk Server をインストールして構成する](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-messaging-server.md)  
  
-   [メッセージング サーバーに BizTalk Accelerator for SWIFT をインストールして構成する](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)