---
title: "パイプライン インターフェイスを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bb88d0d-23ab-4fdb-bcd2-56050456cf69
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c365a8d7bdf37564d3d9b2dceac1c8615e126ebc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-pipeline-interfaces"></a>パイプライン インターフェイスを使用します。
パイプライン コンポーネントは、BizTalk メッセージング エンジンとの対話用にあらかじめ定義された一連のインターフェイスを実装する .NET コンポーネントまたは COM コンポーネントです。 実装する必要のあるインターフェイスは、コンポーネントの機能によって異なります。 このトピックでは、これらのインターフェイスとそのメソッドの一部について説明します。  
  
> [!WARNING]
>  COM を使用してカスタム パイプライン コンポーネントを作成する場合は、マルチスレッド アパートメント (MTA) モデルを使用するようにコンポーネントを構成する必要があります。 この構成を行わないと、コンポーネントの呼び出しは失敗し、E_NOINTERFACE エラーが返されます。  
  
## <a name="ipipelinecontext"></a>IPipelineContext  
 すべてのパイプライン コンポーネントで使用できる**IPipelineContext**ドキュメント処理に固有のすべてのインターフェイスにアクセスするメソッド。 **IPipelineContext**インターフェイスには、次の機能が用意されています。  
  
-   アンビエント パイプラインとステージの設定をコンポーネントで取得できるようにします。  
  
-   メッセージとメッセージ ファクトリをコンポーネントで取得できるようにします。 コンポーネントでこれらのファクトリを使用することにより、コンポーネントの実行に必要なさまざまなオブジェクトを作成することができます。  
  
-   ドキュメント仕様をコンポーネントで取得できるようにします。 ドキュメント仕様とは、XSD スキーマに注釈を加えたものを指します。  
  
## <a name="ibasecomponent"></a>IBaseComponent  
 コンポーネントの基本情報を指定するために、すべてのパイプライン コンポーネントに実装する必要のあるインターフェイスです。  
  
## <a name="icomponent"></a>IComponent  
 処理するメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンから取得し、処理されたメッセージをエンジンに返すために、アセンブラーと逆アセンブラーを除くすべてのパイプライン コンポーネントに実装されるインターフェイスです。  
  
 **実行します。** 入力メッセージをコンポーネントに渡し、処理されたメッセージをコンポーネントから取得するために、エンジンによって呼び出されるメソッドです。  
  
## <a name="ipropertybag-ipersistpropertybag"></a>IPropertyBag、IPersistPropertyBag  
 パイプライン コンポーネントを実装する必要があります**IPersistPropertyBag**その構成情報を受信します。 このインターフェイスと**IPropertyBag**は標準のインターフェイスです。 これらのインターフェイスの詳細については、Microsoft .NET Framework ソフトウェア開発キット (SDK) のドキュメントを参照してください。  
  
## <a name="idisassemblercomponent"></a>IDisassemblerComponent  
 逆アセンブラー コンポーネントは、入力時に 1 通のメッセージを受け取り、出力時に 0 通以上のメッセージを生成するパイプライン コンポーネントです。 逆アセンブラー コンポーネントは、メッセージのインターチェンジを個別のドキュメントに分割するために使用されます。 逆アセンブラー コンポーネントのメソッドを実装する必要があります、 **IDisassemblerComponent**からのメッセージを取得するインターフェイス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理との逆アセンブルしたドキュメント バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
|方法|Description|  
|------------|-----------------|  
|**逆アセンブルします。**|受信ドキュメントの逆アセンブルを実行**pInMsg**です。|  
|**GetNext**|逆アセンブラーを実行して生成されたメッセージ セットから次のメッセージを取得します。 返します**NULL**これ以上メッセージがある場合。|  
  
 回復可能なインターチェンジ処理をサポートする逆アセンブラー コンポーネントを記述する場合は、次の作業を行う必要があります。  
  
1.  入力ストリームを VirtualStream() でラップすることによって、シークできるようにします。  
  
2.  GetNext() 内に、メッセージに問題があるかどうかを判断するロジックを記述します。 メッセージに問題がある場合は、BTS.MessageDestination = "SuspendQueue" と設定して GetNext() でそのメッセージを返します。  
  
3.  メッセージに問題がない場合は、BTS.SuspendMessageOnRoutingFailure = True と設定して GetNext() でメッセージを返します。  
  
