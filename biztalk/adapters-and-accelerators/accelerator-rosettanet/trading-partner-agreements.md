---
title: パートナー アグリーメントを取引先 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trading partners, agreements
- agreements, trading partners
ms.assetid: 846466d2-db39-42ba-8be1-ecca83a55a02
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9dd7bdeac01660cc95c0992ef01028c91cc75df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988443"
---
# <a name="trading-partner-agreements"></a>取引先アグリーメント
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]取引先アグリーメント (TPA) して、パートナーとメッセージ交換を処理します。 TPA は、2 つのパートナー間のメッセージ処理と検証の詳細を定義します。 TPA は、2 つのパートナーが PIP (Partner Interface Process) を実装する方法を定義します。PIP は、特定のメッセージの種類のすべての実装に対するメッセージ コンテンツを指定します。 また、パートナーがインターネット経由でメッセージを交換する方法の詳細も定義します。  
  
## <a name="trading-partner-agreement-contents"></a>取引先アグリーメントの内容  
 各取引先アグリーメントには、以下の情報が含まれます。  
  
- 取引先の ID  
  
- RNIF (RosettaNet Implementation Framework) のバージョンによって定義されるパブリック プロセス。各 TPA は単一のパブリック プロセスを参照して PIP アクションを開始し、PIP アクションに応答します。  
  
- プロセス構成プロファイル (PIP の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 実装)  
  
- アクション、シグナル、および同期 URL を含む ASPX 設定  
  
- エンコーディングと暗号化のプロトコル  
  
- カスタム プロパティ  
  
  取引先アグリーメントを作成するには、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールを使用してプロセス構成を作成する必要があります。 プロセス構成は、通常は RosettaNet PIP に基づいて設定を行いますが、カスタム スキーマに基づいて設定を行うこともできます。 コンソールを使用しても、ホーム組織とパートナーを作成する必要があります。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不明なパーティ間のメッセージ交換をサポートしません。 構成と組織を作成した後に、管理コンソールを使用して取引先アグリーメントを作成します。  
  
### <a name="process-configuration"></a>[プロセス構成設定]  
 この設定によって、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がメッセージの内容を処理する方法が決まります。 この設定は RosettaNet PIP を指定し、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が PIP を実装する方法を示します。 そのために、この設定は、タイムアウト、再試行値などの PIP が指定する動作設定のための値を提供します。 したがって、2 つの異なるパートナーのセット、または同じパートナーのセットは、同じ PIP を 2 つの異なる方法で実装できます。  
  
 この設定は、標準 (RosettaNet または CIDX) を指定し、ホーム組織と取引先のロールの一般的な特徴も指定します。 RosettaNet 以外のコンテンツのプロセス構成も作成できます。 そのためには、コンテンツのスキーマを作成し、スキーマに基づいて構成を作成する必要があります。 RosettaNet 以外のコンテンツの値を入力メッセージ標準、標準のバージョン、およびペイロード バインド ID の設定、**全般** タブで、**プロセス構成設定** ダイアログ ボックス。 RosettaNet 以外のコンテンツは、RNIF 2.0 のみを使用して転送できます。  
  
 これらのプロパティを設定する方法についての詳細については、[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)を参照してください。  
  
### <a name="home-organization"></a>[ホーム組織]  
 この設定は、メッセージを開始するホーム組織を定義します。 設定には、グローバル ビジネス識別子 (GBI) (ビジネスの一意の識別子である DUN 番号) と、一部のトランザクションに必要な連絡先情報が含まれます。 これらのプロパティを設定する方法についての詳細については、[を作成または編集、ホーム組織](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)を参照してください。  
  
### <a name="partner-organization"></a>取引先組織  
 これらの設定を受信してメッセージに応答するパートナーを定義します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ホーム組織との契約を持つ有効なパーティから各着信 RNIF メッセージが発生したことを検証します。 ない場合は、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]を認証し、メッセージを処理は失敗します。 これらのプロパティを設定する方法についての詳細については、[を作成または編集するパートナー](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)を参照してください。  
  
### <a name="agreements-trading-partner-agreement-variables"></a>[アグリーメント] \(取引先アグリーメント変数)  
 このアグリーメントは、取引先とのすべての取引関係を指定します。 アグリーメントは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールの定義に基づいてプロセス構成設定の表示コードを指定します。 RNIF バージョン、ポート URL、プロトコル設定 (エンコーディングと暗号化)、およびその他の変数も指定します。 これらのプロパティを設定する方法についての詳細については、[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)を参照してください。  
  
 管理コンソールの詳細については、[構成、証明書、データベース、およびセキュリティを管理](manage-configuration-certificates-databases-security.md)を参照してください。 開発者用リファレンスの Microsoft.Solutions.BTARN.ConfigurationManager 名前空間のクラスとインターフェイスを使用して、プログラムによってこの設定に読み取り専用でアクセスすることもできます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server に BizTalk Accelerator for RosettaNet の追加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [RNIF パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/rnif-pipelines.md)   
 [作成またはプロセス構成を編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [作成またはホーム組織を編集します。](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [作成または編集するパートナー](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)   
 [アグリーメントの作成と編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)