---
title: "WCF LOB Adapter SDK を使用して、開発のベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ea3a13b-e41f-4920-bf0d-26f7bb145aa3
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9786896a4a5983a438dd855dcc858ba4485cbc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="development-best-practices-using-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用して、開発のベスト プラクティス
このトピックの「ベスト プラクティスを使用するには、アプリケーションおよびアダプターを向上させるためにします。  
  
## <a name="call-abort-before-close-on-channel-exception"></a>チャネルの例外で終了する前に中止を呼び出す  
 WCF チャネル モデルを使用するアプリケーションを記述するときに呼び出す必要は`IRequestChannel.Abort`呼び出す前に`ChannelFactory.Close`です。 そうしない場合`ChannelFactory.Close`例外をスローします。  
  
 次の例では、チャネルの操作が try ブロックと catch ブロック内でしようとしました。 例外が発生する場合、チャネルは中止されます。  
  
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
  
## <a name="implement-both-asynchronous-and-synchronous-handlers"></a>非同期および同期の両方のハンドラーを実装します。  
 可能な場合、アダプターで非同期および同期の両方のハンドラーを実装します。 アダプターがのみ同期呼び出しを実装する場合、大量のメッセージ、またはマルチ スレッド環境で、アダプターを使用する場合の処理時にブロックの問題に遭遇する可能性があります。  
  
## <a name="use-connection-pooling"></a>接続プールを使用します。  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]既定で接続プール機能をサポートしています。 ただし、アダプター開発者プールのプロパティはバインドのプロパティとして公開する決定をします。 内で使用可能な接続プール設定が定義されている`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`です。  
  
 内のオプションはありません、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を簡単にこれらのプロパティとしてアダプター接続のプロパティを公開します。 アダプター開発者は、アダプターの実装でプロパティを手動で定義する必要があります。  
  
```csharp  
public CustomAdapter(): base()  
{  
   this.Settings.ConnectionPool.EnablePooling = true;  
   this.Settings.ConnectionPool.HandlersShareSameConnection = true;  
   this.Settings.ConnectionPool.MaxConnectionsPerSystem = 50;  
   this.Settings.ConnectionPool.MaxAvailableConnections = 5;  
}  
```  
  
## <a name="ensure-that-the-adapter-supports-two-way-operations"></a>アダプターが双方向の操作をサポートしていることを確認してください。  
 アダプターは BizTalk Server から呼び出されると、場合でも、戻り値は void、双方向の操作をサポートする必要があります。 これは BizTalk Server で、出力方向の要求から返された応答を要求するためと、アダプターには、一方向操作のみを実装する場合に例外をスローします。  
  
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
 開発サイクル中にないように思えますコードをステップ実行して、問題をデバッグするため、トレースを使用しているアダプターを追加するのには重要です。 ただし、実稼働環境で、アダプターがインストールされると、できない問題を特定する実行時のデバッグを使用します。 アダプター全体でトレースを有効にした場合、障害が発生している場所の特定に使用できます。  
  
 参照してください[WCF LOB Adapter SDK を持つアダプターのトレース](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md)詳細についてはします。  
  
## <a name="use-uri-properties-for-frequently-changed-settings"></a>URI のプロパティ設定を使用して頻繁に変更されます。  
 バインドまたは URI プロパティとしてカスタム プロパティを公開するかどうかを決定する際に、多くの場合、値が変更された場合は、URI プロパティを使用することをお勧めします。 バインドのプロパティは、めったに変化する値を予約する必要があります。  
  
 例バインディング プロパティは、すべての接続で使用されるデータベース サーバー名になります。 URI プロパティの使用例は、特定のテーブルまたはその特定の接続で使用するストアド プロシージャになります。  
  
## <a name="do-not-pass-user-name-or-password-values-in-the-uri"></a>URI にユーザー名またはパスワードの値を渡すされません。  
 使用する場合、アダプターは、呼び出し元の資格情報を必要とするをお勧め、 **ClientCredentials** URI の一部としてクライアントの資格情報を渡す代わりに資格情報の値を取得するクラス。 **ClientCredentials**クラスより安全な方法でクライアントからサービスに資格情報を渡すためのものでは、WCF の標準機能です。 URI 文字列の一部として、ユーザー情報を渡すと、転送中にユーザー情報が公開する可能性があります。  
  
 資格情報を渡す場合の推奨される方法は、次の表に示します。  
  
|方法|Description|  
|------------|-----------------|  
|デザイン時|使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]アダプタでは、クライアント資格情報の種類を指定することができます。|  
|実行時|生成された .NET CLR プロキシを使用する場合できるプログラムでクライアント資格情報を設定します。<br /><br /> `static void Main(string[] args) {    EchoServiceClient client = new EchoServiceClient();    client.ClientCredentials.UserName.UserName = "TestUser";    client.ClientCredentials.UserName.Password = "TestPassword";    string response=client.EchoString("Test String"); }`<br /><br /> 代わりに、チャネルと直接対話する必要がある場合 WCF チャネル モデルを使用してチャネル ファクトリを作成するときに、クライアントの資格情報を指定することができます。<br /><br /> `EchoAdapterBinding binding = new EchoAdapterBinding(); binding.Count = 3; ClientCredentials clientCredentials = new ClientCredentials(); clientCredentials.UserName.UserName = "TestUser"; clientCredentials.UserName.Password = "TestPassword"; BindingParameterCollection bindingParms = new BindingParameterCollection(); bindingParms.Add(clientCredentials); EndpointAddress address = new EndpointAddress("echo://"); IChannelFactory<IRequestChannel> requestChannelFactory = binding.BuildChannelFactory<IRequestChannel>(bindingParms); requestChannelFactory.Open();`|  
|WCF の構成|クライアント構成ファイルで追加、 \<endpointBehaviors > 要素を含む\<clientCredentials >。<br /><br /> `<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">       <system.serviceModel>           . . . . .           <behaviors>             <endpointBehaviors>               <behavior name="clientEndpointCredential">                 <clientCredentials>                   <windows allowNtlm="false" allowedImpersonationLevel="Delegation" />                    </clientCredentials>               </behavior>             </endpointBehaviors>           </behaviors>       </system.serviceModel>   </configuration>`|  
|BizTalk の使用|追加することができますを使用してアダプターを使用する WCF アダプターを使用する場合、 **clientCredentials**で動作拡張機能、**動作**タブです。これを追加した後は、エンドポイントの動作で目的のクライアント資格情報を設定できます。|  
  
