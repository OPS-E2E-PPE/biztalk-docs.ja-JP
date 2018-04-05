---
title: WCF サービス モデルを使用して SAP アプリケーションを開発 |Microsoft ドキュメント
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
ms.openlocfilehash: 4933610f8416b2c7fb81861562480e355dd8d373
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sap-applications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SAP アプリケーションを開発します。
最下位のレベル、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]をクライアントがクライアントとサービスのエンドポイント間で確立されたチャネル経由で SOAP メッセージを交換することで、サービスに対して操作を呼び出すプログラミング モデルを表示します。 WCF チャネル モデルと呼ばれる、このモデルでは、データ型とすると、WCF チャネル アーキテクチャを直接操作できるようにするメソッドを公開します。 WCF チャネル モデルを使うと、直接的な制御を作成する SOAP メッセージの内容および両方方法、アプリケーションを介して、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]処理ですただし、チャネル経由で送信する整形式の SOAP メッセージを作成し、検証する、。返される応答メッセージには、詳細で正確なタスクを指定できます。  
  
 このため、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] WCF サービス モデルと呼ばれる別のプログラミング モデルを提供します。 WCF サービス モデルには、プロキシ クラスから発信先サービスに対する操作を呼び出すか、クライアントからの受信操作の使用が含まれます。  
  
-   操作の対象となるサービスの呼び出しに使用するプロキシ クラスには、WCF クライアント クラスが呼び出されます。 このクラスは、厳密に型指定されたパラメーターを使用して .NET メソッドとして、サービスによって公開される操作をモデル化します。 WCF サービス モデルを使用すると、によって公開される操作を呼び出すことができます、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF クライアント上の .NET メソッドとして。 WCF クライアントの詳細については、次を参照してください。 [WCF クライアントの概要](https://msdn.microsoft.com/library/ms735103.aspx)です。
  
-   クライアントから、操作を受信するために使用するプロキシ クラスは、WCF サービス コントラクト クラスと呼ばれます。 このクラスは、厳密に型指定されたパラメーターを使用してコールバック メソッドとして、コードによって公開される操作をモデル化します。 このクラスのインスタンスをホストすることができますし、 **System.ServiceModel.ServiceHost**コードで操作を呼び出すクライアントを有効にします。 WCF サービス モデルと POLLINGSTMT 操作を対象とした WCF サービスのコントラクト クラスを使用してからのポーリング クエリの結果を受け取ることができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
 WCF クライアント クラスまたは WCF サービス コントラクトを生成するツールを使用して、関連付けられているサービス メタデータからヘルパー コードを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を公開します。 次のツールのいずれかの操作を行うこともできます。  
  
-   ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF に付属しています。  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]に付属する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と統合されて、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]強力な参照および検索機能を備えたアダプターによって公開される操作では、デザイン エクスペリエンスおよび Microsoft Windows の標準のインターフェイスを表します。 WCF クライアントまたは WCF サービス コントラクト クラスを生成する方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
 WCF サービス モデルは、多くの場合のプログラミング ソリューションを開発する最適な選択肢は .NET プログラマになじみの非表示にする SOAP メッセージ交換の基になる複雑なチャネル経由でモデルを表示、ため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 ただし、シナリオを WCF チャネル モデルの方が適して; 可能性があります、どのストリーミングで特にのシナリオが重要です。 これは、シリアル化するためと、メッセージ全体をメモリに読み取るには、SOAP メッセージ内のオブジェクトの XML 表現とそれらを表すサービス モデルで使用される .NET 型をシリアル化解除します。 詳細については、WCF チャネル モデルを使用して、次を参照してください。 [WCF チャネル モデルを使用して開発 SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)です。
  
 このセクションのトピックでは、情報、プロシージャ、および例を作成してモデルを使用して、WCF サービスを使用してアプリケーションを開発する際に役立ちますが含まれて、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)  
  
-   [メタデータと SAP と WCF サービスのモデル](../../adapters-and-accelerators/adapter-sap/metadata-and-the-wcf-service-model-with-sap.md)  
  
-   [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)  
  
-   [クライアント バインディングを SAP システムを構成します。](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)  
  
-   [WCF サービス モデルを使用して SAP Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して、SAP で受信 RFC 呼び出しを受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して tRFCs を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して、SAP で受信 tRFC の呼び出しを受け取る](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して SAP での Bapi を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して、Idoc を SAP に送信します。](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)