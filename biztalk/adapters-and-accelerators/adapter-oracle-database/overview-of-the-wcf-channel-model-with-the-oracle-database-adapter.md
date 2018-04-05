---
title: Oracle データベース アダプターで WCF チャネル モデルの概要 |Microsoft ドキュメント
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
ms.openlocfilehash: 94cb4b8cfdb0315b55aa88ddd385396ff967b8f6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-database-adapter"></a>Oracle データベース アダプターで WCF チャネル モデルの概要
操作の呼び出しに、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]コードが WCF クライアントとして機能し、アダプターに送信操作を送信します。 WCF チャネル モデルでは、コードは、チャネル経由で要求メッセージを送信することによって、アダプターでの操作を呼び出します。  
  
 Receiveing ポーリング ベース データ変更を使用してメッセージ、アダプターによって提供される POLLINGSTMT 操作などの受信操作の呼び出しには、コードは、WCF サービスとして機能し、アダプターから受信操作を受け取ります。 言い換えると、コードは、チャネル経由で、アダプターから要求メッセージを受信します。  
  
 このセクションのトピックを使用しての概要を説明する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルとします。  
  
## <a name="wcf-channel-model-overview"></a>WCF チャネル モデルの概要  
 クライアントとサービスは、SOAP メッセージを交換して通信します。 WCF チャネル モデルは、このメッセージ交換の低レベルの抽象化です。 インターフェイスとすると、チャネル スタックと呼ばれる階層状のプロトコル スタックを使用してメッセージを送受信できるようにする型を提供します。 スタックの各層は、チャネルから成るされ、WCF バインドから各チャネルが作成されます。 最下位の層で、トランスポート チャネルです。 トランスポート チャネルがサービスとクライアント間の基になるトランスポート機構を実装し、として上の層 (と最終的に処理を行うアプリケーション) を各メッセージを表示、 **System.ServiceModel.Message**です。 WCF**メッセージ**クラスは、SOAP メッセージの抽象化します。 WCF には、基本的な SOAP メッセージ交換パターンをモデルなどの要求/応答または一方向チャネル形状と呼ばれるいくつかのチャネル インターフェイスが用意されています。 WCF トランスポート バインディングは、1 つの実装を提供またはレイヤーの高い複数のチャネル形状がメッセージの送受信に使用できます。 WCF チャネル モデルの詳細については、次を参照してください。[チャネル モデルの概要](https://msdn.microsoft.com/library/ms729840.aspx)です。   
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]は、WCF サービスとして Oracle データベースを公開する WCF カスタム トランスポート バインディングです。  
  
## <a name="supported-channel-shapes-for-the-oracle-database-adapter"></a>Oracle データベース アダプターのチャネル形状をサポート  
 アダプターでは、次の WCF チャネル形状を実装します。  
  
-   **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**インターフェイスは、クライアント側の要求/応答メッセージ交換を実装します。 使用することができます、 **IRequestChannel**応答を消費する操作を実行する例 SELECT を実行するクエリを Oracle のテーブルにします。  
  
-   **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 この図形では、クライアント側の一方向メッセージ交換を実装します。 使用することができます、 **IOutputChannel** OUT パラメーターがない Oracle プロシージャを呼び出す例については、応答を使用する必要のない、操作を呼び出します。  
  
    > [!IMPORTANT]
    >  Oracle クライアントにアダプターによってすべての基になる呼び出しは同期的です。 経由で呼び出された操作の結果は、Oracle クライアントへの呼び出しが含まれます、 **IOutputChannel**です。 使用すると、 **IOutputChannel**アダプターは、Oracle クライアントから受信した応答を破棄します。  
  
-   **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。 この図形では、一方向メッセージ交換のサービス側を実装します。 使用する、 **IInputChannel**アダプターからの受信操作のメッセージを受信します。  
  
 任意の WCF バインドと同様に、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ファクトリ パターンを使用してアプリケーション コードへのチャネルを提供します。 使用する、 **Microsoft.Adapters.OracleDBBinding**オブジェクトのインスタンスを作成します。  
  
-   **System.ServiceModel.ChannelFactory\<IRequestChannel\>** を提供する**IRequestChannel**チャネル アダプターの要求-応答操作の呼び出しに使用することができます。  
  
-   **System.ServiceModel.ChannelFactory\<IOutputChannel\>** を提供する**IOutputChannel**チャネル アダプターの一方向の操作の呼び出しに使用することができます。  
  
-   **System.ServiceModel.IChannelListener\<IInputChannel\>** を提供する**IInputChannel**チャネル アダプターから着信メッセージ (POLLINGSTMT 操作など) の受信に使用することができます.  
  
### <a name="creating-messages-for-the-oracle-database-adapter-in-the-wcf-channel-model"></a>WCF チャネル モデルでの Oracle データベース アダプターのメッセージを作成します。  
 WCF では、 **System.ServiceModel.Channels.Message**クラスは、メモリに SOAP メッセージの表現。 作成する、**メッセージ**、静的なを呼び出すことによってインスタンス**Message.Create**メソッドです。  
  
 必要がありますを指定することを作成する場合、SOAP メッセージに 2 つの重要な部分、**メッセージ**インスタンスに送信する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
-   メッセージのアクションは、SOAP メッセージ ヘッダーの一部である文字列です。 メッセージのアクションでは、Oracle データベースで呼び出される操作を識別します。 SCOTT/EMP テーブルに対する Select 操作の呼び出しに指定されたメッセージのアクションを次に示します:`http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select`です。  
  
-   メッセージの本文には、操作のパラメーターのデータが含まれています。 メッセージ本文がによって予期されるメッセージ スキーマに対応する整形式 xml で構成される、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]要求された操作にします。 次のメッセージ本文には、SCOTT での選択操作を指定します。EMP テーブル (選択 * から EMP)。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP">  
        <COLUMN_NAMES>*</COLUMN_NAMES>  
    </Select>  
    ```  
  
 については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージ スキーマと操作のアクションのメッセージを参照してください[メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)です。  
  
 これは、**作成**メソッドはオーバー ロードされ、メッセージ本文を提供するためのさまざまなオプションを提供します。 次のコードを作成する方法を示しています、**メッセージ**インスタンスを使用して、 **XmlReader**をメッセージ本文を指定します。 このコードでは、メッセージの本文をファイルから読み取られます。  
  
```  
XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select",  
    readerIn);  
```  
  
> [!IMPORTANT]
>  メッセージのアクションを指定する必要があります、**メッセージ**インスタンス。 通常、これを行うときに、**メッセージ**インスタンスを作成します。  
  
## <a name="streaming-support-for-lob-data-types-in-the-wcf-channel-model"></a>WCF チャネル モデルの LOB データ型のストリーミング サポート  
 アダプター側に表示される一部の操作に対しては、エンド ツー エンドは、LOB データ型のストリーミングをサポートします。 作成およびチャネル経由で送受信するメッセージを処理する方法をこれらの操作には、LOB データのストリーミングはサポートされているかどうかを判断します。  
  
 方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]LOB データのストリーミング サポートを参照してください[Oracle データベース アダプターのラージ オブジェクト データ型をストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)です。  
  
 ノード値のエンド ツー エンドの LOB データのストリーミングをサポートするために、コードでは、ストリーミングの実装の詳細については、次を参照してください。[ストリーミング Oracle LOB データ型を使用してデータベース、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)です。  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)