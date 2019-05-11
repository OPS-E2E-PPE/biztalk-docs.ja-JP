---
title: パイプライン インターフェイスの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb88d0d-23ab-4fdb-bcd2-56050456cf69
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9d76df29720f33d8c7433bc34f9be239cfee0a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395399"
---
# <a name="using-pipeline-interfaces"></a>パイプライン インターフェイスの使用
パイプライン コンポーネントは、BizTalk メッセージング エンジンと対話するための定義済みのインターフェイスのセットを実装する .NET または COM コンポーネントです。 コンポーネントの機能、に応じて異なるインターフェイスを実装しなければなりません。 このトピックでは、これらのインターフェイスとそのメソッドの一部について説明します。  
  
> [!WARNING]
>  COM を使用して、カスタム パイプライン コンポーネントを構築する場合は、マルチ スレッド アパートメント (MTA) モデルを使用するコンポーネントを構成する必要があります。 そうでない場合、コンポーネントの呼び出しは E_NOINTERFACE エラーで失敗します。  
  
## <a name="ipipelinecontext"></a>IPipelineContext  
 すべてのパイプライン コンポーネントで使用できる**IPipelineContext**ドキュメント処理に固有のすべてのインターフェイスにアクセスするメソッド。 **IPipelineContext**インターフェイスは、次の機能を提供します。  
  
-   アンビエント パイプラインとステージの設定を取得するコンポーネントを使用します。  
  
-   メッセージとメッセージ ファクトリを取得するコンポーネントを使用します。 これらのファクトリでは、コンポーネントは、コンポーネントの実行に必要なさまざまなオブジェクトを作成できます。  
  
-   ドキュメント仕様を取得するコンポーネントを使用します。 ドキュメント仕様とは、XSD スキーマと注釈を追加します。  
  
## <a name="ibasecomponent"></a>IBaseComponent  
 すべてのパイプライン コンポーネントは、コンポーネントに関する基本的な情報を提供するには、このインターフェイスを実装する必要があります。  
  
## <a name="icomponent"></a>IComponent  
 すべてのパイプライン コンポーネントはアセンブラーを除くと、逆アセンブラーからのメッセージを取得するには、このインターフェイスを実装する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理エンジンし、エンジンに渡す処理されたメッセージを返します。  
  
 **実行します。** 入力メッセージをコンポーネントに渡すし、コンポーネントから処理済みのメッセージを取得する、エンジンによって呼び出されたメソッド。  
  
## <a name="ipropertybag-ipersistpropertybag"></a>IPropertyBag、IPersistPropertyBag  
 パイプライン コンポーネントを実装する必要があります**IPersistPropertyBag**その構成情報を受信します。 このインターフェイスと**IPropertyBag**は標準的なインターフェイスです。 これらのインターフェイスの詳細については、Microsoft .NET Framework ソフトウェア開発キット (SDK) ドキュメントを参照してください。  
  
## <a name="idisassemblercomponent"></a>IDisassemblerComponent  
 逆アセンブラー コンポーネントは、入力に 1 つのメッセージを受信し、出力で、0 個以上のメッセージが生成するパイプライン コンポーネントです。 逆アセンブラー コンポーネントは、個別のドキュメントにメッセージのインターチェンジの分割に使用されます。 逆アセンブラー コンポーネントのメソッドを実装する必要があります、 **IDisassemblerComponent**からのメッセージを取得するインターフェイス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にドキュメントがバックアップ処理のため、逆アセンブルした[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
|方法|説明|  
|------------|-----------------|  
|**逆アセンブルします。**|受信ドキュメントの逆アセンブルを実行します。 **pInMsg**します。|  
|**GetNext**|逆アセンブラーを実行して生成されたメッセージ セットから次のメッセージを取得します。 返します**NULL**以上メッセージがある場合。|  
  
 回復可能なインターチェンジ処理をサポートする逆アセンブラー コンポーネントを作成する場合は、次の操作を行う必要があります。  
  
1.  VirtualStream() でラップすることによって、シーク可能な入力ストリームを行います。  
  
2.  GetNext() でメッセージが不適切な場合を判断するロジックがあります。 メッセージが不良に設定して、BTS の場合は。MessageDestination ="SuspendQueue"と GetNext() でメッセージを返します。  
  
3.  メッセージが適切に設定 BTS の場合は。SuspendMessageOnRoutingFailure = True と GetNext() でメッセージを返します。  
  
## <a name="iassemblercomponent"></a>IAssemblerComponent  
 アセンブラー コンポーネントは、パイプライン コンポーネントの入力に複数のメッセージを受信し、出力の 1 つのメッセージが生成されます。 アセンブラー コンポーネントは、メッセージのインターチェンジ バッチに個々 のドキュメントを収集するために使用されます。  
  
> [!NOTE]
>  このリリースで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、アセンブル機能が使用されないため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]常に 1 つのドキュメントをコンポーネントの入力に渡します。  
  
 アセンブラー コンポーネントを実装して、 **IAssemblerComponent**メソッドによって呼び出される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時にエンジン。  
  
