---
title: WCF LOB Adapter SDK を使用して開発のベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ea3a13b-e41f-4920-bf0d-26f7bb145aa3
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f42980d93c7872811ea26fb9fc21a97f7e4e8e2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991323"
---
# <a name="development-best-practices-using-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用して開発のベスト プラクティス
このトピックの「ベスト プラクティスを使用するには、アプリケーションおよびアダプターを向上させるためにします。  

## <a name="call-abort-before-close-on-channel-exception"></a>チャネルの例外で終了する前に中止を呼び出す  
 WCF チャネル モデルを使用するアプリケーションを記述するときに呼び出す必要があります`IRequestChannel.Abort`呼び出す前に`ChannelFactory.Close`します。 表示されない場合、`ChannelFactory.Close`例外をスローします。  

 次の例では、チャネルの操作は、try/catch ブロック内で試行されます。 例外が発生する場合、チャネルは中止されます。  

```csharp  
ChannelFactory<IRequestChannel> cf = new  ChannelFactory<IRequestChannel>();  
IRequestChannel channel = null;  
try  
{  
  cf.Open();  
  channel = cf.CreateChannel();  
  channel.Open();  
  channel.Request();// This causes the channel to go into a faulted state.  
  channel.Close();  
}  
catch (Exception e)  
{  
  // Abort the channel if we have one  
  if(channel != null)  
    channel.Abort();  
}  
finally  
{  
  if (cf.State == CommunicationState.Opened)  
  {  
    cf.Close(); // It throws an exception that the channel is in a faulted state.  
  }  
}  
```  

## <a name="implement-both-asynchronous-and-synchronous-handlers"></a>非同期と同期の両方のハンドラーを実装します。  
 可能であればでは、アダプター ハンドラーを非同期と同期の両方を実装します。 アダプターは、同期呼び出しのみを実装する場合は、大量のメッセージ、またはマルチ スレッド環境で、アダプターを使用する場合の処理時にブロックの問題に実行できます。  

## <a name="use-connection-pooling"></a>接続プールを使用します。  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]接続が既定でプールをサポートします。 ただし、アダプター開発者がバインドのプロパティとして公開するプロパティをプールする接続の決定までなります。 内で使用可能な接続プール設定が定義されている`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`します。  

 内のオプションがない、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を簡単にこれらのプロパティとしてアダプターの接続プロパティを公開します。 アダプター開発者は、アダプターの実装で、プロパティを手動で定義する必要があります。  

```csharp  
public CustomAdapter(): base()  
{  
   this.Settings.ConnectionPool.EnablePooling = true;  
   this.Settings.ConnectionPool.HandlersShareSameConnection = true;  
   this.Settings.ConnectionPool.MaxConnectionsPerSystem = 50;  
   this.Settings.ConnectionPool.MaxAvailableConnections = 5;  
}  
```  

## <a name="ensure-that-the-adapter-supports-two-way-operations"></a>アダプターが双方向の操作をサポートしていることを確認します。  
 アダプターは BizTalk Server から呼び出されると、戻り値は void 場合でも、双方向の操作をサポートする必要があります。 これは、BizTalk Server が任意の発信要求から返される応答を期待しているためと、アダプターのみ一方向の操作を実装している場合に例外をスローします。  

 Void を返す要求-応答コントラクトの例を次に示します。  

```csharp  
[ServiceContract(Namespace=”Http:Microsoft.BizTalk.Samples.WCFAdapterSample”)]  
public interface ICalculator  
{  
   [OperationContract]  
   void Add(double n1, double n2);  
}  
```  

## <a name="implement-tracing"></a>トレースを実装します。  
 開発サイクル中にないかもしれません、コードをステップ実行して問題をデバッグするために、トレースをアダプターを追加してください。 ただし、アダプターが、運用環境でインストールされると、実行時のデバッグを使用して、問題を特定することができません。 アダプター全体でトレースを有効にした場合は、エラーが発生している場所を特定する使用できます。  

 参照してください[WCF LOB Adapter SDK のアダプターのトレース](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md)の詳細。  

## <a name="use-uri-properties-for-frequently-changed-settings"></a>URI のプロパティを使用して、変更頻度の高い設定  
 カスタム プロパティをバインドまたは URI のプロパティとして公開するかどうかを決定する際は、多くの場合、値が変更された場合は、URI プロパティを使用することをお勧めします。 バインドのプロパティは、ほとんど変更されない値を予約する必要があります。  

 バインド プロパティの例は、すべての接続で使用されるデータベース サーバー名になります。 URI のプロパティの使用例は、特定のテーブルまたはその特定の接続で使用されるストアド プロシージャになります。  

## <a name="do-not-pass-user-name-or-password-values-in-the-uri"></a>URI のユーザー名またはパスワードの値を渡すされません。  
 使用する場合は、アダプターは、呼び出し元の資格情報を必要とするをお勧め、 **ClientCredentials** URI の一部としてクライアントの資格情報を渡す代わりに資格情報の値を取得するクラス。 **ClientCredentials**クラスより安全な方法でクライアントからサービスに資格情報を渡すためのものでは、WCF の標準的な機能です。 URI 文字列の一部として、ユーザー情報を渡すと、転送中にユーザー情報を公開できます。  

 資格情報を渡す場合の推奨される方法は、次の表に表示されます。  


