---
title: WCF サービス モデルを使用して Siebel アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, developing applications by using
- WCF service model, performing operations
- proxy programming, performing operations
- WCF service model, advantages of using
ms.assetid: df5627b9-c80d-4a75-a20a-a0be119735a2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 492d3ca3dc132704913e54045f4c377a32903a67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984067"
---
# <a name="develop-siebel-applications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Siebel アプリケーションを開発します。
[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] プログラミング モデルという、WCF サービス モデルの一部に対処する別のプログラミング モデルの制限事項を提供します-WCF チャネル モデル。  
  
 最下位レベルで、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]をクライアントがクライアントとサービスのエンドポイント間で確立されたチャネル経由で SOAP メッセージを交換することで、サービスで操作を呼び出す、WCF チャネル モデルを表示します。 WCF チャネル モデルでは、データ型と、WCF チャネルのアーキテクチャを直接操作するためのメソッドを公開します。 WCF チャネル モデルを作成する SOAP メッセージの内容と、両方方法、アプリケーションを直接制御とを提供します。 および[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]これらを使用できます。 ただし、チャネル経由で送信する適切な形式で SOAP メッセージを作成して、返される応答メッセージの検証は、詳細かつ面倒な作業をすることができます。  
  
 WCF サービス モデルには、発信先サービスに対する操作を呼び出すか、クライアントからの受信操作にプロキシ クラスを使用してただし、必要があります。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムをするには、操作を呼び出すことができます、WCF サービスとして公開します。  
  
- ターゲット サービスで操作を呼び出すために使用するプロキシ クラスには、WCF クライアント クラスが呼び出されます。 このクラスは、厳密に型指定されたパラメーターを持つ .NET メソッドとして、サービスによって公開される操作をモデル化します。 WCF サービス モデルを使用すると、公開操作を呼び出すことができます、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF クライアントでの .NET メソッドとして。 WCF クライアントの詳細については、次を参照してください。 [WCF Client Overview](https://msdn.microsoft.com/library/ms735103.aspx)します。   
  
  WCF クライアント クラスを生成するツールを使用して、関連付けられているサービス メタデータからヘルパー コードを[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を公開します。 次のツールのいずれかを使用できます。  
  
- ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)、WCF に付属しています。  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]が付属していますが、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]  
  
  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と統合されて、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]強力な参照と検索機能を備えた、アダプターによって公開される操作では、デザイン エクスペリエンスと標準の Microsoft Windows のインターフェイスを表示します。 WCF クライアントを生成する方法の詳細については、次を参照してください[WCF クライアントまたは Siebel ソリューションの成果物の WCF サービス コントラクトの生成。](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
## <a name="why-choose-the-wcf-service-model-or-the-wcf-channel-model"></a>WCF サービス モデルまたは WCF チャネル モデルを選択する理由  
 WCF サービス モデルのプログラミングのソリューションの開発に最適な選択肢は、多くの場合、.NET プログラマになじみがチャネルを基になる SOAP メッセージ交換の複雑さを非表示にするモデルを表示するため、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 ただし、WCF チャネル モデルが適してをする可能性がありますのシナリオがあります。 たとえば、SOAP メッセージ内のオブジェクトの XML 表現と WCF サービス モデルでそれらを表すために使用する .NET 型の間の逆シリアル化とシリアル化は、メッセージ全体をメモリに読み取る必要があります。  
  
 WCF チャネル モデルでは、XML ノード レベルのすべての操作にストリーミングのサポートを提供します。 ノードのレベルがストリーミングで XML メッセージの各ノードのみが一度にメモリに保持されます。 特定の操作など、大きな結果セットを返すクエリを実行している場合 WCF チャネル モデルありますアプリケーションに適しています。 WCF チャネル モデルの使用に関する詳細については、次を参照してください。 [Siebel アプリケーションを開発、WCF チャネル モデルを使用して](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md)します。  
  
 このセクションのトピックでは、情報、手順、および作成しを使用してアプリケーションを開発する WCF サービス モデルを使用するのに役立つ例が含まれて、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Siebel アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md)  
  
-   [メタデータと Siebel と WCF サービス モデル](../../adapters-and-accelerators/adapter-siebel/metadata-and-the-wcf-service-model-with-siebel.md)  
  
-   [WCF クライアントまたは Siebel ソリューションの成果物の WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
-   [Siebel システム用の WCF クライアントを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)  
  
-   [WCF サービス モデルを使用して Siebel アダプターでのビジネス コンポーネントに対する操作を実行します。](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)  
  
-   [MVG フィールドを持つ WCF サービス モデルを使用して Siebel アダプターでのビジネス コンポーネントに対する操作を実行します。](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Siebel アダプターでのビジネス サービス メソッドの呼び出し](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)  
  
## <a name="see-also"></a>参照  
[Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)