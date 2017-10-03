---
title: "WCF サービス モデルを使用した Siebel アプリケーション開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, developing applications by using
- WCF service model, performing operations
- proxy programming, performing operations
- WCF service model, advantages of using
ms.assetid: df5627b9-c80d-4a75-a20a-a0be119735a2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c14560fb92eb2cca1e55d32e556dec23725a0de6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-siebel-applications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Siebel アプリケーションを開発します。
[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデルと呼ばれる、WCF サービスをモデルを部分的に対応するための別のプログラミング モデルの制限の一部は、-、WCF チャネル モデル。  
  
 最下位のレベル、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]をクライアントがクライアントとサービスのエンドポイント間で確立されたチャネル経由で SOAP メッセージを交換することで、サービスに対して操作を呼び出す、WCF チャネル モデルを表示します。 WCF チャネル モデルでは、データ型とすると、WCF チャネル アーキテクチャを直接操作できるようにするメソッドを公開します。 WCF チャネル モデルを使うと、直接的な制御を作成する SOAP メッセージの内容および両方方法、アプリケーションを介して、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]それらを使用します。 ただし、チャネル経由で送信する整形式の SOAP メッセージを作成して、返される応答メッセージの検証は、詳細で正確なタスクを指定できます。  
  
 WCF サービス モデルには、発信先サービスに対する操作を呼び出すか、クライアントからの受信操作に、プロキシ クラスを使用してにはが含まれます。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムをするには、操作を呼び出すことができますを WCF サービスとして公開します。  
  
-   操作の対象となるサービスの呼び出しに使用するプロキシ クラスには、WCF クライアント クラスが呼び出されます。 このクラスは、厳密に型指定されたパラメーターを使用して .NET メソッドとして、サービスによって公開される操作をモデル化します。 WCF サービス モデルを使用すると、によって公開される操作を呼び出すことができます、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF クライアント上の .NET メソッドとして。 WCF クライアントの詳細については、次を参照してください。 [WCF クライアントの概要](https://msdn.microsoft.com/library/ms735103.aspx)です。   
  
 WCF クライアント クラスを生成するツールを使用して、関連付けられているサービス メタデータからヘルパー コードを[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を公開します。 次のツールのいずれかの操作を行うこともできます。  
  
-   ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF に付属しています。  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]に付属する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と統合されて、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]強力な参照および検索機能を備えたアダプターによって公開される操作では、デザイン エクスペリエンスおよび Microsoft Windows の標準のインターフェイスを表します。 WCF クライアントを生成する方法の詳細については、次を参照してください[WCF クライアントまたは Siebel ソリューションの成果物の WCF サービス コントラクトを生成。](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
## <a name="why-choose-the-wcf-service-model-or-the-wcf-channel-model"></a>WCF サービス モデルまたは WCF チャネル モデルを選択する理由  
 WCF サービス モデルは、多くの場合のプログラミング ソリューションを開発する最善の選択、モデルが .NET プログラマになじみしてチャネル経由で SOAP メッセージ交換の基になる複雑さを非表示に表示するため、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 ただし、これには WCF チャネル モデルがより優れた選択肢をする可能性がありますシナリオがあります。 たとえば、シリアル化して、SOAP メッセージ内のオブジェクトの XML 表現とそれらを表す、WCF サービス モデルで使用される .NET 型をシリアル化解除は、メッセージ全体をメモリに読み取るが含まれます。  
  
 WCF チャネル モデルでは、すべての操作では、XML ノード レベルのストリーミングのサポートを提供します。 ノード レベルのストリーミング、XML メッセージの各ノードだけは、任意の時点でメモリに保持されます。 特定の操作のなど、大きな結果セットを返すクエリを実行している場合 WCF チャネル モデル場合があります、アプリケーションの方が適切です。 詳細については、WCF チャネル モデルを使用して、次を参照してください。 [WCF チャネル モデルを使用して開発 Siebel アプリケーション](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md)です。  
  
 このセクションのトピックでは、情報、プロシージャ、および例を作成してモデルを使用して、WCF サービスを使用してアプリケーションを開発する際に役立ちますが含まれて、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Siebel アダプターと WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md)  
  
-   [メタデータと Siebel で WCF サービスのモデル](../../adapters-and-accelerators/adapter-siebel/metadata-and-the-wcf-service-model-with-siebel.md)  
  
-   [WCF クライアントまたは Siebel ソリューションの成果物の WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
-   [Siebel システム用の WCF クライアントを構成します。](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)  
  
-   [WCF サービス モデルを使用して、Siebel アダプターとビジネス コンポーネントでの操作を実行します。](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)  
  
-   [WCF サービス モデルを使用して、Siebel アダプターと MVG フィールドのビジネス コンポーネントでの操作を実行します。](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して、Siebel アダプターとビジネス サービス メソッドを呼び出す](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)  
  
## <a name="see-also"></a>参照  
[Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)