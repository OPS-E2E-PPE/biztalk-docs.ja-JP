---
title: "Ops アダプタの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IOpsAIC interface
- Ops adapters, configuring
- Ops adapters, IOpsAIC interface
- process management solution tutorial, Ops adapters
- Ops adapters, processing
ms.assetid: 331f3614-e00b-4587-b82b-3c7bc394f361
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d93436e727265c4b381cdff72c42b3a677d0a4dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-ops-adapter"></a><span data-ttu-id="b159b-102">Ops アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="b159b-102">Using the Ops Adapter</span></span>
<span data-ttu-id="b159b-103">ビジネス プロセス管理ソリューションは、Ops アダプタを使用して、新しいエラー報告機能からのエラー報告を処理します。</span><span class="sxs-lookup"><span data-stu-id="b159b-103">The business process management solution uses the Ops adapter to handle error reports from the new error reporting feature.</span></span> <span data-ttu-id="b159b-104">アダプタからのメッセージを処理するサンプル ハンドラがソリューションに含まれていますが、独自のハンドラを簡単に作成して、アダプタを他のソリューションで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="b159b-104">The solution includes a sample handler to process messages from the adapter, although you can easily write your own and use the adapter in other solutions.</span></span> <span data-ttu-id="b159b-105">エラー報告機能については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)です。</span><span class="sxs-lookup"><span data-stu-id="b159b-105">For information about the error reporting feature, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b159b-106">このソリューションではエラー報告用にアダプタを使用しますが、アダプタはエラー処理にだけ使用するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b159b-106">Although the solution uses the adapter for error reporting, its use is not limited to error handling.</span></span> <span data-ttu-id="b159b-107">メッセージの応答で特定のオブジェクト メソッドを実行する場合、さまざまな状況でアダプタを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b159b-107">You can use the adapter in a variety of circumstances whenever you want to execute a specific object method in response to a message.</span></span>  
  
