---
title: "BizTalk Server2 とのシステム統合 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system integration
- tools, BizTalk Server
- BizTalk Server, tools
- BizTalk Server, about BizTalk Server
- BizTalk Server, business processes
- messages, BizTalk Server
- BizTalk Server, messages
- BizTalk Server, system integration
- business processes, BizTalk Server
ms.assetid: 5ba3dda1-efdb-4a2b-bb3a-825d76696f15
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8729c6a197ce9ff6fe63f5d20499705fba3b258d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="systems-integration-with-biztalk-server"></a>BizTalk Server とのシステム統合
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server は、eBusiness アプリケーション用に設計された統合サーバーです。 に基づいて構築されて、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]システム プラットフォームを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]® 2008、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 2008/2008 R2 SP1、および[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] SharePoint® Services、およびの利用、機能[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 このようなテクノロジを組み合わせることにより、幅広い機能を使用してソリューションの開発、実装、運用、および保守を行うことができます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]組み合わせて使用できる次の統合サービスを提供[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]です。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 統合サービスの詳細については、[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] のヘルプを参照してください。  
  
## <a name="message-integration"></a>メッセージの統合  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] はメッセージ交換を自動化し、部署、ビジネス パートナー、ベンダーなどのエンティティを統合します。 共通の通信プロトコルとして XML が使用されます。 XSD (XML Schema Definition) スキーマを使用してメッセージを記述および検証し、XSLT (XSL Transformations) を使用してメッセージ間のデータ変換を行います。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] の統合エンジンは、ロケーション間でメッセージをルーティングします。 ここでは、ドキュメントのパブリッシュとサブスクライブを別々の部署で行う、パブリッシャー/サブスクライバー モデルが採用されています。 サブスクライブする部署は、メッセージをパブリッシュした部署に通知することなくサブスクライブできます。 これによって 2 点間通信を柔軟なハブスポーク通信に置き換えることができるので、取引先組織を効率的に処理できます。  
  
## <a name="business-process-automation"></a>ビジネス プロセスの自動化  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] は、オーケストレーションと呼ばれるプロセス マップを使用して一連の関連するアクションを単一のプロセスにリンクすることによって、ビジネス プロセスを自動化して統合します。 オーケストレーションを作成することによって、メッセージの送受信、決定、ループ、およびその他の操作の手順をデータ交換と分析に基づいてリンクできます。 オーケストレーションを使用することで、イベントが発生した場合に自動的に実行されるビジネス プロセスを作成できます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] を使用すると、ビジネス ルールに基づいてプロセスを動的に変更できます。 これによって、連携されたプロセスで実行されるアクションをビジネスの考慮事項に基づいて柔軟に変更できます。 たとえば、注文の請求処理の承認プロセスを特定のしきい値によって制限できます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] を使用すると、ヒューマン ワークフロー サービスを使用して自動化されたオーケストレーションに人為的なアクションを組み込むことができます。 詳細については、[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] ヘルプの「ヒューマン ワークフロー サービス (HWS)」を参照してください。  
  
## <a name="integration-of-heterogeneous-systems"></a>異機種システムの統合  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] は、異なる通信プロトコルでデータを転送する異機種システム混在環境で IT システムを統合できます。 これは、アダプターを使用して、さまざまなプロトコルを使用しているシステムに接続することにより実現します。 サポートされているのは、File、FTP、HTTP、SMTP、SOAP、および SQL アダプターです。 BizTalk アダプター フレームワークを使用して、カスタム アダプターを作成できます。 詳細については、[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] ヘルプの「アダプター フレームワークを使用したアダプターの開発」を参照してください。  
  
## <a name="role-based-tools"></a>ロールベースのツール  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]開発および実行環境を作成、実装、運用、保守、およびシステムをカスタマイズする開発者、IT 担当者、およびビジネス担当者が共同作業します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用方法に応じてカスタマイズされたツールには、これらの各ロールを提供します。  
  
 詳細については、次を参照してください[ロールベースの製品 &#91;。RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/a-role-based-product2.md)、および[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]ヘルプします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server がビジネス ニーズを解決する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [BizTalk Accelerator for RosettaNet により BizTalk Server に追加される機能](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)