---
title: '手順 3: エコー アダプターの接続の実装 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc223901-3ad3-4e71-8672-fea6bb4efe65
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15749fdca84508654fc915fff0c1abe7008de2f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988411"
---
# <a name="step-3-implement-the-connection-for-the-echo-adapter"></a><span data-ttu-id="08a14-102">手順 3: エコー アダプターの接続を実装します。</span><span class="sxs-lookup"><span data-stu-id="08a14-102">Step 3: Implement the Connection for the Echo Adapter</span></span>
<span data-ttu-id="08a14-103">![手順 9 の 3](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span><span class="sxs-lookup"><span data-stu-id="08a14-103">![Step 3 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span></span>  

 <span data-ttu-id="08a14-104">**所要時間:** 45 分</span><span class="sxs-lookup"><span data-stu-id="08a14-104">**Time to complete:** 45 minutes</span></span>  

 <span data-ttu-id="08a14-105">この手順では、エコー アダプターの接続機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="08a14-105">In this step, you implement the connection capability of the Echo adapter.</span></span> <span data-ttu-id="08a14-106">に従って、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、ターゲット システムに接続するときに、次の抽象クラスとインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08a14-106">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], you must implement the following abstract class and interfaces when connecting to the target system.</span></span>  

- `Microsoft.ServiceModel.Channels.Common.ConnectionUri`  

- `Microsoft.ServiceModel.Channels.Common.IConnection`  

- `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`  

  <span data-ttu-id="08a14-107">上記からの派生ではなく抽象クラスとインターフェイスを[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]3 つの派生クラス、EchoAdapterConnection、EchoAdapterConnectionUri、および EchoAdapterConnectionFactory を自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="08a14-107">Instead of deriving from the above abstract class and interfaces, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the three derived classes, EchoAdapterConnection, EchoAdapterConnectionUri, and EchoAdapterConnectionFactory.</span></span> <span data-ttu-id="08a14-108">特定の例外をスローします。 既定のメソッドは、クラスを作成するだけでなく`System.NotImplementedException`します。</span><span class="sxs-lookup"><span data-stu-id="08a14-108">In addition to creating the classes, each has a default method that throws a specific exception, `System.NotImplementedException`.</span></span>  <span data-ttu-id="08a14-109">このステートメントは、開発者は、各クラスを実装するよう通知します。</span><span class="sxs-lookup"><span data-stu-id="08a14-109">This statement reminds the developer to implement each class.</span></span>  <span data-ttu-id="08a14-110">クラスが実装された場合、この例外のスロー ステートメントを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08a14-110">When the class is implemented, this exception-throwing statement must be removed.</span></span>  

  <span data-ttu-id="08a14-111">次のセクションでは、接続を処理する方法、URI の構造は URI のさまざまな要素をプログラムで取得し、アダプター内での要素を使用する方法の理解を深めるためにこれら 3 つのクラスを更新します。</span><span class="sxs-lookup"><span data-stu-id="08a14-111">In the following section, you update those three classes to get a better understanding of how to handle a connection, what the URI structure is, and how to programmatically retrieve various URI elements and then use those elements within the adapter.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="08a14-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="08a14-112">Prerequisites</span></span>  
 <span data-ttu-id="08a14-113">この手順を開始する前にする必要がありますが正常に完了して[手順 2: アダプターと接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="08a14-113">Before you begin this step, you must have successfully completed [Step 2: Categorize the Adapter and Connection Properties](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).</span></span> <span data-ttu-id="08a14-114">明確に理解しておくと、 `Microsoft.ServiceModel.Channels.Common.IConnection`、 `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`、および`Microsoft.ServiceModel.Channels.Common.ConnectionUri`クラス。</span><span class="sxs-lookup"><span data-stu-id="08a14-114">And you should have a clear understanding of the `Microsoft.ServiceModel.Channels.Common.IConnection`, `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`, and `Microsoft.ServiceModel.Channels.Common.ConnectionUri` classes.</span></span>  

## <a name="connection-related-classes"></a><span data-ttu-id="08a14-115">接続に関連するクラス</span><span class="sxs-lookup"><span data-stu-id="08a14-115">Connection-Related Classes</span></span>  
 <span data-ttu-id="08a14-116">[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] 3 つの派生クラス、EchoAdapterConnection、EchoAdapterConnectionUri、および EchoAdapterConnectionFactory が生成されます。</span><span class="sxs-lookup"><span data-stu-id="08a14-116">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] generates three derived classes, EchoAdapterConnection, EchoAdapterConnectionUri, and EchoAdapterConnectionFactory.</span></span> <span data-ttu-id="08a14-117">関連付けられた各メソッドの簡単な概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="08a14-117">The following provides a brief overview of methods associated with each.</span></span>  

### <a name="echoadapterconnection"></a><span data-ttu-id="08a14-118">EchoAdapterConnection</span><span class="sxs-lookup"><span data-stu-id="08a14-118">EchoAdapterConnection</span></span>  
 <span data-ttu-id="08a14-119">アダプターの複雑さによっては、次の 5 つのメソッドをすべて実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08a14-119">Depending on your adapter complexity, you might need to implement all of the following five methods.</span></span> <span data-ttu-id="08a14-120">エコー アダプターのほとんどはサポートされていません、エコー アダプターのサンプルが他のシステムが含まれないためです。</span><span class="sxs-lookup"><span data-stu-id="08a14-120">For Echo adapter, most are not supported, because the Echo adapter sample does not involve any target system.</span></span>  

|<span data-ttu-id="08a14-121">**方法**</span><span class="sxs-lookup"><span data-stu-id="08a14-121">**Method**</span></span>|<span data-ttu-id="08a14-122">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="08a14-122">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="08a14-123">public void 閉じる (TimeSpan タイムアウト)</span><span class="sxs-lookup"><span data-stu-id="08a14-123">public void Close(TimeSpan timeout)</span></span>|<span data-ttu-id="08a14-124">ターゲット システムへの接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="08a14-124">Closes the connection to the target system.</span></span> <span data-ttu-id="08a14-125">エコー アダプターでは、このメソッドを使用して、トレース イベントをトレース リスナーにのみ追加します。</span><span class="sxs-lookup"><span data-stu-id="08a14-125">The Echo adapter uses this method to only add trace events to the trace listener.</span></span>|  
|<span data-ttu-id="08a14-126">public bool IsValid (TimeSpan タイムアウト)</span><span class="sxs-lookup"><span data-stu-id="08a14-126">public bool IsValid(TimeSpan timeout)</span></span>|<span data-ttu-id="08a14-127">接続がまだ有効かどうかを示す値を返します。</span><span class="sxs-lookup"><span data-stu-id="08a14-127">Returns a value indicating whether the connection is still valid.</span></span><br /><br /> <span data-ttu-id="08a14-128">エコー アダプターによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="08a14-128">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="08a14-129">public void オープン (TimeSpan タイムアウト)</span><span class="sxs-lookup"><span data-stu-id="08a14-129">public void Open(TimeSpan timeout)</span></span>|<span data-ttu-id="08a14-130">ターゲット システムへの接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="08a14-130">Opens the connection to the target system.</span></span><br /><br /> <span data-ttu-id="08a14-131">エコー アダプターの該当なし。</span><span class="sxs-lookup"><span data-stu-id="08a14-131">N/A for the Echo adapter.</span></span> <span data-ttu-id="08a14-132">しかし、例を示します enableAuthentication と呼ばれる URI の要素を使用して、ユーザーのユーザー名を指定する必要がある方法。</span><span class="sxs-lookup"><span data-stu-id="08a14-132">However, the example shows you how to use a URI element called enableAuthentication to require users to provide a user name.</span></span>|  
|<span data-ttu-id="08a14-133">public void ClearContext()</span><span class="sxs-lookup"><span data-stu-id="08a14-133">public void ClearContext()</span></span>|<span data-ttu-id="08a14-134">接続のコンテキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="08a14-134">Clears the context of the connection.</span></span> <span data-ttu-id="08a14-135">接続が戻り、接続プールに設定されている場合は、このメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="08a14-135">This method is called when the connection is set back to the connection pool.</span></span><br /><br /> <span data-ttu-id="08a14-136">エコー アダプターによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="08a14-136">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="08a14-137">public void Abort()</span><span class="sxs-lookup"><span data-stu-id="08a14-137">public void Abort()</span></span>|<span data-ttu-id="08a14-138">ターゲット システムへの接続を中止します。</span><span class="sxs-lookup"><span data-stu-id="08a14-138">Aborts the connection to the target system.</span></span><br /><br /> <span data-ttu-id="08a14-139">エコー アダプターによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="08a14-139">Not supported by the Echo adapter.</span></span>|  

### <a name="echoadapterconnectionfactory"></a><span data-ttu-id="08a14-140">EchoAdapterConnectionFactory</span><span class="sxs-lookup"><span data-stu-id="08a14-140">EchoAdapterConnectionFactory</span></span>  
 <span data-ttu-id="08a14-141">接続ファクトリは、接続を作成する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="08a14-141">The connection factory is responsible for creating the connection.</span></span> <span data-ttu-id="08a14-142">既定では、ターゲット システムに接続するときにのみ、このクラスを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08a14-142">By default, you must modify this class only when connecting to a target system.</span></span> <span data-ttu-id="08a14-143">エコー アダプターは、他のシステムを含まないが方法を示します、接続がユーザー認証が必要な場合に enableAuthentication と呼ばれるカスタム URI 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="08a14-143">Although the Echo adapter does not involve any target system, it shows you how to use a custom URI element called enableAuthentication if your connection requires user authentication.</span></span>  

> [!NOTE]
>  <span data-ttu-id="08a14-144">EnableAuthentication は、キーワードではありませんが、変数名にすぎません。</span><span class="sxs-lookup"><span data-stu-id="08a14-144">The enableAuthentication is not a keyword, it is just a variable name.</span></span> <span data-ttu-id="08a14-145">そのため、これは任意の名前を選択できます。</span><span class="sxs-lookup"><span data-stu-id="08a14-145">Hence, you can choose any name for it.</span></span>  

### <a name="echoadapterconnectionuri"></a><span data-ttu-id="08a14-146">EchoAdapterConnectionUri</span><span class="sxs-lookup"><span data-stu-id="08a14-146">EchoAdapterConnectionUri</span></span>  
 <span data-ttu-id="08a14-147">これは、ターゲット システムに接続文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="08a14-147">This represents a connection string to the target system.</span></span>  


|               <span data-ttu-id="08a14-148">**方法**</span><span class="sxs-lookup"><span data-stu-id="08a14-148">**Method**</span></span>               |                                                                                                                                       <span data-ttu-id="08a14-149">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="08a14-149">**Description**</span></span>                                                                                                                                        |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        <span data-ttu-id="08a14-150">パブリック オーバーライドの Uri の Uri</span><span class="sxs-lookup"><span data-stu-id="08a14-150">public override Uri Uri</span></span>         |                                                                                                    <span data-ttu-id="08a14-151">取得し、Uri を設定します。</span><span class="sxs-lookup"><span data-stu-id="08a14-151">Gets and sets the Uri.</span></span> <span data-ttu-id="08a14-152">Uri 文字列を作成するを取得し、Uri 文字列の解析を設定します。</span><span class="sxs-lookup"><span data-stu-id="08a14-152">Gets to build the Uri string and sets to parse the Uri string.</span></span>                                                                                                     |
|   <span data-ttu-id="08a14-153">パブリック EchoAdapterConnectionUri()</span><span class="sxs-lookup"><span data-stu-id="08a14-153">public EchoAdapterConnectionUri()</span></span>    |                                                                                                                    <span data-ttu-id="08a14-154">ConnectionUri クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="08a14-154">Initializes a new instance of the ConnectionUri class.</span></span>                                                                                                                    |
| <span data-ttu-id="08a14-155">パブリック オーバーライド文字列 SampleUriString</span><span class="sxs-lookup"><span data-stu-id="08a14-155">public override string SampleUriString</span></span> | <span data-ttu-id="08a14-156">Returns EchoAdapter.SCHEME + "://{hostname}/{application}?enableAuthentication={True&#124;False}".</span><span class="sxs-lookup"><span data-stu-id="08a14-156">Returns EchoAdapter.SCHEME + "://{hostname}/{application}?enableAuthentication={True&#124;False}".</span></span><br /><br /> <span data-ttu-id="08a14-157">としてこの戻り値の文字列が表示されます、**例**で、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="08a14-157">This return string displays as the **Example** in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, as shown in the following figure.</span></span> |

 <span data-ttu-id="08a14-158">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")</span><span class="sxs-lookup"><span data-stu-id="08a14-158">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")</span></span>  

## <a name="echo-adapter-connection-uri"></a><span data-ttu-id="08a14-159">エコー アダプターの接続 URI</span><span class="sxs-lookup"><span data-stu-id="08a14-159">Echo Adapter Connection URI</span></span>  
 <span data-ttu-id="08a14-160">サンプルのエコー アダプターの接続 URI のとおりです: EchoAapter.SCHEME://{hostname}/{application}?enableAuthentication={true&#124;false}</span><span class="sxs-lookup"><span data-stu-id="08a14-160">The sample Echo adapter connection URI is described as: EchoAapter.SCHEME://{hostname}/{application}?enableAuthentication={true&#124;false}</span></span>  

 <span data-ttu-id="08a14-161">EchoAapter.SCHEME echov2 であるため、接続 URI です。</span><span class="sxs-lookup"><span data-stu-id="08a14-161">Since the EchoAapter.SCHEME is echov2, the connection URI is:</span></span>  

 <span data-ttu-id="08a14-162">echo2://lobhostname/lobapplication?enableAuthentication={true&#124;false}</span><span class="sxs-lookup"><span data-stu-id="08a14-162">echo2://lobhostname/lobapplication?enableAuthentication={true&#124;false}</span></span>  

 <span data-ttu-id="08a14-163">前の接続 URI を読み取ることができる場合 enableAuthentication false を次のように =。</span><span class="sxs-lookup"><span data-stu-id="08a14-163">You can read the previous connection URI when enableAuthentication=false as follows:</span></span>  

 <span data-ttu-id="08a14-164">Echov2 トランスポートのスキーマを使用して、移動 lobhostname、という名前のコンピューターに接続の任意の認証を必要としない lobapplication をという名前のアプリケーションが待機しています。</span><span class="sxs-lookup"><span data-stu-id="08a14-164">Using the echov2 transport schema, go to a computer named lobhostname, where an application named lobapplication that does not require any authentication is waiting for your connection.</span></span>  

 <span data-ttu-id="08a14-165">または、enableAuthentication = true の場合、次のように、接続の読み取り。</span><span class="sxs-lookup"><span data-stu-id="08a14-165">Or, when enableAuthentication=true, read the connection as follows:</span></span>  

 <span data-ttu-id="08a14-166">Echov2 トランスポートのスキーマを使用して、移動 lobhostname、という名前のコンピューターで、lobapplication をという名前のアプリケーションでは、接続が認証を待機しているが必要です。</span><span class="sxs-lookup"><span data-stu-id="08a14-166">Using the echov2 transport schema, go to a computer named lobhostname, where an application named lobapplication expects that authentication is waiting for your connection.</span></span> <span data-ttu-id="08a14-167">エコー アダプターの場合は、ユーザー名のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="08a14-167">For the Echo adapter, only a user name is required.</span></span>  

 <span data-ttu-id="08a14-168">定義済みの URI を持つプログラムで使用し、接続および構成の解析できます。</span><span class="sxs-lookup"><span data-stu-id="08a14-168">With a defined URI, you can programmatically consume and parse it for connectivity and configuration.</span></span> <span data-ttu-id="08a14-169">接続には、ユーザー名とパスワードなどの機密データが必要とする場合は、URI では、このような情報は含まれません。</span><span class="sxs-lookup"><span data-stu-id="08a14-169">If the connection requires sensitive data such as a user name and password, do not contain such information in the URI.</span></span> <span data-ttu-id="08a14-170">代わりに、このような情報を追加、`System.ServiceModel.Description.ClientCredentials`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="08a14-170">Instead, add such information in the `System.ServiceModel.Description.ClientCredentials` object.</span></span> <span data-ttu-id="08a14-171">追加するコード例では、操作を行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="08a14-171">The code example that you add shows you how to do so.</span></span>  

 <span data-ttu-id="08a14-172">次のコードでは、エコー アダプターは、アダプターが URI のさまざまな要素を使用して、アダプターの機能を変更する方法を説明する 2 つの方法で URI を構築します。</span><span class="sxs-lookup"><span data-stu-id="08a14-172">In the following code, the Echo adapter constructs the URI in two ways to show you how the adapter can use various URI elements to modify the adapter feature.</span></span>  

 <span data-ttu-id="08a14-173">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]</span><span class="sxs-lookup"><span data-stu-id="08a14-173">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]</span></span>  

 <span data-ttu-id="08a14-174">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]&echoInUpperCase=true</span><span class="sxs-lookup"><span data-stu-id="08a14-174">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]&echoInUpperCase=true</span></span>  

