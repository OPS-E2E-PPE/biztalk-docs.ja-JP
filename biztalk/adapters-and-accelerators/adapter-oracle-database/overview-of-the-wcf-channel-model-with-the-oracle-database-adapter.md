---
title: Oracle データベース アダプターを使用した WCF チャネル モデルの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, overview
ms.assetid: 4712ba62-8360-475c-b2e4-422e499eca21
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2018910c79e0dea66caaf412d8dc2c650647d819
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376698"
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-database-adapter"></a>Oracle データベース アダプターを使用した WCF チャネル モデルの概要
に対して操作を呼び出す、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]コードは、WCF クライアントとして機能し、送信操作をアダプターに送信します。 WCF チャネル モデルでは、コードは、チャネル経由で要求メッセージを送信することによって、アダプターでの操作を呼び出します。  
  
 Receiveing ポーリングに基づいたデータ変更メッセージなど、アダプターによって提供される POLLINGSTMT 操作を使用して、受信操作の呼び出しには、コードは WCF サービスとして動作し、アダプターから受信操作を受信します。 つまり、コードは、チャネル経由で、アダプターから要求メッセージを受信します。  
  
 このセクションのトピックの使用の概要を提供する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="wcf-channel-model-overview"></a>WCF チャネル モデルの概要  
 クライアントとサービスは、SOAP メッセージを交換して通信します。 WCF チャネル モデルとは、このメッセージ交換の低レベルの抽象化です。 インターフェイスおよびチャネル スタックと呼ばれる複数層のプロトコル スタックを使用してメッセージを送受信するための型を提供します。 チャネルのスタックの各層がで構成され、WCF バインドから各チャネルが作成されます。 最下位の層では、トランスポート チャネルです。 トランスポート チャネルがサービスとクライアント間の基盤トランスポート メカニズムを実装し、として上位レイヤー (および最終的には、コンシューマー側アプリケーション) には、各メッセージを表示、 **System.ServiceModel.Message**します。 WCF**メッセージ**クラスは、SOAP メッセージの抽象化します。 WCF には、基本的な SOAP メッセージ交換パターンなどの要求/応答または一方向のモデル化するチャネル形状と呼ばれるいくつかのチャネル インターフェイスが用意されています。 WCF トランスポート バインディングは、1 つの実装を提供します。 または、レイヤーの高い複数のチャネル形状はメッセージの送受信に使用できます。 WCF チャネル モデルの詳細については、次を参照してください。[チャネル モデルの概要](https://msdn.microsoft.com/library/ms729840.aspx)します。   
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF サービスとしての Oracle データベースを公開する WCF カスタム トランスポート バインドします。  
  
## <a name="supported-channel-shapes-for-the-oracle-database-adapter"></a>チャネル形状は、Oracle データベース アダプターのサポート  
 アダプターは、次の WCF チャネル形状を実装します。  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**インターフェイスは、クライアント側の要求/応答メッセージの交換を実装します。 使用することができます、 **IRequestChannel**応答を使用する操作を実行する選択を実行する例についてはクエリ Oracle のテーブルにします。  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 この図形は、クライアント側の一方向メッセージ交換を実装します。 使用することができます、 **IOutputChannel**を OUT パラメーターを持たない Oracle プロシージャを呼び出す例については、応答を使用する必要のない操作を呼び出します。  
  
  > [!IMPORTANT]
  >  Oracle クライアントに、アダプターによってすべての基になる呼び出しは同期的です。 経由で呼び出す操作の結果である Oracle クライアントへの呼び出しが含まれます、 **IOutputChannel**します。 使用すると、 **IOutputChannel**アダプターは、Oracle クライアントから受信した応答を破棄します。  
  
- **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。 この図形は、サービス側の一方向メッセージ交換を実装します。 使用する、 **IInputChannel**アダプターからの受信操作のメッセージを受信します。  
  
  などの任意の WCF バインド、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ファクトリ パターンを使用して、アプリケーション コードへのチャネルを提供します。 使用する、 **Microsoft.Adapters.OracleDBBinding**オブジェクトのインスタンスを作成します。  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>** を提供する**IRequestChannel**チャネル アダプターの要求-応答操作の呼び出しに使用することができます。  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>** を提供する**IOutputChannel**チャネル アダプターの一方向の操作の呼び出しに使用することができます。  
  
- **System.ServiceModel.IChannelListener\<IInputChannel\>** を提供する**IInputChannel**チャネル アダプターからの受信メッセージ (例: POLLINGSTMT 操作) の受信に使用できます。  
  
### <a name="creating-messages-for-the-oracle-database-adapter-in-the-wcf-channel-model"></a>WCF チャネル モデルでの Oracle データベース アダプターのメッセージを作成します。  
 WCF では、 **System.ServiceModel.Channels.Message**クラスでのメモリを提供する SOAP メッセージの表現。 作成する、**メッセージ**静的を呼び出すことによってインスタンス**Message.Create**メソッド。  
  
 2 つの重要な部分を SOAP メッセージを作成するときに指定する必要があります、**メッセージ**インスタンスに送信する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
- メッセージのアクションは、SOAP メッセージ ヘッダーの一部である文字列です。 メッセージのアクションは、Oracle データベースで呼び出す必要がある操作を識別します。 /SCOTT/EMP テーブルの選択操作を呼び出すために指定されたメッセージのアクションを次に示します:`http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select`します。  
  
- メッセージの本文には、操作のパラメーターのデータが含まれています。 メッセージ本文が想定されているメッセージのスキーマに対応する、整形式 xml で構成される、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]要求された操作をします。 次のメッセージ本文には、SCOTT での選択操作を指定します。EMP テーブル (選択 * から EMP)。  
  
  ```  
  <?xml version="1.0" encoding="utf-8" ?>  
  <Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP">  
      <COLUMN_NAMES>*</COLUMN_NAMES>  
  </Select>  
  ```  
  
  については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージ スキーマと操作のアクションのメッセージを参照してください[メッセージとメッセージ スキーマの BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)します。  
  
  これは、**作成**メソッドがオーバー ロードされ、メッセージ本文を提供するためのさまざまなオプションを提供します。 次のコードを作成する方法を示しています、**メッセージ**インスタンスを使用して、 **XmlReader**メッセージ本文を指定します。 このコードは、メッセージ本文は、ファイルから読み取られます。  
  
```  
XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select",  
    readerIn);  
```  
  
> [!IMPORTANT]
>  メッセージのアクションを指定する必要があります、**メッセージ**インスタンス。 これは、通常はときに、**メッセージ**インスタンスが作成されます。  
  
## <a name="streaming-support-for-lob-data-types-in-the-wcf-channel-model"></a>WCF チャネル モデルでの LOB データ型のストリーミング サポート  
 アダプター側に表示される一部の操作のエンド ツー エンドの LOB データ型のストリーミングはサポートされています。 作成し、チャネル経由で送受信するメッセージを使用する方法をこれらの操作には、LOB データのストリーミングがサポートされているかどうか判断します。  
  
 方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]LOB データのストリーミング サポートを参照してください[Oracle データベース アダプターのラージ オブジェクト データ型のストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)します。  
  
 ノード値のエンド ツー エンドの LOB データのストリーミングをサポートするために、コードでは、ストリーミングの実装の詳細については、次を参照してください。[ストリーミング Oracle LOB データ型を使用してデータベース、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)します。  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)