|      方法       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              説明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    デザイン時    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]アダプターがサポートされるクライアント資格情報の種類を指定することができます。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|     実行時      | 生成された .NET CLR プロキシを使用して、プログラムで設定できますクライアント資格情報。<br /><br /> `static void Main(string[] args) {    EchoServiceClient client = new EchoServiceClient();    client.ClientCredentials.UserName.UserName = "TestUser";    client.ClientCredentials.UserName.Password = "TestPassword";    string response=client.EchoString("Test String"); }`<br /><br /> 代わりに、チャネルと直接対話する必要がある場合は、チャネル ファクトリを作成するときに、クライアントの資格情報を指定する WCF チャネル モデルを使用できます。<br /><br /> `EchoAdapterBinding binding = new EchoAdapterBinding(); binding.Count = 3; ClientCredentials clientCredentials = new ClientCredentials(); clientCredentials.UserName.UserName = "TestUser"; clientCredentials.UserName.Password = "TestPassword"; BindingParameterCollection bindingParms = new BindingParameterCollection(); bindingParms.Add(clientCredentials); EndpointAddress address = new EndpointAddress("echo://"); IChannelFactory<IRequestChannel> requestChannelFactory = binding.BuildChannelFactory<IRequestChannel>(bindingParms); requestChannelFactory.Open();` |
| WCF の構成 |                                                                                                                                                                                                                                               クライアント構成ファイルで、追加、 \<endpointBehaviors\>要素が含まれる\<clientCredentials\>します。<br /><br /> `<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">       <system.serviceModel>           . . . . .           <behaviors>             <endpointBehaviors>               <behavior name="clientEndpointCredential">                 <clientCredentials>                   <windows allowNtlm="false" allowedImpersonationLevel="Delegation" />                    </clientCredentials>               </behavior>             </endpointBehaviors>           </behaviors>       </system.serviceModel>   </configuration>`                                                                                                                                                                                                                                               |
|   BizTalk を使用します。   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                 追加することができますを使用してアダプターを使用する WCF アダプターを使用する場合、 **clientCredentials**で動作拡張機能、**動作**タブ。これが追加されたらは、エンドポイントの動作で目的のクライアント資格情報を設定できます。                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

## <a name="do-not-return-both-strongdatasettype-and-weakdatasettype"></a>両方が返されない StrongDataSetType と WeakDataSetType  
 アダプターに返された場合、 `DataSet`、いずれかを使用して、`Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A`または`Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`同時に両方は使用しません。 両方の種類によって生成された名前空間とルート ノードの名前が同じであり、WSDL で同時に存在できません。  

 中に`WeakDataSetType`と`StrongDataSetType`両方を表す、 `System.Data.DataSet`、`StrongDataSetType`として生成されたプロキシが表示されるため、.NET アプリケーションで使いやすく、`System.Data.Dataset`します。 によって生成されたプロキシ`WeakDataSetType`は`XmlElement[]`、.NET アプリケーションで使用することが困難であります。  BizTalk Server から返されたスキーマを使用できない`StrongDataSet`が使用できるように`WeakDataSetType`します。  

> [!NOTE]
>  `StrongDataSetType` `WeakDataSetType`のみ、クライアント アプリケーションがアダプターによって渡される XML メッセージを解釈する方法を制御します。 XML メッセージでは、型の指定に関係なく同じです。  

> [!NOTE]
>  返すときに`StrongDataSetType`を設定する必要があります`Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A`に`false`します。 設定すると`true`、既定値は、`XmlSchemaSet::Compile`が呼び出されます内、WSDL でエラーがないことを確認するアダプター、ただし、スキーマによって生成された`StrongDataSetType`で例外が発生する`XmlSchemaSet`。  
>   
>  設定`CompileWsdl`に`false`バイパス プロキシの生成中に、アダプターと検証の WSDL スキーマの検証が行われます。  Svcutil.exe などのユーティリティは、両方のプロキシを生成する`StrongDataSetType`と`WeakDataSetType`します。  

 BizTalk および .NET の両方の環境を操作するには、環境に従い、2 つの戻り値の型を切り替えることができますをバインド プロパティの実装を検討してください。  

```csharp  
internal static QualifiedType GetDataSetQualifiedType(MyAdapterBindingProperties bindingProperties)  
{  
   if (bindingProperties.EnableBizTalkCompatibility)  
      return QualifiedType.WeakDataSetType;  
   else  
      return QualifiedType.StrongDataSetType;  
}  
```  