### <a name="retrieving-the-uri-element"></a><span data-ttu-id="08a14-175">URI の要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="08a14-175">Retrieving the URI Element</span></span>  
 <span data-ttu-id="08a14-176">エコー アダプター URI echo2 内の各 URI 要素を解析することができます://lobhostname/lobapplication? enableAuthentication = false & echoInUpperCase = false。</span><span class="sxs-lookup"><span data-stu-id="08a14-176">You can parse each URI element in the Echo adapter URI echo2://lobhostname/lobapplication?enableAuthentication=false&echoInUpperCase=false.</span></span>  <span data-ttu-id="08a14-177">URI の要素の値と関連付けられているメソッドは、次の表のとおりです。</span><span class="sxs-lookup"><span data-stu-id="08a14-177">The URI element values and associated methods are listed in the following table:</span></span>  

|<span data-ttu-id="08a14-178">**URI の要素の値**</span><span class="sxs-lookup"><span data-stu-id="08a14-178">**URI Element Value**</span></span>|<span data-ttu-id="08a14-179">**方法**</span><span class="sxs-lookup"><span data-stu-id="08a14-179">**Method**</span></span>|  
|---------------------------|----------------|  
|<span data-ttu-id="08a14-180">lobhostname</span><span class="sxs-lookup"><span data-stu-id="08a14-180">lobhostname</span></span>|<span data-ttu-id="08a14-181">`System.Uri.Host%2A` ホスト名を取得するには</span><span class="sxs-lookup"><span data-stu-id="08a14-181">`System.Uri.Host%2A` to retrieve the host name</span></span>|  
|<span data-ttu-id="08a14-182">Lobapplication</span><span class="sxs-lookup"><span data-stu-id="08a14-182">Lobapplication</span></span>|<span data-ttu-id="08a14-183">`System.Uri.AbsolutePath%2A` ターゲット アプリケーションの名前を取得するには</span><span class="sxs-lookup"><span data-stu-id="08a14-183">`System.Uri.AbsolutePath%2A` to retrieve the target application name</span></span>|  
|<span data-ttu-id="08a14-184">enableAuthentation = false</span><span class="sxs-lookup"><span data-stu-id="08a14-184">enableAuthentation=false</span></span>|<span data-ttu-id="08a14-185">GetQueryStringValue("enableAuthentication")</span><span class="sxs-lookup"><span data-stu-id="08a14-185">GetQueryStringValue("enableAuthentication")</span></span><br /><br /> <span data-ttu-id="08a14-186">この URI の要素を使用して、ユーザーの資格情報を検証する**注:** GetQueryStringValue 静的メソッドで定義されているは、 `Microsoft.ServiceModel.Channels.Common.ConnectionUri`</span><span class="sxs-lookup"><span data-stu-id="08a14-186">Use this URI element to validate user credentials **Note:**  GetQueryStringValue is a static method defined in the `Microsoft.ServiceModel.Channels.Common.ConnectionUri`</span></span>|  
|<span data-ttu-id="08a14-187">echoInUpperValue=false</span><span class="sxs-lookup"><span data-stu-id="08a14-187">echoInUpperValue=false</span></span>|<span data-ttu-id="08a14-188">GetQueryStringValue("echoInUpperValue")</span><span class="sxs-lookup"><span data-stu-id="08a14-188">GetQueryStringValue("echoInUpperValue")</span></span><br /><br /> <span data-ttu-id="08a14-189">受信の文字列を大文字に変換するためには、この URI の要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="08a14-189">Use this URI element to convert the incoming string to upper case.</span></span>|  