## <a name="how-the-ops-adapter-processes-error-reports"></a><span data-ttu-id="b159b-108">Ops アダプタがエラー報告を処理する方法</span><span class="sxs-lookup"><span data-stu-id="b159b-108">How the Ops Adapter Processes Error Reports</span></span>  
 <span data-ttu-id="b159b-109">エラー報告を使用するソリューション内のポート最終的には、エラー メッセージを送信する、 **BIZTALKERRORS-SP**ポートです。</span><span class="sxs-lookup"><span data-stu-id="b159b-109">Ports in the solution that use error reporting ultimately send the error messages to the **BizTalkErrors-SP** port.</span></span> <span data-ttu-id="b159b-110">ポートのフィルターがの存在を検査、 **ErrorReport.ErrorType**コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="b159b-110">The filter on the port tests for the existence of the **ErrorReport.ErrorType** context property.</span></span> <span data-ttu-id="b159b-111">エラー報告メッセージだけがこのコンテキスト プロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="b159b-111">Only error report messages have this context property.</span></span>  
  
 <span data-ttu-id="b159b-112">**BIZTALKERRORS-SP**送信ポートは、エンベロープにメッセージを格納する、XML アセンブラ コンポーネントを使用するパイプラインを介して、エラー メッセージを実行します。</span><span class="sxs-lookup"><span data-stu-id="b159b-112">The **BizTalkErrors-SP** send port runs the error message through a pipeline that uses an XML assembler component to put the message in an envelope.</span></span> <span data-ttu-id="b159b-113">その後で、メッセージは Ops アダプタに送られます。</span><span class="sxs-lookup"><span data-stu-id="b159b-113">The message then goes to the Ops adapter.</span></span>  
  
 <span data-ttu-id="b159b-114">ErrorEnvelope スキーマによって定義されるエンベロープは、メッセージの種類をすべて受け入れるようにマークされています。</span><span class="sxs-lookup"><span data-stu-id="b159b-114">The envelope, defined by the ErrorEnvelope schema, is marked to accept any type of message.</span></span> <span data-ttu-id="b159b-115">ただし、BizTalk グループで定義されたメッセージの種類に限られます。</span><span class="sxs-lookup"><span data-stu-id="b159b-115">However, "any" means any message type defined in the BizTalk group.</span></span> <span data-ttu-id="b159b-116">未知の種類のメッセージを受け取った場合は、メッセージが保留されます。</span><span class="sxs-lookup"><span data-stu-id="b159b-116">This can produce suspended messages if the solution receives a message of an unknown type.</span></span> <span data-ttu-id="b159b-117">このようなメッセージとエラーが生成されにルーティングされます、 **BIZTALKERRORS-SP**ポートです。</span><span class="sxs-lookup"><span data-stu-id="b159b-117">Such a message would produce an error and would be routed to the **BizTalkErrors-SP** port.</span></span> <span data-ttu-id="b159b-118">その結果、メッセージは既知の種類にはならないので、パイプラインの XML アセンブラ コンポーネントでエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b159b-118">In turn, the message would generate an error in the XML assembler component of the pipeline because it would not be a known message type.</span></span> <span data-ttu-id="b159b-119">パイプライン エラーによりメッセージが保留されます。</span><span class="sxs-lookup"><span data-stu-id="b159b-119">The pipeline error suspends the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b159b-120">不明なメッセージの種類によるルーティング エラーを処理するには、カスタム パイプライン コンポーネントを記述および用のカスタム パイプラインのコンポーネントを使用する必要があります、 **BIZTALKERRORS-SP**ポートです。</span><span class="sxs-lookup"><span data-stu-id="b159b-120">To handle routing errors due to unknown message types, you must write a custom pipeline component and use the component in a custom pipeline for the **BizTalkErrors-SP** port.</span></span> <span data-ttu-id="b159b-121">カスタム コンポーネントは、XML アセンブラ コンポーネントを置換します。</span><span class="sxs-lookup"><span data-stu-id="b159b-121">The custom component replaces the XML assembler component.</span></span> <span data-ttu-id="b159b-122">カスタム コンポーネントを配置する必要があります、 **ErrorReport**エンベロープ ヘッダー内のプロパティとメッセージをエンベロープの本文に追加します。</span><span class="sxs-lookup"><span data-stu-id="b159b-122">Your custom component must put the **ErrorReport** properties in the envelope header and add the message to the body of the envelope.</span></span>  
  
 <span data-ttu-id="b159b-123">Ops アダプタは、トランザクションの一方向送信アダプタです。</span><span class="sxs-lookup"><span data-stu-id="b159b-123">The Ops adapter is a transactional, one-way send adapter.</span></span> <span data-ttu-id="b159b-124">アダプタがメッセージを処理する場合、必要に応じて、最初に指定のアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b159b-124">When the adapter processes a message, it first loads the specified assembly, if necessary.</span></span> <span data-ttu-id="b159b-125">アダプタはアセンブリをメモリにキャッシュして、呼び出しごとにアセンブリを読み込むというオーバーヘッドを回避します。</span><span class="sxs-lookup"><span data-stu-id="b159b-125">The adapter caches assemblies in memory to avoid the overhead of loading the assembly for each call.</span></span> <span data-ttu-id="b159b-126">指定したクラスのインスタンスを作成し、リフレクションを使用して実装するアセンブリのオブジェクトを取得、 **IOpsAIC**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b159b-126">It then creates an instance of the specified class, and then uses reflection to get the object in the assembly implementing the **IOpsAIC** interface.</span></span> <span data-ttu-id="b159b-127">これはすべてが成功した場合、アダプターを呼び出す、**初期化**メソッドを呼び出し、続いて、 **Execute**メソッド、エラー レポート メッセージを渡すことです。</span><span class="sxs-lookup"><span data-stu-id="b159b-127">If all of this is successful, the adapter calls the **Initialize** method and then calls the **Execute** method, passing the error report message.</span></span>  
  
 <span data-ttu-id="b159b-128">エラーがある場合を呼び出す**Execute**アダプターがメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="b159b-128">If there is an error calling **Execute**, the adapter resubmits the message.</span></span> <span data-ttu-id="b159b-129">指定したクラスを実装しない場合、 **IOpsAIC**インターフェイス、またはクラスやアセンブリが見つかりません、アダプターがメッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="b159b-129">If the specified class does not implement the **IOpsAIC** interface, or the class or assembly can't be found, the adapter suspends the message.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="b159b-130">アダプタはリフレクションを使用するので、グローバル アセンブリ キャッシュ (GAC) 内にクラスを含むアセンブリが必要です。</span><span class="sxs-lookup"><span data-stu-id="b159b-130">Because the adapter uses reflection, the assembly containing the class must be in the Global Assembly Cache (GAC).</span></span>  
  
## <a name="the-iopsaic-interface"></a><span data-ttu-id="b159b-131">IOpsAIC インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b159b-131">The IOpsAIC Interface</span></span>  
 <span data-ttu-id="b159b-132">アダプターを実装するオブジェクトが必要です、 **IOpsAIC**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b159b-132">The adapter requires an object that implements the **IOpsAIC** interface.</span></span> <span data-ttu-id="b159b-133">インターフェイスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b159b-133">The interface appears as follows:</span></span>  
  
