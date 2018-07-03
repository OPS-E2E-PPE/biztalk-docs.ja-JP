---
title: BizTalk accelerator for HL7 開始 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.gettingstarted
helpviewer_keywords:
- BizTalk Accelerator for HL7
- BizTalk Accelerator for HL7, getting started
- getting started
ms.assetid: e842d501-2037-4fd6-a518-d29b25877250
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14559d888bc020a5772fbbc6eddf3ba4fdb4beb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989603"
---
# <a name="get-started-with-the-biztalk-accelerator-for-hl7"></a>BizTalk accelerator for HL7 開始します。
Microsoft を使用して[!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)]、医療のコンピューター システム間でビジネス プロセスを開発することができます。 使用して[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]開発者、IT プロフェッショナル、およびインターフェイス アナリストは、医療アプリケーション間でのエンド ツー エンドの統合 BTAHL7 ベース ソリューションの開発に共通の環境で作業できます。  
  
 具体的で[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]ことができます。  
  
- **医療のアプリケーション統合を簡素化**します。 ビルド、管理、および追跡を使用して分散型ビジネス プロセス、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]開発環境。  
  
- **医療アプリケーション間での臨床データ交換を標準化**します。 アプリケーション間の既存のデータ転送の変換、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]標準。  
  
- **効率を高める**します。 最小限の介入を医療アプリケーション間のすべての通信プロセスを自動化します。  

役割に固有の情報を使用する方法について説明します[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]を病院および企業間取引の医療ソリューションを自動化する医療分野内でエンタープライズ アプリケーション統合 (EAI) を容易にする.  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] ソリューションの種類ごとに、チュートリアルの形式で 4 つの独立したシナリオを提供します。 これらのチュートリアルを開始する前の基本的な概念を理解する必要があります[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]、ツールやソリューションを構築するために必要なプロセスを[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]します。  

> [!TIP] 
> これらのレッスンを開始する前に[HL7 アクセラレータと BizTalk ツールの使用について説明します](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)します。  
  
 次の説明には、それぞれの基本的な知識[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]チュートリアル。  
  
## <a name="end-to-end-tutorial"></a>エンド ツー エンドのチュートリアル  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]エンド ツー エンドのチュートリアルによって、サブスクライバーとパブリッシャーのシナリオでビジネス プロセスを容易に詳細な手順を提供します。 このシナリオでは、たとえば、入学退院と転送システムの発行元が特定のサブスクライバーにメッセージを送信する状況。  
  
 メッセージをルーティング、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]インターフェイス エンジンは、さらに受け取ると、プロセス、検証、書式を再設定、およびをサブスクライバーにメッセージをルーティングします。 このシナリオではサブスクライバーには、病院の情報システムおよび薬剤システムです。  
  
 このシナリオでは、ファイルと最小限の下位レイヤー プロトコル (MLLP) の両方の種類のアダプターを使用します。 パブリッシャーは、サブスクライバーを意識する必要はありません、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]インターフェイス エンジンは、メッセージの処理後、パブリッシャーに適切な受信確認を送信します。  
  
## <a name="interrogative-tutorial"></a>Interrogative チュートリアル  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interrogative チュートリアルは詳細な手順を実装するため、組織内のサブシステム間のクエリ応答システム。 このシナリオは、入学で基幹業務 (LOB) アプリケーションで、放電し、転送システムでは、病院情報システムは、患者の結果を得るためにクエリを送信します。 病院の情報システムは、クエリを受信した後、クエリを発行したシステムに戻したり、要求されたデータを送信します。  
  
 このシナリオでは、受信確認を含むすべてのメッセージのトランスポート プロトコルとして MLLP を使用します。  
  
## <a name="message-enrichment-tutorial"></a>メッセージ強化のチュートリアル  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]強化のチュートリアルによって、特定のビジネス上の問題を解決するために詳細な手順を提供します。 メッセージ強化シナリオ。 メッセージ強化シナリオを追加、または強化する必要がある場合は HL7 に準拠していないことが完了していないメッセージです。 このような状況は、アプリケーションでは、患者登録アプリケーションなど、または XML データからのメッセージを作成するときに発生する可能性が[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]します。  
  
 メッセージをキャプチャするシナリオでは、メッセージの強化、 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]、患者レコード データベースからなど、不足しているあらゆるデータを提供します。 メッセージを変換し、研究室、保険、または MLLP アダプターを使用して、従来の基幹業務 (LOB) アプリケーションに送信します。  
  
## <a name="batching-tutorial"></a>バッチ処理のチュートリアル  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バッチ処理のチュートリアルによってバッチ処理されたメッセージを送受信するための詳細な手順を提供します。 バッチ処理と、1 つの複合メッセージとしてグループの個々 のメッセージ (または受信確認) を送受信する必要があります。  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 次のメッセージのバッチ処理状況をサポートしています。  
  
- **断片化した受信バッチ**します。 このシナリオで[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]HL7 メッセージのバッチを受信し、送信先システムに、個々 のメッセージをルーティングします。  
  
- **バッチ処理/バッチ アウト**します。[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バッチ内の個々 のメッセージを確認し、HL7 メッセージのバッチを受信ファイルと送信先システムにメッセージのバッチをルーティングします。  
  
- **バッチ (または、送信バッチ処理) を作成**です。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 個々 のメッセージを受信し、送信先システムにルーティングする前にバッチとしてします。  
  
## <a name="tutorial-links"></a>チュートリアルのリンク  
  
-   [エンド ツー エンドのチュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)  
  
-   [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)  
  
-   [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)  
  
-   [バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)
  
## <a name="see-also"></a>参照
  
[障碍がある方のためのユーザー補助機能](../../adapters-and-accelerators/accelerator-hl7/accessibility-for-people-with-disabilities5.md)