### <a name="enableauthentication-uri-element"></a><span data-ttu-id="08a14-190">EnableAuthentication URI 要素</span><span class="sxs-lookup"><span data-stu-id="08a14-190">EnableAuthentication URI Element</span></span>  
 <span data-ttu-id="08a14-191">多くの場合、ターゲット システムでは、ターゲット システムへの接続を確立するためにクライアントの資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08a14-191">Your target system often requires you to provide client credentials to establish a connection to the target system.</span></span> <span data-ttu-id="08a14-192">前述のように、エコー アダプターは、他のシステムを関与しません。</span><span class="sxs-lookup"><span data-stu-id="08a14-192">As mentioned, the Echo adapter does not involve any target system.</span></span> <span data-ttu-id="08a14-193">サンプルとして、enableAuthentication と呼ばれるカスタム URI 要素を使用して、資格情報を提供する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="08a14-193">Though as a sample, it shows how to use a custom URI element called enableAuthentication to provide the credentials.</span></span>  

```  
 public class EchoAdapterConnection : IConnection   
{  
….  
   public void Open(TimeSpan timeout)  
  {  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
  }  
}  
```  

 <span data-ttu-id="08a14-194">EnableAuthentication が true の場合と、ユーザー名が提供されていない場合、コードを確認しますユーザー名が指定されていない場合でキャッチされた例外がスローされます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを次に示すよう。</span><span class="sxs-lookup"><span data-stu-id="08a14-194">The code checks to see if enableAuthentication is true and if a user name is not provided; if a user name is not provided, it throws an exception, which is caught by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, as shown below:</span></span>  

 <span data-ttu-id="08a14-195">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/901095c7-c70d-491a-a1ae-8f37f22a61a7.gif "901095c7-c70d-491a-a1ae-8f37f22a61a7")</span><span class="sxs-lookup"><span data-stu-id="08a14-195">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/901095c7-c70d-491a-a1ae-8f37f22a61a7.gif "901095c7-c70d-491a-a1ae-8f37f22a61a7")</span></span>  

 <span data-ttu-id="08a14-196">ユーザー名を指定する入力できますが、アダプターの構成 ダイアログ ボックスで、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="08a14-196">To provide the user name, you can enter it in the Configure Adapter dialog box in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, as shown in the following figure:</span></span>  

 <span data-ttu-id="08a14-197">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4069a7d-1403-4195-b0b5-21ad97dbc3ce.gif "e4069a7d-1403-4195-b0b5-21ad97dbc3ce")</span><span class="sxs-lookup"><span data-stu-id="08a14-197">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4069a7d-1403-4195-b0b5-21ad97dbc3ce.gif "e4069a7d-1403-4195-b0b5-21ad97dbc3ce")</span></span>  

