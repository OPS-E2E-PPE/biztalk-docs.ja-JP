---
title: HL7 のシステム統合 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f66a4fc-186c-415f-a7ed-31f620f0495f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c7189802ea981bd26b717f09bb3de0e445c9314
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005035"
---
# <a name="systems-integration-with-biztalk-server"></a>BizTalk Server とのシステム統合
Microsoft BizTalk Server は、eBusiness アプリケーション用に設計された統合サーバーです。 Windows Server、SQL Server および SharePoint 上に構築し、Visual Studio の機能を利用します。 このようなテクノロジを組み合わせることにより、幅広い機能を使用してソリューションの開発、実装、運用、および保守を行うことができます。  
  
 BizTalk Server の次の統合サービスを提供用 HL7 BizTalk Accelerator と組み合わせて使用することができます ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。  
  
## <a name="message-integration"></a>メッセージの統合  
 BizTalk Server では、メッセージ交換を自動化することによって別のエンティティ (部門、ビジネス パートナー、ベンダー、およびなど) を統合します。 一般的な通信プロトコルとして、拡張マークアップ言語 (XML) を使用します。 XSD (XML Schema Definition) スキーマを使用してメッセージを記述および検証し、XSLT (XSL Transformations) を使用してメッセージ間のデータ変換を行います。  
  
 BizTalk Server の統合エンジンは、別に、1 つの場所からメッセージをルーティングします。 ここでは、ドキュメントのパブリッシュとサブスクライブを別々の部署で行う、パブリッシャー/サブスクライバー モデルが採用されています。 サブスクライブする部署は、メッセージをパブリッシュした部署に通知することなくサブスクライブできます。 これによって 2 点間通信を柔軟なハブスポーク通信に置き換えることができるので、取引先組織を効率的に処理できます。  
  
## <a name="business-process-automation"></a>ビジネス プロセスの自動化  
 BizTalk Server では、自動化し、1 つのプロセスに関連するアクションのセットをリンクするオーケストレーションと呼ばれるプロセス マップを使用してビジネス プロセスを統合します。 オーケストレーションを作成することによって、メッセージの送受信、決定、ループ、およびその他の操作の手順をデータ交換と分析に基づいてリンクできます。 オーケストレーションでは、イベントが発生したときに自動的に実行されるビジネス プロセスを作成することができます。  
  
 BizTalk Server を使用して、ビジネス ルールに基づいてプロセスを動的に変更することができます。 これによって、連携されたプロセスで実行されるアクションをビジネスの考慮事項に基づいて柔軟に変更できます。 たとえば、注文の請求処理の承認プロセスを特定のしきい値によって制限できます。  
  
 BizTalk Server では、自動化されたオーケストレーションは、ヒューマン ワークフロー サービスに人為的なアクションを含めることもできます。  
  
## <a name="integration-of-heterogeneous-systems"></a>異機種システムの統合  
 BizTalk Server では、システムが異なる通信プロトコルでデータを転送する異機種混在環境で IT システムを統合できます。 これは、アダプターを使用して、さまざまなプロトコルを使用しているシステムに接続することにより実現します。 これは、ファイル、FTP、HTTP、SMTP、SOAP、および SQL アダプターの使用をサポートします。 BizTalk アダプター フレームワークを使用して、カスタム アダプターを作成できます。  
  
## <a name="role-based-tools"></a>ロール ベースのツール  
 BizTalk Server は、開発および実行環境を作成、実装、運用、保守、およびシステムをカスタマイズする開発者、IT 担当者、およびビジネス担当者が共同作業です。 BizTalk Server では、それらの使用に合わせて調整ツールを使用してこれらの各ロールを提供します。  
  
 詳細については、次を参照してください。[ロール ベースの製品](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md)です。
  
## <a name="see-also"></a>参照  
 [BizTalk Accelerator for HL7 により BizTalk Server に追加される機能](../../adapters-and-accelerators/accelerator-hl7/what-biztalk-accelerator-for-hl7-adds-to-biztalk-server.md)