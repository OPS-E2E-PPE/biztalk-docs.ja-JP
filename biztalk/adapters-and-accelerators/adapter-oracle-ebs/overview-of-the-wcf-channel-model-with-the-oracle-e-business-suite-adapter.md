---
title: Oracle E-business Suite アダプターを使用した WCF チャネル モデルの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3afd2a97-5734-4c25-87a3-702d8461898b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54402a6ea9040d8821912214a6b206ed075628f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375129"
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターを使用した WCF チャネル モデルの概要
に対して操作を呼び出す、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]コードは、WCF クライアントとして機能し、送信操作をアダプターに送信します。 WCF チャネル モデルでは、コードは、チャネル経由で要求メッセージを送信することによって、アダプターでの操作を呼び出します。  
  
 ポーリングに基づいたデータ変更を使用してメッセージを受け取るなどの受信操作の呼び出しに、**ポーリング**コードが WCF サービスとして機能し、アダプターからの受信操作の受信アダプターによって、操作を指定します。 つまり、コードは、チャネル経由で、アダプターから要求メッセージを受信します。  
  
 このセクションのトピックの使用の概要を提供する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="wcf-channel-model-overview"></a>WCF チャネル モデルの概要  
 クライアントとサービスは、SOAP メッセージを交換して通信します。 WCF チャネル モデルとは、このメッセージ交換の低レベルの抽象化です。 インターフェイスおよびチャネル スタックと呼ばれる複数層のプロトコル スタックを使用してメッセージを送受信するための型を提供します。 チャネルのスタックの各層がで構成され、WCF バインドから各チャネルが作成されます。 最下位の層では、トランスポート チャネルです。 トランスポート チャネルがサービスとクライアント間の基盤トランスポート メカニズムを実装し、として上位レイヤー (および最終的には、コンシューマー側アプリケーション) には、各メッセージを表示、 **System.ServiceModel.Message**します。 WCF**メッセージ**クラスは、SOAP メッセージの抽象化します。 WCF には、基本的な SOAP メッセージ交換パターンなどの要求/応答または一方向のモデル化するチャネル形状と呼ばれるいくつかのチャネル インターフェイスが用意されています。 WCF トランスポート バインディングは、1 つの実装を提供します。 または、レイヤーの高い複数のチャネル形状はメッセージの送受信に使用できます。 WCF チャネル モデルの詳細についてを参照してください「チャネル モデルの概要」 [ http://go.microsoft.com/fwlink/?LinkId=82614](http://go.microsoft.com/fwlink/?LinkId=82614)します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]は WCF サービスとしての Oracle E-business Suite 成果物を公開する WCF カスタム トランスポート バインドします。  
  
## <a name="supported-channel-shapes-for-the-oracle-e-business-suite-adapter"></a>チャネル形状は、Oracle E-business Suite アダプターのサポート  
 アダプターは、次の WCF チャネル形状を実装します。  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**インターフェイスは、クライアント側の要求/応答メッセージの交換を実装します。 使用することができます、 **IRequestChannel**応答を使用する操作を実行する選択を実行する例のクエリ インターフェイス テーブルでします。  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 この図形は、クライアント側の一方向メッセージ交換を実装します。 使用することができます、 **IOutputChannel**を OUT パラメーターを持たないプロシージャを呼び出す例については、応答を使用する必要のない操作を呼び出します。  
  
  > [!IMPORTANT]
  >  Oracle クライアントに、アダプターによってすべての基になる呼び出しは同期的です。 経由で呼び出す操作の結果である Oracle クライアントへの呼び出しが含まれます、 **IOutputChannel**します。 使用すると、 **IOutputChannel**アダプターは、Oracle クライアントから受信した応答を破棄します。  
  
- **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。 この図形は、サービス側の一方向メッセージ交換を実装します。 使用する、 **IInputChannel**アダプターから受信メッセージを受信します。  
  
  などの任意の WCF バインド、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ファクトリ パターンを使用して、アプリケーション コードへのチャネルを提供します。 使用する、 **Microsoft.Adapters.OracleEBSBinding**オブジェクトのインスタンスを作成します。  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>** を提供する**IRequestChannel**チャネル アダプターの要求-応答操作の呼び出しに使用することができます。  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>** を提供する**IOutputChannel**チャネル アダプターの一方向の操作の呼び出しに使用することができます。  
  
- **System.ServiceModel.IChannelListener\<IInputChannel\>** を提供する**IInputChannel**チャネルがメッセージを受信する受信アダプターから使用することができます。  
  
### <a name="creating-messages-for-the-oracle-enterprise-business-solution-in-the-wcf-channel-model"></a>WCF チャネル モデルの Oracle Enterprise ビジネス ソリューションのメッセージを作成  
 WCF では、 **System.ServiceModel.Channels.Message**クラスでのメモリを提供する SOAP メッセージの表現。 作成する、**メッセージ**静的を呼び出すことによってインスタンス**Message.Create**メソッド。  
  
 2 つの重要な部分を SOAP メッセージを作成するときに指定する必要があります、**メッセージ**インスタンスに送信する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
- メッセージのアクションは、SOAP メッセージ ヘッダーの一部である文字列です。 メッセージのアクションは、Oracle E-business Suite で呼び出す必要がある操作を識別します。 呼び出す指定したメッセージのアクションを次に示します、**顧客インターフェイス**同時実行プログラム、 **Receivables** Oracle E-business suite アプリケーション:`ConcurrentPrograms/AR/RACUST`します。  
  
- メッセージの本文には、操作のパラメーターのデータが含まれています。 メッセージ本文が想定されているメッセージのスキーマに対応する、整形式 xml で構成される、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求された操作をします。 次のメッセージ本文を起動する要求メッセージを指定します、**顧客インターフェイス**同時実行プログラム。  
  
  ```  
  <RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
    <Description>Customer Interface Program</Description>  
    <StartTime></StartTime>  
    <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
    <ORG_ID>203</ORG_ID>  
  </RACUST>  
  
  ```  
  
  については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージ スキーマと操作のアクションのメッセージを参照してください[メッセージとメッセージ スキーマの BizTalk Adapter for Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)します。  
  
  **作成**メソッドがオーバー ロードされ、メッセージ本文を提供するためのさまざまなオプションを提供します。 次のコードを作成する方法を示しています、**メッセージ**インスタンスを使用して、 **XmlReader**メッセージ本文を指定します。 このコードは、メッセージ本文は、ファイルから読み取られます。  
  
```  
XmlReader readerIn = XmlReader.Create("ConcProgRequest.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "ConcurrentPrograms/AR/RACUST",  
    readerIn);  
```  
  
 ここで、ConProgRequest.xml には、要求メッセージが含まれています。  
  
> [!IMPORTANT]
>  メッセージのアクションを指定する必要があります、**メッセージ**インスタンス。 これは、通常はときに、**メッセージ**インスタンスが作成されます。  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle E-business Suite のアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)