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
ms.openlocfilehash: 20c29c3f295d4401b30bfeecc32d9df3aa532e16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282048"
---
# <a name="rosettanet-pips"></a>RosettaNet Pip
RosettaNet 組織では、作成し、Partner Interface Process (Pip) のすべての RosettaNet メッセージ交換の共通のビジネス プロセス定義を提供するを保持します。  
  
 各 PIP 仕様では、ドキュメント型定義 (DTD) ファイルとメッセージ ガイドライン ドキュメントを提供します。 DTD ファイルは、service content のメッセージの構造を定義します。 人間が判読できる HTML ファイルには、メッセージ ガイドライン ドキュメントには、要素レベルの制約を指定します。 同時に、ビジネス プロセスの完全な定義を提供します。  
  
 PIP 仕様の詳細については、RosettaNet の Web サイトを参照してください。 [ http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)します。  
  
## <a name="pip-contents"></a>PIP の内容  
 PIP 仕様は、次を行います。  
  
- 実装するパブリック プロセスのパターンについて説明します  
  
- パブリック プロセスを構成する方法について説明します  
  
- PIP 内で交換するドキュメントへの参照を提供します。  
  
  PIP 仕様には、次の 3 つの主要な部分が含まれています: Business Operational View (BOV)、機能サービス ビュー (FSV)、および実装 Framework ビュー (IFV)。 これらの各ビューには、要素レベルの制約を指定します。  
  
- BOV には、ビジネス データ エンティティのセマンティクスとビジネス プロセス フローを指定します。 これは、開始時刻、終了状態、およびパートナーの役割について説明します。 これには、ロール、および詳細情報のセキュリティ、監査、およびプロセス コントロール間の相互作用について説明します。 これは、ビジネス ドキュメントとビジネス データ エンティティを指定します。  
  
- FSV には、ネットワーク コンポーネント サービス、エージェント、および相互作用を指定します。 Pip を実行するために必要なネットワーク コンポーネントのデザインを提供し、可能なネットワーク コンポーネントの相互作用について説明します。  
  
- IFV は、ネットワーク プロトコルのメッセージ形式と PIP を実行するために必要な通信要件を指定します。  
  
## <a name="clusters-and-segments"></a>クラスターとセグメント  
 (クラスター) の高度なビジネス機能とサブ関数 (セグメント) では、Pip を分類します。 クラスターとセグメントは、ビジネス メッセージを認識可能なカテゴリに分類します。 次の表は、これらのクラスターとセグメントを示します。  
  
|クラスター|セグメント|  
|--------------|--------------|  
|0:RosettaNet のサポート|0A:管理<br /><br /> 0 の C:Testing (テスト)|  
|1:パートナー製品とサービス レビュー|1 A:パートナーのレビュー<br /><br /> 1 B:製品とサービス レビュー|  
|2:製品情報|2 A:配布準備<br /><br /> 2 B:製品変更通知<br /><br /> 2 C:製品設計情報<br /><br /> 2D:Collaborative Design & Engineering 部門|  
|3:注文管理|3 A:見積もりと注文エントリ<br /><br /> 3 B:輸送と配布<br /><br /> 3 C:Finance (&) を返します。<br /><br /> 3D:製品の構成|  
|4:Inventory Management|4A:コラボレーションの予測<br /><br /> 4 B:在庫の割り当て<br /><br /> 4 C:インベントリ レポート<br /><br /> 4 D:在庫の補充<br /><br /> 4E:Sales のレポート<br /><br /> 4F:価格保証|  
|5:Marketing Information Management|5A:潜在顧客の営業案件管理<br /><br /> 5 B:マーケティング キャンペーン管理|  
|6:サービスとサポート|6A:提供し、管理の保証、サービス パッケージ、およびサービスのコントラクト<br /><br /> 6B:提供し、管理 (6 a に統合) 資産の管理<br /><br /> 6C:テクニカル サポートとサービスの管理|  
|7:Manufacturing|7A:デザインの転送<br /><br /> 7 B:製造 WO と WIP を管理します。<br /><br /> 7 C:製造情報を配布します。|  
  
 各セグメントには、特定のメッセージ Pip の数が含まれています。 たとえば、3A4 PIP は、注文管理クラスター (クラスター 3) と見積もりと注文エントリ セグメント (セグメント A のクラスター 3) の一部です。 このセグメントには、その他の関連メッセージ Pip には、次のようが含まれます。  
  
 クラスター 3:注文管理  
  
-   セグメント a:見積もりと注文エントリ  
  
    -   PIP 3A1:見積もりを要求します。  
  
    -   PIP 3 A 2:Request Price and Availability  
  
    -   PIP 3A3:ショッピング カート転送を要求します。  
  
    -   PIP 3A4:注文書を管理します。  
  
    -   PIP 3A5:クエリの注文の状態  
  
    -   PIP 3A6:注文の状態を配布します。  
  
    -   …  
  
## <a name="see-also"></a>参照  
 [RosettaNet および CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [RNIF 規格](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)