## <a name="iassemblercomponent"></a>IAssemblerComponent  
 アセンブラー コンポーネントは、入力時に複数のメッセージを受け取り、出力時に 1 通のメッセージを生成するパイプライン コンポーネントです。 アセンブラー コンポーネントは、個別のドキュメントをまとめてメッセージ インターチェンジのバッチを作成するために使用されます。  
  
> [!NOTE]
>  このリリースの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではアセンブル機能は使用されていないため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は常に 1 つのドキュメントをコンポーネントの入力として渡します。  
  
 アセンブラー コンポーネントを実装して、 **IAssemblerComponent**メソッドによって呼び出される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時にエンジンです。  
  
|方法|Description|  
|------------|-----------------|  
|**AddDocument**|ドキュメントに追加**pInMsg**インターチェンジに含まれるメッセージの一覧にします。|  
|**アセンブル**|前のメソッドによって追加されたメッセージからインターチェンジを構築します。 アセンブルされたメッセージへのポインターを返します。|  
  
## <a name="iprobemessage"></a>IProbeMessage  
 任意のパイプライン コンポーネント (全般、アセンブル、または逆アセンブル) を実装できます**IProbeMessage**メッセージ プローブ機能が必要とする場合。 プローブ コンポーネントはされているパイプライン ステージで使用**FirstMatch**実行モードです。 、このような段階的に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントへのメッセージを提供し、**プローブ**メソッドは、コンポーネントにメッセージの形式が認識されるかどうかを決定するメッセージの先頭を検査します。  
  
|方法|Description|  
|------------|-----------------|  
|**プローブ**|このメソッドは、 **pInMsg**メッセージ、および返します**True**形式が認識された場合または**False**それ以外の場合。|  
  
## <a name="inameditem"></a>INamedItem  
 マネージ コードおよびアンマネージ コードからドキュメント スキーマにアクセスするためのヘルパー インターフェイスです。  
  
## <a name="inameditemlist"></a>INamedItemList  
 マネージ コードおよびアンマネージ コードからドキュメント スキーマにアクセスするためのヘルパー インターフェイスです。  
  
## <a name="idocumentspec"></a>IDocumentSpec  
 パイプライン コンポーネントのメソッドを使用できる、 **IDocumentSpec**コンテキストと、ドキュメント スキーマにアクセスするコンテンツのプロパティの移動など、ドキュメントに固有の操作を実行するためのインターフェイスし、などです。  
  
|方法|Description|  
|------------|-----------------|  
|**DocType**|現在のドキュメントの型を返します。|  
|**DocSpecName**|現在のドキュメントの仕様名を返します。|  
|**GetSchemaCollection**|現在のドキュメントのドキュメント スキーマの一覧を返します。|  
|**GetBodyPath**|ボディ部が開始されるドキュメント内ノードへの XPath を返します。|  
|**GetDistinguishedPropertyAnnotationEnumerator**|すべての識別フィールド プロパティ注釈のディクショナリ列挙子を返します。|  
|**GetPropertyAnnotationEnumerator**|すべてのプロパティ注釈の列挙子を返します。|  
  
## <a name="icomponentui"></a>IComponentUI  
 パイプライン コンポーネントをパイプライン デザイナー環境で使用できるようにするには、このインターフェイスを実装する必要があります。  
  
|方法|Description|  
|------------|-----------------|  
|**アイコン**|このコンポーネントに関連付けられたアイコンを指定します。|  
|**[検証]**|パイプライン デザイナーは、パイプラインのコンパイル前にこのメソッドを呼び出して、すべての構成プロパティが正しく設定されていることを確認します。|  
  
 **アイコン**プロパティから返される、 **IntPtr**です。 次の c# の例を返す方法を示しています、 **IntPtr**です。  
  
```csharp  
static   ResourceManager resManager = new ResourceManager("ResourceManager", Assembly.GetExecutingAssembly());  
...  
[Browsable(false)]  
public IntPtr Icon  
{  
   get  
   {  
      return ((Bitmap)resManager.GetObject("MyIcon")).GetHicon();  
   }  
}  
```  
  
 詳細については、次を参照してください。 **IComponentUI インターフェイス (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 
  
## <a name="see-also"></a>参照  
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)   
 [CustomComponent (BizTalk Server サンプル)](../core/customcomponent-biztalk-server-sample.md)