---
title: BizTalk Server とシステムの統合 |Microsoft Docs
description: BizTalk Server には、XML を使用してメッセージの統合、マップと、オーケストレーションを使用してビジネス プロセスを自動化および FTP、HTTP、SMTP、SOAP、および SQL などのさまざまなプロトコルを使用するシステムと連携する機能が含まれています。
ms.custom: ''
ms.date: 06/08/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ba3dda1-efdb-4a2b-bb3a-825d76696f15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b29ccb1c4e249200bc409b36d1ee383b664a68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314625"
---
# <a name="systems-integration-with-biztalk-server"></a>BizTalk Server とのシステム統合
BizTalk Server が使用する統合サーバー、[パブリッシュ/サブスクライブ アーキテクチャ](../../core/publish-and-subscribe-architecture.md)します。 EBusiness アプリケーション用に設計されていますを[アダプターを使用して](../../core/using-adapters.md)メッセージを送受信するには、次のように実装します[オーケストレーションを通じて、ビジネス プロセス](../../core/defining-business-processes.md)、含める[管理および追跡。](../../core/management-and-tracking-architecture.md)の 3 つのパーツ。 BizTalk Server も含まれています[取引先の管理](../../core/trading-partner-management-using-biztalk-server.md)企業間メッセージングの[高可用性](../../core/planning-for-high-availability3.md)する開発プラットフォームのアップタイムを最大化する[独自に作成。コンポーネント](../../core/developing-custom-components.md)、管理コンソールを[、アーティファクトの管理](../../core/operational-and-administrative-tasks-in-your-biztalk-environment.md)、およびビジネス アクティビティの監視を管理する[集計、警告、およびプロファイル](../../core/using-business-activity-monitoring.md)します。 このようなテクノロジを組み合わせることにより、幅広い機能を使用してソリューションの開発、実装、運用、および保守を行うことができます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Microsoft と組み合わせて使用できる次の統合サービスを提供します。[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。 詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]integration services を参照してください[BizTalk Accelerator for RosettaNet](microsoft-biztalk-accelerator-for-rosettanet-documentation.md)します。
  
## <a name="message-integration"></a>メッセージの統合  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] はメッセージ交換を自動化し、部署、ビジネス パートナー、ベンダーなどのエンティティを統合します。 共通の通信プロトコルとして XML が使用されます。 XSD (XML Schema Definition) スキーマを使用してメッセージを記述および検証し、XSLT (XSL Transformations) を使用してメッセージ間のデータ変換を行います。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] の統合エンジンは、ロケーション間でメッセージをルーティングします。 ここでは、ドキュメントのパブリッシュとサブスクライブを別々の部署で行う、パブリッシャー/サブスクライバー モデルが採用されています。 サブスクライブする部署は、メッセージをパブリッシュした部署に通知することなくサブスクライブできます。 これによって 2 点間通信を柔軟なハブスポーク通信に置き換えることができるので、取引先組織を効率的に処理できます。  
  
## <a name="business-process-automation"></a>ビジネス プロセスの自動化  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] は、オーケストレーションと呼ばれるプロセス マップを使用して一連の関連するアクションを単一のプロセスにリンクすることによって、ビジネス プロセスを自動化して統合します。 オーケストレーションを作成することによって、メッセージの送受信、決定、ループ、およびその他の操作の手順をデータ交換と分析に基づいてリンクできます。 オーケストレーションを使用することで、イベントが発生した場合に自動的に実行されるビジネス プロセスを作成できます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] を使用すると、ビジネス ルールに基づいてプロセスを動的に変更できます。 これによって、連携されたプロセスで実行されるアクションをビジネスの考慮事項に基づいて柔軟に変更できます。 たとえば、注文の請求処理の承認プロセスを特定のしきい値によって制限できます。  
  
  
## <a name="integration-of-heterogeneous-systems"></a>異機種システムの統合  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] は、異なる通信プロトコルでデータを転送する異機種システム混在環境で IT システムを統合できます。 これは、アダプターを使用して、さまざまなプロトコルを使用しているシステムに接続することにより実現します。 サポートされているのは、File、FTP、HTTP、SMTP、SOAP、および SQL アダプターです。 BizTalk アダプター フレームワークを使用して、カスタム アダプターを作成できます。 詳細については、次を参照してください。[カスタム アダプターを作成する](../../core/developing-custom-adapters.md)します。
  
## <a name="role-based-tools"></a>ロールベースのツール  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 開発と実行環境を作成、実装、運用、保守、およびシステムをカスタマイズして、開発者、IT プロフェッショナル、ビジネスの専門家が共同作業します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] それらを使用するようにカスタマイズ ツールを使用して、これらの各ロールを提供します。  
  
 詳細については、次を参照してください。[ロールベース製品](../../adapters-and-accelerators/accelerator-rosettanet/a-role-based-product2.md)、および[について、RosettaNet アクセラレータ](../../adapters-and-accelerators/accelerator-rosettanet/learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md)します。
  
## <a name="see-also"></a>参照  
 [BizTalk Server がビジネス ニーズを解決する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [BizTalk Accelerator for RosettaNet により BizTalk Server に追加される機能](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)