### <a name="echoinuppercase-uri-element"></a><span data-ttu-id="08a14-198">EchoInUpperCase URI 要素</span><span class="sxs-lookup"><span data-stu-id="08a14-198">EchoInUpperCase URI Element</span></span>  
 <span data-ttu-id="08a14-199">EchoInUpperCase URI 要素は、ブール型のフラグのように参照できます。</span><span class="sxs-lookup"><span data-stu-id="08a14-199">The EchoInUpperCase URI element can be referenced like a Boolean flag.</span></span> <span data-ttu-id="08a14-200">フラグが true の場合、アダプター EchoStrings 操作の入力文字列を大文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="08a14-200">If the flag is true, then the adapter converts the input string of the EchoStrings operation to uppercase.</span></span>  

 <span data-ttu-id="08a14-201">EchoInUpperCase URI 要素の既定値を変更するには、アダプターでの構成の URI のプロパティ タブを使用、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]以下に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="08a14-201">To change the default value of the echoInUpperCase URI element, use the URI Properties tab of the Configure Adapter in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], as shown below.</span></span>  

 <span data-ttu-id="08a14-202">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f22511b2-3fca-4875-ac65-8e61f4367e94.gif "f22511b2-3fca-4875-ac65-8e61f4367e94")</span><span class="sxs-lookup"><span data-stu-id="08a14-202">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f22511b2-3fca-4875-ac65-8e61f4367e94.gif "f22511b2-3fca-4875-ac65-8e61f4367e94")</span></span>  