## <a name="do-not-return-both-strongdatasettype-and-weakdatasettype"></a>両方を返さない StrongDataSetType と WeakDataSetType  
 アダプターが返された場合、 `DataSet`、いずれかの方法`Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A`または`Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`は、同時に両方を使用しません。 両方の種類によって生成される名前空間とルート ノード名が同じであり、WSDL で同時に存在できません。  
  
 中に`WeakDataSetType`と`StrongDataSetType`両方を表す、 `System.Data.DataSet`、`StrongDataSetType`として生成されたプロキシが表示されるため、.NET アプリケーションで使用する方が簡単`System.Data.Dataset`です。 によって生成されたプロキシ`WeakDataSetType`は`XmlElement[]`、これは .NET アプリケーションで使用することは困難です。  BizTalk Server から返されたスキーマを使用できない`StrongDataSet`を使用することが、`WeakDataSetType`です。  
  
> [!NOTE]
>  `StrongDataSetType``WeakDataSetType`のみ、クライアント アプリケーションがアダプターによって渡された XML メッセージを解釈する方法を制御します。 XML メッセージは、型の指定に関係なく同じです。  
  
> [!NOTE]
>  返すときに`StrongDataSetType`、設定する必要があります`Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A`に`false`です。 設定すると`true`、既定値、`XmlSchemaSet::Compile`が呼び出された内アダプター WSDL でエラーがないことを確認するには、ただし、スキーマによって生成される`StrongDataSetType`で例外が生成されます`XmlSchemaSet`です。  
>   
>  設定`CompileWsdl`に`false`バイパス プロキシの生成中に、アダプターと検証内での WSDL スキーマ検証が行われます。  Svcutil.exe などのユーティリティは、両方のプロキシを生成できません`StrongDataSetType`と`WeakDataSetType`です。  
  
 BizTalk と .NET の両方の環境を操作するには、環境内で使用される 2 つの戻り値の型の間で切り替えを可能にするバインディングのプロパティを実装することを検討してください。  
  
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
 使用する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]デザイン時ツール、BizTalk プロジェクトで生成される XSD スキーマの名前が作成されたを使用して、`DefaultXsdFileNamePrefix`プロパティ、 `fileNameHint` WSDL 内の注釈と、必要に応じて、一意の整数値。  
  
 たとえば場合、 `DefaultXsdFileNamePrefix` "MyAdapter"に設定されていると、`fileNameHint`注釈が"Stream"に設定されている、MyAdapterStream.xsd の名前は、XSD スキーマを作成します。  
  
```  
\<xs:schema elementFormDefault='qualified' targetNamespace='http://schemas.microsoft.com/Message' xmlns:xs='http://www.w3.org/2001/XMLSchema' xmlns:tns='http://schemas.microsoft.com/Message'>  
\<xs:annotation>  
\<xs:appinfo>  
\<fileNameHint xmlns='http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd'>Stream</fileNameHint>  
\</xs:appinfo>  
\</xs:annotation>  
\<xs:simpleType name='StreamBody'>  
\<xs:restriction base='xs:base64Binary' />  
\</xs:simpleType>  
\</xs:schema>  
  
```  
  
> [!NOTE]
>  既定値の`DefaultXsdFileNamePrefix`バインディングの名前を指定します。 別の値を指定するには、オーバーライド`DefaultXsdFileNamePrefix`から派生するアダプター クラスに`Microsoft.ServiceModel.Channels.Common.AdapterBinding`です。  
  
 2 つの可能なメソッドを追加する、`fileNameHint`スキーマに注釈を: エクスポートを上書きしています.スキーマ メソッド OperationMetadata\TypeMetadata またはアダプターの IWsdlRetrieval 実装をオーバーライドします。 いずれかの方法は、基本実装を呼び出すし、スキーマ コレクション内のスキーマに注釈を追加します。  
  
> [!NOTE]
>  エクスポートをオーバーライドする場合.スキーマ メソッド、同じスキーマに複数の操作/型定義がある可能性がありますアダプターはことを確認の複数の発生、`fileNameHints`同じスキーマで注釈の競合は発生しません。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]最初に見つかった位置を使用して`fileNameHint`スキーマ内で複数回に発生する場合。  
  
 次の例では、IWsdlRetrieval を使用に追加されて、`fileNameHint`に WSDL 注釈。  
  
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
 アダプターはのみに設定する必要があります、 **AdapterEnvironmentSettings**、 **ConnectionPoolManager**、**接続プール**、および**CommonCacheSize**アダプターの初期化中にし、実行中のインスタンスの値を変更しないでください。  
  
 これらの設定は、現在実行中のアダプター インスタンスで変更が場合、これが原因で接続を現在実行中の構成設定を上書きして新しい接続。  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して、開発のベスト プラクティス](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)