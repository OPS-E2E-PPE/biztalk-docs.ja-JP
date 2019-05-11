---
title: WCF サービス モデルを使用して SAP アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, developing applications
ms.assetid: 5387d063-31d3-49b3-9771-354802542f8f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f765dde8a21882d291df98bc9eebd4e9151b03b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373504"
---
# <a name="develop-sap-applications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SAP アプリケーションを開発します。
最下位レベルで、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]をクライアントがクライアントとサービスのエンドポイント間で確立されたチャネル経由で SOAP メッセージを交換することで、サービスで操作を呼び出すプログラミング モデルを表示します。 WCF チャネル モデルと呼ばれる、このモデルでは、データ型および WCF チャネル アーキテクチャを直接操作するためのメソッドを公開します。 WCF チャネル モデルを作成する SOAP メッセージの内容と、両方方法、アプリケーションを直接制御とを提供しますおよび[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用。 ただし、チャネル経由で送信する適切な形式で SOAP メッセージを作成および検証します。返される応答メッセージには、詳細かつ面倒なタスクを指定できます。  
  
 このため、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] WCF サービス モデルと呼ばれる別のプログラミング モデルを提供します。 WCF サービス モデルには、発信先サービスに対する操作を呼び出すか、クライアントからの受信操作にプロキシ クラスの使用が含まれます。  
  
- ターゲット サービスで操作を呼び出すために使用するプロキシ クラスには、WCF クライアント クラスが呼び出されます。 このクラスは、厳密に型指定されたパラメーターを持つ .NET メソッドとして、サービスによって公開される操作をモデル化します。 WCF サービス モデルを使用すると、公開操作を呼び出すことができます、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF クライアントでの .NET メソッドとして。 WCF クライアントの詳細については、次を参照してください。 [WCF Client Overview](https://msdn.microsoft.com/library/ms735103.aspx)します。
  
- クライアントから、操作を受信するために使用するプロキシ クラスは、WCF サービス コントラクト クラスと呼ばれます。 このクラスは、厳密に型指定されたパラメーターを持つコールバック メソッドとして、コードによって公開される操作をモデル化します。 このクラスのインスタンスをホストすることができますし、 **System.ServiceModel.ServiceHost**コードで操作を呼び出すクライアントを有効にします。 ポーリング クエリの結果を受信する WCF サービス モデルおよび POLLINGSTMT 操作を対象とした WCF サービス コントラクト クラスを使用して、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
  WCF クライアント クラスまたは WCF サービス コントラクトを生成するツールを使用して、関連付けられているサービス メタデータからヘルパー コードを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を公開します。 次のツールのいずれかを使用できます。  
  
- ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)、WCF に付属しています。  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]が付属していますが、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]  
  
  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と統合されて、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]強力な参照と検索機能を備えた、アダプターによって公開される操作では、デザイン エクスペリエンスと標準の Microsoft Windows のインターフェイスを表示します。 WCF クライアントまたは WCF サービス コントラクト クラスを生成する方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。  
  
  WCF サービス モデルのプログラミングのソリューションの開発に最適な選択肢は、多くの場合、.NET プログラマになじみがあるし、チャネル経由で SOAP メッセージ交換の基になる複雑さが隠蔽されるモデルを表示するため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 ただし、WCF チャネル モデルが適しています。 をする可能性があります。 シナリオがあります。どのストリーミングのシナリオで特にことが重要です。 これは、シリアル化するためと、SOAP メッセージ内のオブジェクトの XML 表現とサービス モデルでそれらを表すために使用する .NET 型の間の逆シリアル化には、メッセージ全体をメモリに読み取る必要があります。 WCF チャネル モデルの使用に関する詳細については、次を参照してください。 [WCF チャネル モデルを使用して開発の SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)します。
  
  このセクションのトピックでは、情報、手順、および作成しを使用してアプリケーションを開発する WCF サービス モデルを使用するのに役立つ例が含まれて、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)  
  
-   [メタデータと SAP を含む WCF サービス モデル](../../adapters-and-accelerators/adapter-sap/metadata-and-the-wcf-service-model-with-sap.md)  
  
-   [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)  
  
-   [SAP システムのクライアントのバインディングを構成します。](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)  
  
-   [WCF サービス モデルを使用して SAP で Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して、SAP で受信 RFC 呼び出しを受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して、Trfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して、SAP で受信 tRFC 呼び出しを受け取る](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して SAP の Bapi を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Idoc を SAP に送信します。](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)