## <a name="updating-echoadapterconnection"></a><span data-ttu-id="08a14-203">EchoAdapterConnection を更新しています</span><span class="sxs-lookup"><span data-stu-id="08a14-203">Updating EchoAdapterConnection</span></span>  
 <span data-ttu-id="08a14-204">EchoAdapterConnection クラスの IsValid、Open、Close メソッドを実装するとします。</span><span class="sxs-lookup"><span data-stu-id="08a14-204">You implement the IsValid, Open, and Close method of the EchoAdapterConnection class.</span></span>  

#### <a name="to-update-the-echoadapterconnection-class"></a><span data-ttu-id="08a14-205">EchoAdapterConnection クラスを更新するには</span><span class="sxs-lookup"><span data-stu-id="08a14-205">To update the EchoAdapterConnection class</span></span>  

1.  <span data-ttu-id="08a14-206">**ソリューション エクスプ ローラー**、ダブルクリックして、 **EchoAdapterConnection.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="08a14-206">In **Solution Explorer**, double-click the **EchoAdapterConnection.cs** file.</span></span>  

2.  <span data-ttu-id="08a14-207">Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内をポイント**アウトライン**、 をクリックし、**アウトラインの中止**します。</span><span class="sxs-lookup"><span data-stu-id="08a14-207">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  

