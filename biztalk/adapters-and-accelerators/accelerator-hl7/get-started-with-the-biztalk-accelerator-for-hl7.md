---
title: 使い始める BizTalk Accelerator 用 HL7 |Microsoft ドキュメント
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
ms.openlocfilehash: bebe61b152c7a74c2d45c0604e23b0a39bc6a4fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205186"
---
# <a name="get-started-with-the-biztalk-accelerator-for-hl7"></a>使い始める BizTalk Accelerator 用 HL7
使用して、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)]、医療コンピューター システム間のビジネス プロセスを開発することができます。 使用して[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]開発者、IT 担当者、およびインターフェイス アナリストが医療アプリケーション間でエンド ツー エンド統合 BTAHL7 ベースのソリューションを開発するための一般的な環境で作業できます。  
  
 具体的で[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]することができます。  
  
-   **医療アプリケーション統合を簡略化**です。 ビルド、管理、および使用する分散型のビジネス プロセスを追跡、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]開発環境です。  
  
-   **医療アプリケーション間で治療のデータ交換を標準化**です。 アプリケーション間の既存のデータ転送の変換、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]標準です。  
  
-   **効率を高める**です。 手動による介入を最小限に抑えると医療アプリケーション間でのすべての通信プロセスを自動化します。  

このセクションでは、役割に固有の情報を使用する方法についてを説明[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]を病院および企業間取引医療ソリューションを自動化する医療分野内でエンタープライズ アプリケーション統合 (EAI) を容易にする.  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]各種類のソリューションのチュートリアル形式の 4 つの異なるシナリオを提供します。 これらのチュートリアルを開始する前にの基本的な概念を理解する必要があります[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]、およびツールとプロセスを使用したソリューションの構築を開始する必要がある[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]です。  

> [!TIP] 
> これらのレッスンを開始する前に[HL7 アクセラレータと使用可能な BizTalk ツールについて](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)です。  
  
 次の説明には、それぞれの基本的な知識[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]チュートリアルです。  
  
## <a name="end-to-end-tutorial"></a>エンド ツー エンドのチュートリアル  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]エンド ツー エンドのチュートリアルを使うと、サブスクライバーとパブリッシャーのシナリオでビジネス プロセスを容易にする詳細な手順です。 このシナリオは、パブリッシャーなど、受付放電と転送システムが特定のサブスクライバーにメッセージを送信する状況です。  
  
 メッセージをルーティング、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]インターフェイス エンジンは、さらに受信すると、プロセスを検証して、再フォーマットし、サブスクライバーにメッセージをルーティングします。 このシナリオでは、サブスクライバーとは、病院情報と薬局システムです。  
  
 このシナリオでは、ファイルと最小限の下位層プロトコル (MLLP) の両方の種類のアダプターを使用します。 パブリッシャーは、サブスクライバーに注意する必要はありません、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]インターフェイス エンジンがメッセージの処理後のパブリッシャーに適切な受信確認を送信します。  
  
## <a name="interrogative-tutorial"></a>Interrogative チュートリアル  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interrogative チュートリアルでは、する詳細な手順と、組織内のサブ システム間でクエリ応答システムを実装するためです。 このシナリオは、受付の基幹業務 (LOB) アプリケーションで、放電して転送するシステムが、病院情報システム患者の結果を得るためにクエリを送信します。 病院情報システムは、クエリを受信した後、クエリを発行したシステムに、要求されたデータを送信します。  
  
 このシナリオでは、受信確認を含む、すべてのメッセージのトランスポート プロトコルとして MLLP を使用します。  
  
## <a name="message-enrichment-tutorial"></a>メッセージの強化のチュートリアル  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Enrichment チュートリアルを使うと、特定のビジネス問題を解決する詳細な手順: メッセージ強化シナリオです。 メッセージ強化シナリオは、する必要がある追加、または強化する場合、HL7 準拠ではありませんやが完了するメッセージです。 このような状況は、アプリケーションでは、患者の登録、アプリケーションなど、またはからの XML データを含むメッセージを作成するときに発生する可能性が[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]です。  
  
 メッセージをキャプチャするシナリオでは、メッセージの強化、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]患者のレコードをデータベースからなど、不足しているデータを提供します。 メッセージを変換し、実験、保険、または MLLP アダプターを使用して、従来の基幹業務 (LOB) アプリケーションに送信します。  
  
## <a name="batching-tutorial"></a>バッチ処理のチュートリアル  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バッチ処理のチュートリアルを使うと、バッチ処理されたメッセージを送受信する詳細な手順です。 バッチ処理と、1 つの複合メッセージとして、個々 のメッセージ (または受信確認) のグループの送受信が含まれます。  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]次のメッセージのバッチ処理状況をサポートしています。  
  
-   **断片化された受信バッチ**です。 このシナリオで[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]HL7 メッセージ バッチを受信し、送信先システムに個々 のメッセージをルーティングします。  
  
-   **バッチ/アウト バッチ**です。[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] HL7 メッセージ バッチを受け取り、バッチ内の個々 のメッセージを確認し、送信先システムに、メッセージ バッチをルーティングします。  
  
-   **バッチ (または、送信バッチ処理) を作成**です。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]個々 のメッセージを受信し、送信先システムにルーティングする前にそれらをバッチ処理します。  
  
## <a name="tutorial-links"></a>チュートリアルのリンク  
  
-   [エンド ツー エンドのチュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)  
  
-   [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)  
  
-   [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)  
  
-   [バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)
  
## <a name="see-also"></a>参照
  
[障碍を持つユーザー補助機能](../../adapters-and-accelerators/accelerator-hl7/accessibility-for-people-with-disabilities5.md)