---
title: "チュートリアル 2: Siebel に移行する BizTalk プロジェクトの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a2a1828-8cc8-4b80-99bd-c083c04e5d04
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b8d138d348e750102d82a4aba2e39bc7d119c8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-2-migrating-biztalk-projects-in-siebel"></a>チュートリアル 2: Siebel の BizTalk プロジェクトを移行します。
Microsoft BizTalk Server に付属している Siebel アダプターの以前のバージョンが WCF ベース異なる[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]など、多くの点で。  
  
-   デザイン時に、BizTalk プロジェクトを作成する操作。  
  
-   メタデータの取得エクスペリエンス。  
  
-   スキーマ ファイル名と名前空間。  
  
-   データは、マッピングを入力します。  
  
-   アダプターを使用して実行できる操作です。  
  
-   BizTalk Server 管理コンソールで物理ポートの構成  
  
 これらの相違点が含まれるトピックで説明した[を移行する BizTalk プロジェクト作成を使用して、前のバージョンの Siebel アダプター](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)です。  
  
 ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースで動作させるため[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
 このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトに加える必要があります変更について説明します。  
  
> [!NOTE]
>  ここでは簡略化のため、このチュートリアルでは、Siebel アダプターの以前のバージョンを vPrev Siebel アダプターと呼びます。 同様に、vPrev Siebel アダプターを使用する BizTalk プロジェクトが参照されます vPrev BizTalk プロジェクトです。  
  
## <a name="sample-used-for-the-tutorial"></a>チュートリアルでは、使用されるサンプル  
 このチュートリアルは、アカウントの Siebel ビジネス コンポーネントで挿入操作を実行する BizTalk プロジェクトを vPrev 移行する方法を示すサンプル (Siebel_BussComp_Migration) に基づいています。 サンプルが付属して Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。[アダプター サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルには、アカウントのビジネス コンポーネントで挿入操作を実行する BizTalk プロジェクトが含まれます。  
  
-   VPrev Siebel アダプターを使用してアカウントのビジネス コンポーネントで挿入操作を実行する要求メッセージが必要です。 要求メッセージは、vPrev Siebel アダプターを使用して生成する挿入操作のスキーマに準拠している必要があります。  
  
-   内の手順を完了する必要があります[Siebel アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md)です。  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
-   **BizTalk オーケストレーション**です。 これは、ポートの送信、Siebel を使用して、Siebel システムに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、別のファイルの場所に保存する簡単なオーケストレーションです。  
  
-   **Siebel ビジネス コンポーネントで実行する操作のスキーマ**です。 このチュートリアルには、アカウントのビジネス コンポーネントで挿入操作を実行する BizTalk プロジェクトが含まれます。 アカウントのビジネス コンポーネントに対して生成されたスキーマは、AccountService_Account_x5d.xsd です。 このスキーマは、vPrev Siebel アダプターを使用して生成されます。  
  
    > [!NOTE]
    >  WCF ベースとは異なり[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、vPrev Siebel アダプターはビジネス コンポーネントで特定の操作を生成するメタデータをサポートしません。 既定では、アダプターは、ビジネス コンポーネントでサポートされるすべての操作のスキーマを生成します。 このような複数 vPrev Siebel アダプターと WCF ベースの違いの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[を移行する BizTalk プロジェクト作成を使用して、前のバージョンの Siebel アダプター](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)です。  
  
-   **要求メッセージ**です。 アカウントのビジネス コンポーネントで挿入操作を実行する要求メッセージ。 要求メッセージのスキーマは vPrev Siebel アダプター側に表示される、挿入操作のスキーマに準拠しています。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行チュートリアルの目的は、WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev Siebel アダプターによって生成されたスキーマに準拠した要求メッセージを送信するために[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 そのため、簡単に言えば、移行練習では、WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]のスキーマです。  
  
 ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。  
  
-   WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
-   WCF ベースを使用する挿入操作を実行するための要求メッセージに vPrev Siebel アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
-   WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]vPrev Siebel アダプターの応答メッセージにします。  
  
-   Wcf-custom Siebel の作成、BizTalk Server 管理コンソールのポートの送信受信します。  
  
-   要求と応答のマッピングを使用する WCF カスタム ポートを構成します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: vPrev Oracle データベースでの BizTalk プロジェクトを変更します。](../../adapters-and-accelerators/adapter-oracle-database/step-1-modify-the-vprev-biztalk-project-in-oracle-database.md)  
  
-   [手順 2: ORacle データベース アダプターを使用する BizTalk Server 管理コンソールでオーケストレーションを構成します。](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)  
  
-   [手順 3: Siebel アダプターを使用して移行されたアプリケーションをテストします。](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)  
  
## <a name="see-also"></a>参照  
 [Siebel アダプタ チュートリアル](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)