3.  <span data-ttu-id="08a14-208">Visual Studio エディターで検索、 **IsValid**メソッド。</span><span class="sxs-lookup"><span data-stu-id="08a14-208">In the Visual Studio editor, find the **IsValid** method.</span></span> <span data-ttu-id="08a14-209">内で、 **IsValid**メソッドでは、既存の実装を次に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="08a14-209">Inside the **IsValid** method, replace the existing implementation with the one below:</span></span>  

    ```csharp  
    return true;  
    ```  

4.  <span data-ttu-id="08a14-210">Visual Studio エディターで検索、**オープン**メソッド。</span><span class="sxs-lookup"><span data-stu-id="08a14-210">In the Visual Studio editor, find the **Open** method.</span></span> <span data-ttu-id="08a14-211">内で、**オープン**メソッドでは、既存の実装を次の実装に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="08a14-211">Inside the **Open** method, replace the existing implementation with the following implementation.</span></span> <span data-ttu-id="08a14-212">これは、URI enableAuthentication 要素を使用して、ユーザー名が提供されていることを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="08a14-212">This shows you how to use the URI enableAuthentication element to ensure user  name is provided:</span></span>  

    ```csharp  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        // it just logs the credentials in the trace file  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
        // got the username, log it in trace file  
        EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Username is " + this.connectionFactory.ClientCredentials.UserName.UserName);  
    }  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully established!");  
    ```  

5.  <span data-ttu-id="08a14-213">Visual Studio エディターで検索、**閉じる**メソッド。</span><span class="sxs-lookup"><span data-stu-id="08a14-213">In the Visual Studio editor, find the **Close** method.</span></span> <span data-ttu-id="08a14-214">内で、**閉じる**メソッドでは、次の 1 つのステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="08a14-214">Inside the **Close** method, add the following single statement:</span></span>  

    ```csharp  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Close", "Connection successfully closed!");  
    ```  

## <a name="updating-the-echoadapterconnectionfactory"></a><span data-ttu-id="08a14-215">EchoAdapterConnectionFactory を更新しています</span><span class="sxs-lookup"><span data-stu-id="08a14-215">Updating the EchoAdapterConnectionFactory</span></span>  
 <span data-ttu-id="08a14-216">EchoAdapterConnectionFactory コンストラクターを実装し、ClientCredentials、ConnectionUri という 2 つのプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="08a14-216">You implement EchoAdapterConnectionFactory constructor, and add two properties called ClientCredentials and ConnectionUri.</span></span>  

#### <a name="to-update-the-echoadapterconnectionfactory-class"></a><span data-ttu-id="08a14-217">EchoAdapterConnectionFactory クラスを更新するには</span><span class="sxs-lookup"><span data-stu-id="08a14-217">To update the EchoAdapterConnectionFactory class</span></span>  

1.  <span data-ttu-id="08a14-218">**ソリューション エクスプ ローラー**、ダブルクリックして、 **EchoAdapterConnectionFactory.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="08a14-218">In **Solution Explorer**, double-click the **EchoAdapterConnectionFactory.cs** file.</span></span>  

2.  <span data-ttu-id="08a14-219">Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内をポイント**アウトライン**、 をクリックし、**アウトラインの中止**します。</span><span class="sxs-lookup"><span data-stu-id="08a14-219">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  

3.  <span data-ttu-id="08a14-220">Visual Studio エディターで検索、**プライベート フィールド**リージョン。</span><span class="sxs-lookup"><span data-stu-id="08a14-220">In the Visual Studio editor, find the **Private Fields** region.</span></span> <span data-ttu-id="08a14-221">次の 1 つのステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="08a14-221">Add the following single statement:</span></span>  

    ```csharp  
    private EchoAdapterConnectionUri connectionUri;  
    ```  

     <span data-ttu-id="08a14-222">プライベート フィールドの一覧は、次と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08a14-222">Your list of private fields should match the following:</span></span>  

    ```csharp  
    // Stores the client credentials  
    private ClientCredentials clientCredentials;  
    // Stores the adapter class  
    private EchoAdapter adapter;  
    private EchoAdapterConnectionUri connectionUri;  
    ```  