```  
interface IOpsAIC  
{  
    void Initialize(string config);  
    void Execute(byte[] message);  
}  
```  
  
 <span data-ttu-id="b159b-134">アダプターでは、元のメッセージを渡すバイト配列として、 **Execute**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="b159b-134">The adapter passes the original message as a byte array to the **Execute** method.</span></span>  
  
## <a name="configuring-the-adapter"></a><span data-ttu-id="b159b-135">アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="b159b-135">Configuring the Adapter</span></span>  
 <span data-ttu-id="b159b-136">他のアダプタと同じようにアダプタを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b159b-136">You configure the adapter just as you would any other adapter.</span></span> <span data-ttu-id="b159b-137">次の表では、アダプタの構成プロパティについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="b159b-137">The following table describes the adapter's configuration properties:</span></span>  
  
|<span data-ttu-id="b159b-138">表示名</span><span class="sxs-lookup"><span data-stu-id="b159b-138">Display Name</span></span>|<span data-ttu-id="b159b-139">Description</span><span class="sxs-lookup"><span data-stu-id="b159b-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="b159b-140">**.NET アセンブリの厳密な名前**</span><span class="sxs-lookup"><span data-stu-id="b159b-140">**.NET Assembly Strong Name**</span></span>|<span data-ttu-id="b159b-141">アセンブリの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="b159b-141">The fully qualified name of the assembly.</span></span>|  
|<span data-ttu-id="b159b-142">**OpsAIC クラス名**</span><span class="sxs-lookup"><span data-stu-id="b159b-142">**OpsAIC Class Name**</span></span>|<span data-ttu-id="b159b-143">実装するアセンブリ内のクラスの名前、 **IOpsAIC**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b159b-143">The name of the class within the assembly that implements the **IOpsAIC** interface.</span></span>|  
|<span data-ttu-id="b159b-144">**初期化データ**</span><span class="sxs-lookup"><span data-stu-id="b159b-144">**Initialization Data**</span></span>|<span data-ttu-id="b159b-145">引数として渡される文字列、**初期化**クラスのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="b159b-145">A string passed as an argument to the **Initialize** method of the class.</span></span>|  
  
 <span data-ttu-id="b159b-146">アダプタにはアセンブリの完全修飾名が必要です。</span><span class="sxs-lookup"><span data-stu-id="b159b-146">Notice that the adapter requires the fully qualified name of the assembly.</span></span> <span data-ttu-id="b159b-147">完全修飾名は、アセンブリを GAC に追加するときにアセンブリに指定する名前で、</span><span class="sxs-lookup"><span data-stu-id="b159b-147">The fully qualified name is the name given to an assembly when you add it to the GAC.</span></span> <span data-ttu-id="b159b-148">アセンブリの名前、バージョン、カルチャ、および公開キー トークンを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="b159b-148">The fully qualified name is a string containing the assembly's name, version, culture, and public key token.</span></span> <span data-ttu-id="b159b-149">グローバル アセンブリ キャッシュ ツールを使用して、アセンブリの完全修飾名を参照できます。</span><span class="sxs-lookup"><span data-stu-id="b159b-149">You can see the fully qualified names of assemblies by using the Global Assembly Cache Tool, gacutil.exe.</span></span>  
  
 <span data-ttu-id="b159b-150">完全修飾名の詳細については、『.NET Framework 開発者ガイド』の「アセンブリ名 (Assembly Names)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b159b-150">For more information about fully qualified assembly names, see "Assembly Names" in the .NET Framework Developer's Guide.</span></span> <span data-ttu-id="b159b-151">gacutil.exe の詳細については、『[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 開発者ガイド』の「グローバル アセンブリ キャッシュ ツール (Gacutil.exe) (Global Assembly Cache Tool (Gacutil.exe))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b159b-151">For more information about gacutil.exe, see "Global Assembly Cache Tool (Gacutil.exe)" in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Developer's Guide.</span></span>  
  
 <span data-ttu-id="b159b-152">クラス名には名前空間を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b159b-152">You must provide the namespace with the class name.</span></span> <span data-ttu-id="b159b-153">たとえば、クラスが**OpsHandler**で、 **OperationsHandler**名前空間とクラス名を指定**OperationsHandler.OpsHandler**です。</span><span class="sxs-lookup"><span data-stu-id="b159b-153">For example, if the class is **OpsHandler** in the **OperationsHandler** namespace, you would give the class name as **OperationsHandler.OpsHandler**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b159b-154">参照</span><span class="sxs-lookup"><span data-stu-id="b159b-154">See Also</span></span>  
 [<span data-ttu-id="b159b-155">Ops アダプタ</span><span class="sxs-lookup"><span data-stu-id="b159b-155">The Ops Adapter</span></span>](../core/the-ops-adapter.md)