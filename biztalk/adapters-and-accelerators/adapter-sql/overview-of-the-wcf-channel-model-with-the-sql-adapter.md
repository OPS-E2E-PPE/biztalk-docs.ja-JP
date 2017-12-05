---
title: "SQL アダプタを使用して WCF チャネル モデルの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5e5f77c-c922-4039-92c7-38d2b7638459
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad124e7ce9fdf8c3dac6a1ac0ffda122127becb9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="overview-of-the-wcf-channel-model-with-the-sql-adapter"></a>SQL アダプタを使用して WCF チャネル モデルの概要
操作の呼び出しに、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]コードが WCF クライアントとして機能し、アダプターに送信操作を送信します。 WCF チャネル モデルでは、コードは、チャネル経由で要求メッセージを送信することによって、アダプターでの操作を呼び出します。  
  
 メッセージを受信するポーリングに基づくデータが変更されて、アダプターを使用して、コードが WCF サービスとして機能し、受信、受信**ポーリング**、 **TypedPolling**、または**通知**アダプターから操作します。 言い換えると、コードは、チャネル経由で、アダプターからこれらの操作の要求メッセージを受け取ります。  
  
 このセクションのトピックを使用しての概要を説明する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF チャネル モデルとします。  
  
## <a name="wcf-channel-model-overview"></a>WCF チャネル モデルの概要  
 クライアントとサービスは、SOAP メッセージを交換して通信します。 WCF チャネル モデルは、このメッセージ交換の低レベルの抽象化です。 インターフェイスとすると、チャネル スタックと呼ばれる階層状のプロトコル スタックを使用してメッセージを送受信できるようにする型を提供します。 スタックの各層は、チャネルから成るされ、WCF バインドから各チャネルが作成されます。 最下位の層で、トランスポート チャネルです。 トランスポート チャネルがサービスとクライアント間の基になるトランスポート機構を実装し、として上の層 (と最終的に処理を行うアプリケーション) を各メッセージを表示、 **System.ServiceModel.Message**です。 WCF**メッセージ**クラスは、SOAP メッセージの抽象化します。 WCF には、基本的な SOAP メッセージ交換パターンをモデルなどの要求/応答または一方向チャネル形状と呼ばれるいくつかのチャネル インターフェイスが用意されています。 WCF トランスポート バインディングは、1 つの実装を提供またはレイヤーの高い複数のチャネル形状がメッセージの送受信に使用できます。 WCF チャネル モデルの詳細については、次を参照してください。[チャネル モデルの概要](https://msdn.microsoft.com/library/ms729840.aspx)です。
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は、WCF サービスとしての SQL Server データベースを公開する WCF カスタム トランスポート バインディングです。  
  
## <a name="supported-channel-shapes-for-the-sql-server-adapter"></a>チャネル形状は、SQL Server のアダプターのサポート  
 アダプターでは、次の WCF チャネル形状を実装します。  
  
-   **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**インターフェイスは、クライアント側の要求/応答メッセージ交換を実装します。 使用することができます、 **IRequestChannel**応答を消費する操作を実行するには、たとえば、SELECT を実行するためにテーブルのクエリします。  
  
-   **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 この図形では、クライアント側の一方向メッセージ交換を実装します。 使用することができます、 **IOutputChannel**を戻り値パラメーターを持たず、プロシージャを呼び出す例については、応答を使用する必要のない、操作を呼び出します。  
  
    > [!IMPORTANT]
    >  SQL Server クライアントにアダプターによってすべての基になる呼び出しは同期的です。 経由で呼び出された操作の結果である SQL Server クライアントへの呼び出しが含まれます、 **IOutputChannel**です。 使用すると、 **IOutputChannel**アダプターは、SQL Server クライアントから受信した応答を破棄します。  
  
-   **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。 この図形では、一方向メッセージ交換のサービス側を実装します。 使用する、 **IInputChannel**メッセージを受信する受信操作は、のように**ポーリング**または**通知**、アダプターからです。  
  
 任意の WCF バインドと同様に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ファクトリ パターンを使用してアプリケーション コードへのチャネルを提供します。 使用する、 **Microsoft.Adapters.SQLBinding**オブジェクトのインスタンスを作成します。  
  
-   **System.ServiceModel.ChannelFactory\<IRequestChannel\>** を提供する**IRequestChannel**チャネル アダプターの要求-応答操作の呼び出しに使用することができます。  
  
-   **System.ServiceModel.ChannelFactory\<IOutputChannel\>** を提供する**IOutputChannel**チャネル アダプターの一方向の操作の呼び出しに使用することができます。  
  
-   **System.ServiceModel.IChannelListener\<IInputChannel\>** を提供する**IInputChannel**などの受信操作は、メッセージの受信に使用できるチャネル**ポーリング**または**通知**、アダプターからです。  
  
### <a name="creating-messages-for-the-sql-server-database-adapter-in-the-wcf-channel-model"></a>WCF チャネル モデルでは、SQL Server データベース アダプターのメッセージを作成します。  
 WCF では、 **System.ServiceModel.Channels.Message**クラスは、メモリに SOAP メッセージの表現。 作成する、**メッセージ**、静的なを呼び出すことによってインスタンス**Message.Create**メソッドです。  
  
 必要がありますを指定することを作成する場合、SOAP メッセージに 2 つの重要な部分、**メッセージ**インスタンスに送信する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
-   メッセージのアクションは、SOAP メッセージ ヘッダーの一部である文字列です。 メッセージのアクションでは、データベースで呼び出される操作を識別します。 Employee テーブルでの Select 操作の呼び出しに指定されたメッセージのアクションを次に示します:`TableOp/Select/dbo/Employee`です。  
  
-   メッセージの本文には、操作のパラメーターのデータが含まれています。 メッセージ本文がによって予期されるメッセージ スキーマに対応する整形式 xml で構成される、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]要求された操作にします。 次のメッセージ本文が Employee テーブルでの選択操作を指定します (選択 * 従業員 WHERE Employee_ID = 10001)。  
  
    ```  
    <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <Columns>*</Columns>  
      <Query>where Employee_ID=10001</Query>  
    </Select>  
  
    ```  
  
 については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メッセージ スキーマと操作のアクションのメッセージを参照してください[メッセージと BizTalk Adapter for SQL Server のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)です。  
  
 これは、**作成**メソッドはオーバー ロードされ、メッセージ本文を提供するためのさまざまなオプションを提供します。 次のコードを作成する方法を示しています、**メッセージ**インスタンスを使用して、 **XmlReader**をメッセージ本文を指定します。 このコードでは、メッセージの本文をファイルから読み取られます。  
  
```  
XmlReader readerIn = XmlReader.Create("SelectInput.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "TableOp/Select/dbo/Employee",  
    readerIn);  
```  
  
> [!IMPORTANT]
>  メッセージのアクションを指定する必要があります、**メッセージ**インスタンス。 通常、これを行うときに、**メッセージ**インスタンスを作成します。  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)