4.  <span data-ttu-id="08a14-223">Visual Studio エディターで検索、 **EchoAdapterConnectionFactory**メソッド。</span><span class="sxs-lookup"><span data-stu-id="08a14-223">In the Visual Studio editor, find the **EchoAdapterConnectionFactory** method.</span></span> <span data-ttu-id="08a14-224">内で、 **EchoAdapterConnectionFactory**コンストラクターのメソッドの前に"}"、最後のステートメントとして次の 1 つのステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="08a14-224">Inside the **EchoAdapterConnectionFactory** constructor method, before "}", add the following single statement as the last statement.</span></span>  

    ```csharp  
    this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    ```  

     <span data-ttu-id="08a14-225">実装、 **EchoAdapterConnectionFactory**メソッドは、次と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08a14-225">The implementation of the **EchoAdapterConnectionFactory** method should match the following:</span></span>  

    ```csharp  
    /// <summary>  
    /// Initializes a new instance of the EchoAdapterConnectionFactory class  
    /// </summary>  
    public EchoAdapterConnectionFactory(ConnectionUri connectionUri  
        , ClientCredentials clientCredentials  
        , EchoAdapter adapter)  
    {  
        this.clientCredentials = clientCredentials;  
        this.adapter = adapter;  
        //added  
        this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    }  
    ```  

5.  <span data-ttu-id="08a14-226">Visual Studio エディターで検索、**パブリック プロパティ**リージョン。</span><span class="sxs-lookup"><span data-stu-id="08a14-226">In the Visual Studio editor, find the **Public Properties** region.</span></span> <span data-ttu-id="08a14-227">次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="08a14-227">Add the following code:</span></span>  

    ```csharp  
    /// <summary>  
    /// Returns the client credentials  
    /// </summary>  
    public ClientCredentials ClientCredentials  
    {  
        get  
        {  
            return this.clientCredentials;  
        }  
    }  

    /// <summary>  
    /// Returns the Connection Uri for this adapter  
    /// </summary>  
    public EchoAdapterConnectionUri ConnectionUri  
    {  
        get  
        {  
            return this.connectionUri;  
        }  
    }  
    ```  

## <a name="updating-the-echoadapterconnectionuri"></a><span data-ttu-id="08a14-228">EchoAdapterConnectionUri を更新しています</span><span class="sxs-lookup"><span data-stu-id="08a14-228">Updating the EchoAdapterConnectionUri</span></span>  
 <span data-ttu-id="08a14-229">EchoAdapterConnectionUri 既定のコンストラクターを実装して、EchoAdapterConnectionUri(Uri uri) コンストラクターをオーバー ロードされたパブリック Uri Uri プロパティをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="08a14-229">You implement the EchoAdapterConnectionUri default constructor, EchoAdapterConnectionUri(Uri uri) overloaded constructor, and the public override Uri Uri property.</span></span>  

#### <a name="to-update-the-echoadapterconnectionuri-class"></a><span data-ttu-id="08a14-230">EchoAdapterConnectionUri クラスを更新するには</span><span class="sxs-lookup"><span data-stu-id="08a14-230">To update the EchoAdapterConnectionUri class</span></span>  

1.  <span data-ttu-id="08a14-231">**ソリューション エクスプ ローラー**、ダブルクリックして、 **EchoAdapterConnectionUri.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="08a14-231">In **Solution Explorer**, double-click the **EchoAdapterConnectionUri.cs** file.</span></span>  

2.  <span data-ttu-id="08a14-232">Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内をポイント**アウトライン**、 をクリックし、**アウトラインの中止**します。</span><span class="sxs-lookup"><span data-stu-id="08a14-232">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  

3.  <span data-ttu-id="08a14-233">Visual Studio エディターで検索、**コンストラクター**リージョン。</span><span class="sxs-lookup"><span data-stu-id="08a14-233">In the Visual Studio editor, find the **Constructors** region.</span></span> <span data-ttu-id="08a14-234">内で、 **EchoAdapterConnectionUri()** 既定コンストラクターを次のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="08a14-234">Inside the **EchoAdapterConnectionUri()** default constructor, add the following statement:</span></span>  

    ```csharp  
    Uri = new Uri("echov2://lobhostname/lobapplication?enableauthentication=False");  
    ```  

