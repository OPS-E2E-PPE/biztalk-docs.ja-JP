---
title: RosettaNet Pip |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, clusters
- RosettaNet, PIPs
- PIPs, PIP specifications
- PIPs, segments
- PIPs, RosettaNet
- DTDs, DTD files
ms.assetid: 2f7e8db3-9ccb-403a-9fe7-58fbba3c4cb1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8891979352ce47e18c8cfda80162b3683002c6f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989251"
---
# <a name="rosettanet-pips"></a>RosettaNet Pip
RosettaNet 組織は PIP (Partner Interface Processes) の作成および保守を行って、すべての RosettaNet メッセージ交換のための共通のビジネス プロセス定義を提供します。  
  
 PIP 仕様ごとに、文書型定義 (DTD) ファイルとメッセージ ガイドライン ドキュメントがあります。 DTD ファイルは、Service Content のメッセージ構造を定義します。 HTML ファイル形式のメッセージ ガイドライン ドキュメントは、要素レベルでの制約を指定します。 この 2 つにより、ビジネス プロセスが詳細に定義されます。  
  
 PIP 仕様の詳細については、RosettaNet の Web サイトを参照してください。 [ http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)します。  
  
## <a name="pip-contents"></a>PIP の内容  
 PIP 仕様の内容は以下のとおりです。  
  
- 実装するパブリック プロセスのパターンについて説明する。  
  
- パブリック プロセスを構成する方法について説明する。  
  
- PIP 内で交換できる文書への参照を提供する。  
  
  PIP 仕様は、BOV (Business Operational View)、FSV (Functional Service View)、IFV (Implementation Framework View) の 3 つに大きく分かれます。 これらの各ビューは、要素レベルの制約を指定します。  
  
- BOV は、ビジネス データ エンティティの意味とビジネス処理フローを指定します。 開始状態と終了状態、およびパートナーのロールについて記述します。 ロール間での相互処理について説明し、セキュリティ、監査、およびプロセス コントロールの詳細を示します。 ビジネス ドキュメントとビジネス データ エンティティを指定します。  
  
- FSV は、ネットワーク コンポーネント サービス、エージェント、および操作を指定します。 PIP を実行するために必要なネットワーク コンポーネント設計を提供し、可能なネットワーク コンポーネント操作について説明します。  
  
- IFV は、ネットワーク プロトコルのメッセージ形式と PIP を実行するために必要な通信要件を指定します。  
  
## <a name="clusters-and-segments"></a>クラスターおよびセグメント  
 PIP は、高度のビジネス関数 (クラスター) とサブ関数 (セグメント) によって分類します。 メッセージはクラスターとセグメントによって、わかりやすいカテゴリに分類されます。 次の表に、これらのクラスターとセグメントの一覧です。  
  
|Clusters|セグメント|  
|--------------|--------------|  
|0: RosettaNet のサポート|0A : Administrative (管理)<br /><br /> 0C : Testing (テスト)|  
|1: パートナーの製品とサービス レビュー|1A : Partner Review (パートナーのレビュー)<br /><br /> 1B : Product & Service Review (製品とサービスのレビュー)|  
|2: 製品情報|2A : Preparation for Distribution (配信の準備)<br /><br /> 2B : Product Change Notification (製品変更通知)<br /><br /> 2C : Product Design Information (製品設計情報)<br /><br /> 2D : Collaborative Design & Engineering (共同の設計とエンジニアリング)|  
|3: 注文管理|3A : Quote & Order Entry (見積もりと注文の入力)<br /><br /> 3B : Transportation & Distribution (配送と配信)<br /><br /> 3C : Returns & Finance (返品と財務管理)<br /><br /> 3D : Product Configuration (製品の構成)|  
|4: 在庫管理|4A : Collaborative Forecasting (協働的需要予測)<br /><br /> 4B : Inventory Allocation (在庫の割り当て)<br /><br /> 4C : Inventory Reporting (在庫のレポート)<br /><br /> 4D : Inventory Replenishment (在庫の補充)<br /><br /> 4E : Sales Reporting (売上レポート)<br /><br /> 4F : Price Protection (価格の保護)|  
|5: マーケティング情報の管理|5A : Lead Opportunity Management (見込み顧客管理)<br /><br /> 5B : Marketing Campaign Management (マーケティング キャンペーン管理)|  
|6: サービスとサポート|6A : Provide and Administer Warranties, Service Packages, and Contract Services (保証、サービス パッケージ、および契約サービスの提供と管理)<br /><br /> 6B : Provide and Administer Asset Management (資産管理の提供と管理) (6A に統合）<br /><br /> 6C : Technical Support and Service Management (技術サポートとサービスの管理)|  
|7: 製造|7A : Design Transfer (デザインの転送)<br /><br /> 7B : Manage Manufacturing WO & WIP (製造する WO と WIP の管理)<br /><br /> 7C : Distribute Manufacturing Information (製造情報の配布)|  
  
 各セグメントには、特定のメッセージ PIP 番号が含まれています。 たとえば 3A4 PIP は、注文管理クラスター (クラスター 3)、および見積もりと注文エントリ セグメント (セグメント A のクラスター 3) の一部です。 このセグメントには、次に示す他の関連メッセージ PIP が含まれます。  
  
 クラスタ 3 : Order Management (注文の管理)  
  
-   セグメント A : Quote and Order Entry (見積もりと注文の入力)  
  
    -   PIP 3A1 : Request Quote (見積もりの要求)  
  
    -   PIP 3A2 : Request Price and Availability (価格とアベイラビリティの要求)  
  
    -   PIP 3A3 : Request Shopping Cart Transfer (ショッピング カーと転送の要求)  
  
    -   PIP 3A4 : Manage Purchase Order (発注の要求)  
  
    -   PIP 3A5 : Query Order Status (注文状態の照会)  
  
    -   PIP 3A6 : Distribute Order Status (注文状態の配信)  
  
    -   …  
  
## <a name="see-also"></a>参照  
 [RosettaNet および CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [RNIF 規格](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)