|方法|説明|  
|------------|-----------------|  
|**AddDocument**|ドキュメントを追加します**pInMsg**インターチェンジに含まれるメッセージの一覧にします。|  
|**アセンブル**|前のメソッドによって追加されたメッセージからインターチェンジを構築します。 アセンブルされたメッセージへのポインターを返します。|  
  
## <a name="iprobemessage"></a>IProbeMessage  
 任意のパイプライン コンポーネント (全般、アセンブル、または逆アセンブル) を実装できます**IProbeMessage**メッセージ プローブ機能が必要な場合。 プローブ コンポーネントがされているパイプライン ステージで使用される**FirstMatch**実行モード。 、このような段階的に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントへのメッセージを提供し、**プローブ**メソッドは、コンポーネントのかどうか、メッセージの形式を認識を確認するメッセージの先頭を検査します。  
  
|方法|説明|  
|------------|-----------------|  
|**プローブ**|このメソッドは**pInMsg**メッセージ、および返します**True**形式が認識された場合または**False**それ以外の場合。|  
  
## <a name="inameditem"></a>INamedItem  
 これは、マネージ コードとアンマネージ コードからドキュメント スキーマにアクセスするためのヘルパー インターフェイスです。  
  
## <a name="inameditemlist"></a>INamedItemList  
 これは、マネージ コードとアンマネージ コードからドキュメント スキーマにアクセスするためのヘルパー インターフェイスです。  
  
## <a name="idocumentspec"></a>IDocumentSpec  
 パイプライン コンポーネントのメソッドを使用できる、 **IDocumentSpec**し、コンテンツのプロパティをコンテキストと、ドキュメント スキーマへのアクセスに移動するなどのドキュメントに固有の操作を実行するためのインターフェイスします。  
  
|方法|説明|  
|------------|-----------------|  
|**DocType**|現在のドキュメントの種類を返します。|  
|**しない docspecname を含む**|現在のドキュメントの仕様の名前を返します。|  
|**GetSchemaCollection**|現在のドキュメントのドキュメント スキーマの一覧を返します。|  
|**GetBodyPath**|ボディ部が開始されるドキュメント内のノードに、XPath を返します。|  
|**GetDistinguishedPropertyAnnotationEnumerator**|すべての識別フィールド プロパティ注釈のディクショナリ列挙子を返します。|  
|**GetPropertyAnnotationEnumerator**|すべてのプロパティ注釈の列挙子を返します。|  
  
## <a name="icomponentui"></a>IComponentUI  
 パイプライン コンポーネントは、パイプライン デザイナー環境で使用するには、このインターフェイスを実装する必要があります。  
  
|方法|説明|  
|------------|-----------------|  
|**アイコン**|このコンポーネントに関連付けられているアイコンを提供します。|  
|**[検証]**|パイプライン デザイナーでは、すべての構成プロパティが正しく設定されていることを確認するパイプラインのコンパイル前にこのメソッドを呼び出します。|  
  
 **アイコン**プロパティが返す、 **IntPtr**します。 次C#を返す方法を示します、 **IntPtr**します。  
  
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
  
 詳細については、次を参照してください。 **IComponentUI インターフェイス (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 
  
## <a name="see-also"></a>参照  
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)   
 [CustomComponent (BizTalk Server サンプル)](../core/customcomponent-biztalk-server-sample.md)