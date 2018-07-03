---
title: SQL アダプターを使用した WCF チャネル モデルの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5e5f77c-c922-4039-92c7-38d2b7638459
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 819143bd7e65c9cea91232e2529b20cfab2c049d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003171"
---
# <a name="overview-of-the-wcf-channel-model-with-the-sql-adapter"></a>SQL アダプターを使用した WCF チャネル モデルの概要
に対して操作を呼び出す、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]コードは、WCF クライアントとして機能し、送信操作をアダプターに送信します。 WCF チャネル モデルでは、コードは、チャネル経由で要求メッセージを送信することによって、アダプターでの操作を呼び出します。  
  
 データ変更メッセージのポーリング ベース アダプターを使用してを受信するコードが WCF サービスとして機能し、受信、受信**ポーリング**、 **TypedPolling**、または**通知**アダプターから操作します。 つまり、コードは、チャネル経由でアダプターからこれらの操作要求メッセージを受信します。  
  
 このセクションのトピックの使用の概要を提供する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="wcf-channel-model-overview"></a>WCF チャネル モデルの概要  
 クライアントとサービスは、SOAP メッセージを交換して通信します。 WCF チャネル モデルとは、このメッセージ交換の低レベルの抽象化です。 インターフェイスおよびチャネル スタックと呼ばれる複数層のプロトコル スタックを使用してメッセージを送受信するための型を提供します。 チャネルのスタックの各層がで構成され、WCF バインドから各チャネルが作成されます。 最下位の層では、トランスポート チャネルです。 トランスポート チャネルがサービスとクライアント間の基盤トランスポート メカニズムを実装し、として上位レイヤー (および最終的には、コンシューマー側アプリケーション) には、各メッセージを表示、 **System.ServiceModel.Message**します。 WCF**メッセージ**クラスは、SOAP メッセージの抽象化します。 WCF には、基本的な SOAP メッセージ交換パターンなどの要求/応答または一方向のモデル化するチャネル形状と呼ばれるいくつかのチャネル インターフェイスが用意されています。 WCF トランスポート バインディングは、1 つの実装を提供します。 または、レイヤーの高い複数のチャネル形状はメッセージの送受信に使用できます。 WCF チャネル モデルの詳細については、次を参照してください。[チャネル モデルの概要](https://msdn.microsoft.com/library/ms729840.aspx)します。
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は WCF サービスとしての SQL Server データベースを公開する WCF カスタム トランスポート バインドします。  
  
## <a name="supported-channel-shapes-for-the-sql-server-adapter"></a>チャネル形状は、SQL Server のアダプターのサポート  
 アダプターは、次の WCF チャネル形状を実装します。  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**インターフェイスは、クライアント側の要求/応答メッセージの交換を実装します。 使用することができます、 **IRequestChannel**応答を使用する操作を実行する選択を実行する例についてはテーブルのクエリします。  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 この図形は、クライアント側の一方向メッセージ交換を実装します。 使用することができます、 **IOutputChannel**戻りパラメーターを持たないプロシージャを呼び出す例については、応答を使用する必要のない操作を呼び出します。  
  
  > [!IMPORTANT]
  >  SQL Server クライアントに、アダプターによってすべての基になる呼び出しは同期的です。 経由で呼び出す操作の結果である SQL Server クライアントへの呼び出しが含まれます、 **IOutputChannel**します。 使用すると、 **IOutputChannel**アダプターは、SQL Server クライアントから受信した応答を破棄します。  
  
- **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。 この図形は、サービス側の一方向メッセージ交換を実装します。 使用する、 **IInputChannel**など、受信操作のメッセージを受信する**ポーリング**または**通知**、アダプターから。  
  
  などの任意の WCF バインド、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ファクトリ パターンを使用して、アプリケーション コードへのチャネルを提供します。 使用する、 **Microsoft.Adapters.SQLBinding**オブジェクトのインスタンスを作成します。  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>** を提供する**IRequestChannel**チャネル アダプターの要求-応答操作の呼び出しに使用することができます。  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>** を提供する**IOutputChannel**チャネル アダプターの一方向の操作の呼び出しに使用することができます。  
  
- **System.ServiceModel.IChannelListener\<IInputChannel\>** を提供する**IInputChannel**際など、受信操作のメッセージを受信するチャネル**ポーリング**または**通知**、アダプターから。  
  
### <a name="creating-messages-for-the-sql-server-database-adapter-in-the-wcf-channel-model"></a>WCF チャネル モデルでは、SQL Server データベース アダプターのメッセージを作成します。  
 WCF では、 **System.ServiceModel.Channels.Message**クラスでのメモリを提供する SOAP メッセージの表現。 作成する、**メッセージ**静的を呼び出すことによってインスタンス**Message.Create**メソッド。  
  
 2 つの重要な部分を SOAP メッセージを作成するときに指定する必要があります、**メッセージ**インスタンスに送信する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
- メッセージのアクションは、SOAP メッセージ ヘッダーの一部である文字列です。 メッセージのアクションは、データベースに対して呼び出す必要がある操作を識別します。 Employee テーブルの選択操作を呼び出すために指定されたメッセージのアクションを次に示します:`TableOp/Select/dbo/Employee`します。  
  
- メッセージの本文には、操作のパラメーターのデータが含まれています。 メッセージ本文が想定されているメッセージのスキーマに対応する、整形式 xml で構成される、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]要求された操作をします。 次のメッセージ本文が Employee テーブルでの選択操作を指定します (選択 * 従業員 WHERE Employee_ID から = 10001)。  
  
  ```  
  <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Columns>*</Columns>  
    <Query>where Employee_ID=10001</Query>  
  </Select>  
  
  ```  
  
  については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メッセージ スキーマと操作のアクションのメッセージを参照してください[メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)します。  
  
  これは、**作成**メソッドがオーバー ロードされ、メッセージ本文を提供するためのさまざまなオプションを提供します。 次のコードを作成する方法を示しています、**メッセージ**インスタンスを使用して、 **XmlReader**メッセージ本文を指定します。 このコードは、メッセージ本文は、ファイルから読み取られます。  
  
```  
XmlReader readerIn = XmlReader.Create("SelectInput.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "TableOp/Select/dbo/Employee",  
    readerIn);  
```  
  
> [!IMPORTANT]
>  メッセージのアクションを指定する必要があります、**メッセージ**インスタンス。 これは、通常はときに、**メッセージ**インスタンスが作成されます。  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)