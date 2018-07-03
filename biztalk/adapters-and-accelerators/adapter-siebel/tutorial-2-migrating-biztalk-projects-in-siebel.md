---
title: 'チュートリアル 2: Siebel のプロジェクトを移行する BizTalk |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a2a1828-8cc8-4b80-99bd-c083c04e5d04
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ada19454c3d2aef1c725987d8d37f7b98a2d1c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996435"
---
# <a name="tutorial-2-migrating-biztalk-projects-in-siebel"></a>チュートリアル 2: Siebel の BizTalk プロジェクトを移行します。
WCF ベースの Microsoft BizTalk Server に付属する Siebel アダプターの以前のバージョンとは異なる[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]など、多くの点で。  
  
- BizTalk プロジェクトの作成、デザイン時エクスペリエンス。  
  
- メタデータの取得エクスペリエンス。  
  
- スキーマ ファイル名と名前空間。  
  
- データ型のマッピング。  
  
- アダプターを使用して実行できる操作。  
  
- BizTalk Server 管理コンソールで物理ポートの構成  
  
  これらの相違点については、トピックで[を移行する BizTalk プロジェクト作成を使用して前のバージョンの Siebel アダプター](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)します。  
  
  ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
  このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。  
  
> [!NOTE]
>  説明を簡潔にするため、このチュートリアルでは、vPrev Siebel アダプターと Siebel アダプターの以前のバージョンに参照されます。 同様に、vPrev Siebel アダプターを使用する BizTalk プロジェクトは vPrev BizTalk プロジェクトとしてに参照されます。  
  
## <a name="sample-used-for-the-tutorial"></a>このチュートリアルで使用されるサンプル  
 このチュートリアルは、アカウントの Siebel ビジネス コンポーネントに対して、挿入操作を実行する vPrev BizTalk プロジェクトを移行する方法を示すサンプル (Siebel_BussComp_Migration) に基づいています。 Microsoft とサンプルが提供される[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。[アダプター サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルには、アカウントのビジネス コンポーネントに対して、挿入操作を実行する BizTalk プロジェクトが含まれます。  
  
-   VPrev Siebel アダプターを使用して、アカウントのビジネス コンポーネントに対して、挿入操作を実行する要求メッセージが必要です。 要求メッセージは、vPrev Siebel アダプターを使用して生成する挿入操作のスキーマに準拠している必要があります。  
  
-   」の手順を完了する必要があります[Siebel アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md)します。  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
- **BizTalk オーケストレーション**します。 これは、ポートの送信、Siebel を使用して Siebel システムに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、ファイルの別の場所に保存する簡単なオーケストレーションです。  
  
- **Siebel ビジネス コンポーネントに実行する操作のスキーマを**します。 このチュートリアルには、アカウントのビジネス コンポーネントに対して、挿入操作を実行する BizTalk プロジェクトが含まれます。 アカウントのビジネス コンポーネントに対して生成されたスキーマは、AccountService_Account_x5d.xsd です。 VPrev の Siebel アダプターを使用して、このスキーマが生成されます。  
  
  > [!NOTE]
  >  WCF ベースとは異なり[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、vPrev Siebel アダプターは特定のビジネス コンポーネント操作のメタデータの生成をサポートしていません。 既定では、アダプターは、ビジネス コンポーネントでサポートされているすべての操作のスキーマを生成します。 はこのような違いについて vPrev Siebel アダプターと WCF ベース[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[を移行する BizTalk プロジェクト作成を使用して前のバージョンの Siebel アダプター](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)します。  
  
- **要求メッセージ**します。 アカウントのビジネス コンポーネントに対して、挿入操作を実行する要求メッセージ。 要求メッセージのスキーマは vPrev Siebel アダプター、挿入操作のスキーマに準拠しています。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行のチュートリアルの目的は WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev Siebel アダプターによって生成されたスキーマに準拠している要求メッセージを送信できるように、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 そのため、簡単に言えばの移行の練習では WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]のスキーマ。  
  
 ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。  
  
- WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
- WCF ベースを使用して挿入操作を実行するための vPrev Siebel アダプターの要求メッセージを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
- WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]vPrev Siebel アダプターの応答メッセージにします。  
  
- Wcf-custom Siebel を作成、BizTalk Server 管理コンソールのポートの送信-受信します。  
  
- 要求と応答のマッピングを使用する WCF カスタム ポートを構成します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: vPrev BizTalk プロジェクトで Oracle データベースを変更します。](../../adapters-and-accelerators/adapter-oracle-database/step-1-modify-the-vprev-biztalk-project-in-oracle-database.md)  
  
-   [手順 2: ORacle データベース アダプターを使用する BizTalk Server 管理コンソールでオーケストレーションを構成します。](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)  
  
-   [手順 3: Siebel アダプターを使用して移行されたアプリケーションをテストします。](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)  
  
## <a name="see-also"></a>参照  
 [Siebel アダプターのチュートリアル](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)