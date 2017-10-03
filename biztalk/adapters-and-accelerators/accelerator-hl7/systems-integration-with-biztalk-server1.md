---
title: "BizTalk Server1 とのシステム統合 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system integration
- BizTalk Server, tools
- business processes, automating
- BTAHL7, BizTalk Server
- BizTalk Server
- BizTalk Server, business process automation
- BizTalk Server, messages
- BizTalk Server, system integration
ms.assetid: 8f66a4fc-186c-415f-a7ed-31f620f0495f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13eba7a4a799803340d2757bd39c3e5e9844603e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="systems-integration-with-biztalk-server"></a>BizTalk Server とのシステム統合
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] は、eBusiness アプリケーション用に設計された統合サーバーです。 に基づいて構築されて、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]システム プラットフォームを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2008、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]、および[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]の機能を活用して、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[vs2012](../../includes/vs2012-md.md)]. このようなテクノロジを組み合わせることにより、幅広い機能を使用してソリューションの開発、実装、運用、および保守を行うことができます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]組み合わせて使用できる次の統合サービスを提供[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 統合サービスの詳細については、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] のヘルプを参照してください。  
  
## <a name="message-integration"></a>メッセージの統合  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ交換を自動化することによって、別のエンティティ (部門、ビジネス パートナー、ベンダー、およびなど) を統合します。 一般的な通信プロトコルとして、拡張マークアップ言語 (XML) を使用します。 XSD (XML Schema Definition) スキーマを使用してメッセージを記述および検証し、XSLT (XSL Transformations) を使用してメッセージ間のデータ変換を行います。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] の統合エンジンは、ロケーション間でメッセージをルーティングします。 ここでは、ドキュメントのパブリッシュとサブスクライブを別々の部署で行う、パブリッシャー/サブスクライバー モデルが採用されています。 サブスクライブする部署は、メッセージをパブリッシュした部署に通知することなくサブスクライブできます。 これによって 2 点間通信を柔軟なハブスポーク通信に置き換えることができるので、取引先組織を効率的に処理できます。  
  
## <a name="business-process-automation"></a>ビジネス プロセスの自動化  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]自動化して、単一のプロセスに関連するアクションのセットをリンクするオーケストレーションと呼ばれるプロセス マップを使用してビジネス プロセスを統合します。 オーケストレーションを作成することによって、メッセージの送受信、決定、ループ、およびその他の操作の手順をデータ交換と分析に基づいてリンクできます。 オーケストレーションでは、イベントが発生したときに自動的に実行されるビジネス プロセスを作成することができます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] を使用すると、ビジネス ルールに基づいてプロセスを動的に変更できます。 これによって、連携されたプロセスで実行されるアクションをビジネスの考慮事項に基づいて柔軟に変更できます。 たとえば、注文の請求処理の承認プロセスを特定のしきい値によって制限できます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]自動化されたオーケストレーションは、ヒューマン ワークフロー サービスに人為的なアクションを含めることもできます。  
  
## <a name="integration-of-heterogeneous-systems"></a>異機種システムの統合  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] は、異なる通信プロトコルでデータを転送する異機種システム混在環境で IT システムを統合できます。 これは、アダプターを使用して、さまざまなプロトコルを使用しているシステムに接続することにより実現します。 これは、ファイル、FTP、HTTP、SMTP、SOAP、および SQL アダプターの使用をサポートします。 BizTalk アダプター フレームワークを使用して、カスタム アダプターを作成できます。  
  
## <a name="role-based-tools"></a>ロール ベースのツール  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]開発および実行環境を作成、実装、運用、保守、およびシステムをカスタマイズする開発者、IT 担当者、およびビジネス担当者が共同作業します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]それらの使用に合わせて調整ツールを使用して、これらの各ロールを提供します。  
  
 詳細については、次を参照してください。[ロール ベースの製品](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md)、および[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプ。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server に追加する BizTalk Accelerator 用 HL7](../../adapters-and-accelerators/accelerator-hl7/what-biztalk-accelerator-for-hl7-adds-to-biztalk-server.md)