## <a name="create-meaningful-xsd-schema-names-in-biztalk-server"></a>BizTalk Server で意味のある XSD スキーマの名前を作成します。  
 使用する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]デザイン時ツール、BizTalk プロジェクトで生成される XSD スキーマの名前を使用して作成、`DefaultXsdFileNamePrefix`プロパティ、 `fileNameHint` WSDL 注釈と、必要に応じて、一意の整数値。  

 たとえば場合、 `DefaultXsdFileNamePrefix` "MyAdapter"に設定されている、`fileNameHint`注釈が"Stream"に設定されている、MyAdapterStream.xsd の名前は、XSD スキーマを作成します。  

```  
<xs:schema elementFormDefault='qualified' targetNamespace='http://schemas.microsoft.com/Message' xmlns:xs='http://www.w3.org/2001/XMLSchema' xmlns:tns='http://schemas.microsoft.com/Message'>  
<xs:annotation>  
<xs:appinfo>  
<fileNameHint xmlns='http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd'>Stream</fileNameHint>  
</xs:appinfo>  
</xs:annotation>  
<xs:simpleType name='StreamBody'>  
<xs:restriction base='xs:base64Binary' />  
</xs:simpleType>  
</xs:schema>  

```  

> [!NOTE]
>  既定値`DefaultXsdFileNamePrefix`バインディングの名前を指定します。 別の値を指定するには、オーバーライド`DefaultXsdFileNamePrefix`アダプター クラスから派生したで`Microsoft.ServiceModel.Channels.Common.AdapterBinding`します。  

 追加する 2 つの方法がある、`fileNameHint`スキーマに注釈: エクスポートをオーバーライドしています.OperationMetadata\TypeMetadata またはアダプターの IWsdlRetrieval 実装をオーバーライド スキーマ メソッドします。 いずれかの方法は、基本実装を呼び出すし、スキーマ コレクションのスキーマに注釈を追加します。  

> [!NOTE]
>  エクスポートをオーバーライドするときにしています.スキーマ メソッドでは、同じスキーマに複数の操作/型定義である可能性がありますアダプターを確認してくださいを複数回出現、`fileNameHints`同じスキーマで注釈が競合しません。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]最初に見つかった位置を使用して`fileNameHint`スキーマ内で複数回に発生する場合。  

 追加する次の例では、IWsdlRetrieval が使用される、`fileNameHint`を WSDL 注釈。  

```csharp  
sealed class MyAdapterWsdlRetrieval : IWsdlRetrieval  
{  
   IWsdlRetrieval mBaseWsdlRetrieval;  
   public MyAdapterWsdlRetrieval(IWsdlRetrieval baseWsdlRetrieval)  
   {  
      mBaseWsdlRetrieval = baseWsdlRetrieval;  
   }  

   ServiceDescription IWsdlRetrieval.GetWsdl(Microsoft.ServiceModel.Channels.MetadataRetrievalNode[] nodes, Uri uri, TimeSpan timeout)  
   {  
      ServiceDescription baseDesc = mBaseWsdlRetrieval.GetWsdl(nodes, uri, timeout);  
      foreach (XmlSchema schema in baseDesc.Types.Schemas)  
      {  
         CreateFileNameHint(schema);  
      }  
      return baseDesc;  
   }  

   void CreateFileNameHint(XmlSchema schema)  
   {  
      string targetNamespace = schema.TargetNamespace;  
      if (string.IsNullOrEmpty(targetNamespace))  
         return;  
      string fileNameHint = null;  
      //determine the filename based on namespace  
      if (targetNamespace.StartsWith("myadapter:// adapters.samples.myadaptpter/HelloWorld"))  
      {  
         fileNameHint = "HelloWorld";  
      }  
      if (targetNamespace.StartsWith("myadapter:// adapters.samples.myadapter/Hello"))  
      {  
         fileNameHint = "Hello";  
      }  
      //create the annotation and populate it with fileNameHint  
      XmlSchemaAnnotation annotation = new XmlSchemaAnnotation();  
      XmlSchemaAppInfo appInfo = new XmlSchemaAppInfo();  
      XmlDocument doc = new XmlDocument();  
      XmlNode[] fileNameHintNodes = new XmlNode[1];  
      fileNameHintNodes[0] = doc.CreateElement(null, "fileNameHint", "http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd");  
      fileNameHintNodes[0].AppendChild(doc.CreateTextNode(fileNameHint));  
      appInfo.Markup = fileNameHintNodes;  
      annotation.Items.Add(appInfo);  
      schema.Items.Insert(0, annotation);  
   }  
```  

## <a name="do-not-modify-adapterenvironmentsettings-during-processing"></a>処理中に AdapterEnvironmentSettings は変更しないでください。  
 アダプターはのみに設定する必要があります、 **AdapterEnvironmentSettings**、 **ConnectionPoolManager**、 **ConnectionPool**、および**CommonCacheSize**アダプターの初期化中にし、実行中のインスタンスの値を変更しないでください。  

 これらの設定を変更するには、現在実行中のアダプター インスタンスで、現在実行中の接続の構成設定を上書きする新しい接続でこれが原因します。  

## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して開発のベスト プラクティス](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)