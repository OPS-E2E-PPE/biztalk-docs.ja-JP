---
title: 'チュートリアル 1: エンタープライズ アプリケーション統合 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial
- getting started tutorials, integrating enterprise applications
- enterprise application integration tutorial, about the tutorial
ms.assetid: aca5fc97-0fd6-4964-9cf1-482aa4f444b8
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb6ddbd6c2a3e25619c684036eee3fb0fa46a18f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287514"
---
# <a name="tutorial-1-enterprise-application-integration"></a>チュートリアル 1: エンタープライズ アプリケーション統合
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アプリケーション統合とビジネス プロセス マネジメント (BPM) 用の開発環境と実行環境が提供されます。 このチュートリアルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用してエンタープライズ アプリケーション統合 (EAI) ソリューションをセットアップして展開する方法について、詳細に学習します。  
  
##  <a name="BKMK_Tut1_scenario"></a>ビジネス シナリオ  
 Contoso は、コンピューターのハードウェアやソフトウェアを販売するオンライン ストアです。  Contoso は最近、リソース管理用にエンタープライズ リソース プランニング (ERP) システムを購入しました。  このチュートリアルでは、既存の倉庫システムを ERP システムに統合し、倉庫の要求プロセスを自動化するために、BizTalk Server を使用してエンタープライズ アプリケーション統合 (EAI) ソリューションを開発します。  
  
 この統合ソリューションには課題がいくつかあります。  
  
-   **メッセージのトランスポート**です。  倉庫システムと ERP システムは、2 つの異なるプラットフォームに存在し、メッセージの送受信に異なるトランスポート プロトコルを使用する可能性があります。 このソリューションでは、送信側システムによってサポートされるプロトコルでメッセージを受信し、受信側システムによってサポートされるプロトコルでメッセージを転送できる必要があります。  BizTalk Server を使用して*アダプター*メッセージを転送します。  BizTalk Server と BizTalk Adapter Pack には多数のネイティブ アダプターが付属しています。  アダプターを追加するには、ベンダーから購入する方法と、BizTalk Server で提供されるアダプター フレームワークを使用して独自に開発する方法があります。 アダプターの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=191131](http://go.microsoft.com/fwlink/?LinkId=191131)です。  
  
-   **メッセージの変換**です。 メッセージには、XML (eXtended Markup Language)、EDI (Electronic Data Interchange)、区切り文字を使用したファイルなど、多くの種類があります。 BizTalk Server では主に XML を使用します。 ほとんどの場合、受信メッセージはまず XML に変換されます。  このプロセスが呼び出されると*解析*です。  送信側では、メッセージを XML から他の種類に変換できます。  このプロセスが呼び出されると*シリアル化*です。  
  
-   **ビジネス プロセス管理**です。 ほとんどの EAI シナリオは、メッセージをあるシステムから別のシステムに転送するだけではありません。  通常は、より多くのシステムと複雑なワークフローにかかわっています。  このシナリオでは、倉庫は在庫の補充を要求するメッセージを送信します。ソリューションでは、メッセージを受信し、要求の総計を確認します。  総計が一定量を超える場合、要求は自動的に拒否され、拒否メッセージが送信されます。それ以外の場合は要求が ERP システムに転送されます。  
  
     このビジネス プロセスを説明する図を次に示します。  
  
     ![チュートリアル 1 メッセージ フロー](../core/media/tut1-msg-flow.gif "tut1_msg_flow")  
  
 このチュートリアルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 開発ツールを使用して、ビジネス プロセスをデザインし、展開します。  
  
## <a name="preparation"></a>準備  
 BizTalk Server 統合ソリューションを作成する前に、次の基本情報を収集する必要があります。  
  
-   BizTalk Server ソリューションで統合する必要があるアプリケーション/システムの数。  このシナリオでは、ERP と倉庫の 2 つのシステムがあります。  
  
-   各アプリケーションでサポートされるトランスポート プロトコル。  ソリューションを簡易にするために、両方のアプリケーションでファイルが使用されると想定します。  倉庫システムは、要求をファイルとしてファイル フォルダー内に入れます。 BizTalk Server ソリューションはフォルダーからファイルを取得し、ファイルを処理して、ERP システムが監視する別のフォルダーに要求を入れます。  
  
-   アプリケーションが使用するメッセージの種類。  ソリューションを簡易にするために、両方のアプリケーションで XML が使用されると想定します。 BizTalk のスキーマは、BizTalk メッセージ内の XML データ構造を定義するドキュメントであり、その目的は、XML メッセージの処理および検証用のテンプレートを作成することです。 BizTalk Server には、BizTalk スキーマを作成できる BizTalk エディターが付属しています。  
  
-   ビジネス プロセス。  プロセスの説明については、前述しました。  
  
## <a name="biztalk-server-architecture"></a>BizTalk Server のアーキテクチャ  
 ソリューションが BizTalk Server でどのように実行されるかを理解しておくと役に立ちます。  次の図は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を介したデータの流れを示しています。  
  
 ![チュートリアル 1 のシナリオのデータ フロー](../core/media/tut1-dataflow.gif "Tut1_Dataflow")  
  
-   (倉庫システムは、要求をファイル フォルダーに入れます。)  
  
-   BizTalk Server の受信場所には、ファイル アダプターと XML 送信パイプラインが構成されます。  ファイル アダプターは、ファイル フォルダーを定期的にポーリングしてファイルがあるかどうかを確認します。 メッセージが受信されると、BizTalk Server メッセージング エンジンは、メッセージをパイプライン経由で送信します。  要求メッセージは XML 形式なので、この場合は XML 送信パイプラインが使用されます。  XML 送信パイプラインは、メッセージが整形式の XML ファイルであることを確認します。  その後、メッセージはメッセージ ボックス データベースに保存されます。  
  
-   オーケストレーション エンジンが、メッセージをオーケストレーションで処理する準備ができたと判断すると、オーケストレーションのインスタンスがインスタンス化されます。  メッセージの総計により、オーケストレーション エンジンは要求メッセージか要求拒否メッセージのどちらかをメッセージ ボックス データベースに保存します。  
  
-   さらに、メッセージ エンジンは、要求メッセージか要求拒否メッセージかで送信ポートを使い分けてメッセージを処理します。  まず、メッセージング エンジンは、メッセージを XML 送信パイプライン経由で送信し、次に、ファイル アダプターを使用して、送信ポートの構成に応じて異なるファイル フォルダーにメッセージを送信します。  
  
-   (倉庫システムと ERP システムの両方が、指定されたフォルダーを監視してメッセージを取得します。)  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md) 
  
-   [レッスン 1: 定義のスキーマとマップ](../core/lesson-1-define-schemas-and-a-map.md) 
  
-   [レッスン 2: ビジネス プロセスを定義します。](../core/lesson-2-define-the-business-process.md)  
  
-   [レッスン 3: ソリューションを配置します。](../core/lesson-3-deploy-the-solution.md)