4.  <span data-ttu-id="08a14-235">Visual Studio エディターでの内部、 **EchoAdapterConnectionUri (Uri の uri)** コンストラクターをオーバー ロードされ、次のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="08a14-235">In the Visual Studio editor, inside the **EchoAdapterConnectionUri(Uri uri)** overloaded constructor, and add the following statement:</span></span>  

    ```csharp  
    Uri = uri;  
    ```  

     <span data-ttu-id="08a14-236">EchoAdapterConnectionUri(Uri uri) メソッドの実装は、次と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08a14-236">Your implementation of the EchoAdapterConnectionUri(Uri uri) method should match the following:</span></span>  

    ```csharp  
    public EchoAdapterConnectionUri(Uri uri)  
        : base()  
    {  
        Uri = uri;  
    }  
    ```  

5.  <span data-ttu-id="08a14-237">Visual Studio エディターで内で、**パブリック Uri の Uri をオーバーライドする**メソッドを次のロジックで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="08a14-237">In the Visual Studio editor, inside the **public override Uri Uri** method, replace the existing with the following logic.</span></span> <span data-ttu-id="08a14-238">Get は、echoInUpperCase 有無にかかわらず、Uri を構築します。</span><span class="sxs-lookup"><span data-stu-id="08a14-238">The get builds the Uri with echoInUpperCase or without it.</span></span> <span data-ttu-id="08a14-239">セットは、ホスト名、データベース名、およびクエリの値を取得する URI を解析します。</span><span class="sxs-lookup"><span data-stu-id="08a14-239">The set parses the URI to retrieve host name, database name, and query values.</span></span>  

    ```csharp  
    get  
    {  
        // Build the uri  
        if (String.IsNullOrEmpty(this.hostname)) throw new InvalidUriException("Invalid target system host name.");  
        if (String.IsNullOrEmpty(this.application)) throw new InvalidUriException("Invalid target system data source name.");  
        if (EchoInUpperCase)  
        {  
            // build the uri with echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication + "&" + "echoInUpperCase=" + echoInUpperCase);  
        }  
        else  
        {  
            // build the uri without echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication);  
        }  
    }  
    set  
    {  
        // Parse the uri  
        String[] enableAuthValue = GetQueryStringValue(value, "enableAuthentication");  
        if (enableAuthValue.Length > 0) this.enableAuthentication = Boolean.Parse(enableAuthValue[0]);  
        String[] echoInUpperValue = GetQueryStringValue(value, "echoInUpperCase");  
        if (echoInUpperValue.Length > 0) this.echoInUpperCase = Boolean.Parse(echoInUpperValue[0]);  

        this.hostname = value.Host;  
        String[] applicationValue = value.AbsolutePath.Split('/');  
        if (applicationValue.Length > 1) this.Application = applicationValue[1];  
    }  
    ```  

6.  <span data-ttu-id="08a14-240">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="08a14-240">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  

7.  <span data-ttu-id="08a14-241">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08a14-241">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="08a14-242">プロジェクトを正常にコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08a14-242">You should successfully compile the project.</span></span> <span data-ttu-id="08a14-243">そうでない場合は、上記のすべての手順に従っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="08a14-243">If not, ensure that you have followed every step above.</span></span>  

> [!NOTE]
>  <span data-ttu-id="08a14-244">これで作業が保存されました。</span><span class="sxs-lookup"><span data-stu-id="08a14-244">You saved your work.</span></span> <span data-ttu-id="08a14-245">安全にこの時点で Visual Studio を閉じて、次の手順に進むまたは[手順 4: エコー アダプターのメタデータ参照ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="08a14-245">You can safely close Visual Studio at this time or go to the next step, [Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).</span></span>  

## <a name="what-did-i-just-do"></a><span data-ttu-id="08a14-246">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="08a14-246">What Did I Just Do?</span></span>  
 <span data-ttu-id="08a14-247">エコー アダプターの接続を実装しました。</span><span class="sxs-lookup"><span data-stu-id="08a14-247">You implemented the connection for the Echo adapter.</span></span> <span data-ttu-id="08a14-248">接続のコンポーネントについて説明しました、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、接続 URI の基本的な構造、URI の要素をプログラムで解析する方法および URI 要素を使用して、アダプターの機能を変更する方法。</span><span class="sxs-lookup"><span data-stu-id="08a14-248">You learned the connection components of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], the basic structure of the connection URI, how to programmatically parse the URI elements, and how you can use the URI element to change the adapter feature.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="08a14-249">次の手順</span><span class="sxs-lookup"><span data-stu-id="08a14-249">Next Steps</span></span>  
 <span data-ttu-id="08a14-250">メタデータの参照、検索、および機能、および送信のメッセージ交換の解決を実装します。</span><span class="sxs-lookup"><span data-stu-id="08a14-250">You implement metadata browsing, searching, and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="08a14-251">最後に、ビルドし、アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="08a14-251">Finally, you build and deploy the adapter.</span></span>  

## <a name="see-also"></a><span data-ttu-id="08a14-252">参照</span><span class="sxs-lookup"><span data-stu-id="08a14-252">See Also</span></span>  
 <span data-ttu-id="08a14-253">[手順 4: エコー アダプターのメタデータ参照ハンドラーを実装する.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="08a14-253">[Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="08a14-254">チュートリアル 1: エコー アダプターを開発する</span><span class="sxs-lookup"><span data-stu-id="08a14-254">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)