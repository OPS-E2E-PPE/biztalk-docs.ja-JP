---
title: Ops アダプタの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IOpsAIC interface
- Ops adapters, configuring
- Ops adapters, IOpsAIC interface
- process management solution tutorial, Ops adapters
- Ops adapters, processing
ms.assetid: 331f3614-e00b-4587-b82b-3c7bc394f361
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b219d88ec07c63baf476cc3a3bf31775e03b2b4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246430"
---
# <a name="using-the-ops-adapter"></a><span data-ttu-id="8a6a2-102">Ops アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="8a6a2-102">Using the Ops Adapter</span></span>
<span data-ttu-id="8a6a2-103">ビジネス プロセス管理ソリューションでは、Ops アダプタを使用して、新しいエラー報告機能からエラー レポートを処理します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-103">The business process management solution uses the Ops adapter to handle error reports from the new error reporting feature.</span></span> <span data-ttu-id="8a6a2-104">ソリューションは、独自に作成し、その他のソリューションでアダプターを使用できますが、簡単にサンプル ハンドラーをメッセージを処理する、アダプターから、です。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-104">The solution includes a sample handler to process messages from the adapter, although you can easily write your own and use the adapter in other solutions.</span></span> <span data-ttu-id="8a6a2-105">エラー報告機能については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-105">For information about the error reporting feature, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a6a2-106">ソリューションでは、エラー報告のアダプターを使用して、その使用はエラー処理に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-106">Although the solution uses the adapter for error reporting, its use is not limited to error handling.</span></span> <span data-ttu-id="8a6a2-107">メッセージに対する応答で特定のオブジェクトのメソッドを実行するたびに、さまざまな状況でアダプタを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-107">You can use the adapter in a variety of circumstances whenever you want to execute a specific object method in response to a message.</span></span>  
  
## <a name="how-the-ops-adapter-processes-error-reports"></a><span data-ttu-id="8a6a2-108">Ops アダプタがエラー レポートを処理する方法</span><span class="sxs-lookup"><span data-stu-id="8a6a2-108">How the Ops Adapter Processes Error Reports</span></span>  
 <span data-ttu-id="8a6a2-109">エラー報告を使用して、ソリューション内のポートが最終的に、エラー メッセージを送信、 **BIZTALKERRORS-SP**ポート。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-109">Ports in the solution that use error reporting ultimately send the error messages to the **BizTalkErrors-SP** port.</span></span> <span data-ttu-id="8a6a2-110">存在のテストをポートでフィルター処理、 **ErrorReport.ErrorType**コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-110">The filter on the port tests for the existence of the **ErrorReport.ErrorType** context property.</span></span> <span data-ttu-id="8a6a2-111">エラー報告メッセージだけでは、このコンテキスト プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-111">Only error report messages have this context property.</span></span>  
  
 <span data-ttu-id="8a6a2-112">**BIZTALKERRORS-SP**送信ポートは、エンベロープにメッセージを配置する、XML アセンブラ コンポーネントを使用するパイプラインでエラー メッセージを実行します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-112">The **BizTalkErrors-SP** send port runs the error message through a pipeline that uses an XML assembler component to put the message in an envelope.</span></span> <span data-ttu-id="8a6a2-113">メッセージは Ops アダプタに移動します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-113">The message then goes to the Ops adapter.</span></span>  
  
 <span data-ttu-id="8a6a2-114">ErrorEnvelope スキーマによって定義された、エンベロープは、あらゆる種類のメッセージを受け入れるようにマークされます。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-114">The envelope, defined by the ErrorEnvelope schema, is marked to accept any type of message.</span></span> <span data-ttu-id="8a6a2-115">ただし、"any"は、メッセージ型で定義されている BizTalk グループ。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-115">However, "any" means any message type defined in the BizTalk group.</span></span> <span data-ttu-id="8a6a2-116">ソリューションが不明な種類のメッセージを受信メッセージが保留になることもします。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-116">This can produce suspended messages if the solution receives a message of an unknown type.</span></span> <span data-ttu-id="8a6a2-117">このようなメッセージがエラーを生成およびにルーティングされます、 **BIZTALKERRORS-SP**ポート。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-117">Such a message would produce an error and would be routed to the **BizTalkErrors-SP** port.</span></span> <span data-ttu-id="8a6a2-118">さらに、メッセージはエラーを生成パイプラインの XML アセンブラー コンポーネントで既知のメッセージの種類はならないためです。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-118">In turn, the message would generate an error in the XML assembler component of the pipeline because it would not be a known message type.</span></span> <span data-ttu-id="8a6a2-119">パイプラインのエラーは、メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-119">The pipeline error suspends the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a6a2-120">不明なメッセージの種類によるルーティング エラーを処理するカスタム パイプライン コンポーネントを記述し、用のカスタム パイプラインでコンポーネントを使用する必要があります、 **BIZTALKERRORS-SP**ポート。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-120">To handle routing errors due to unknown message types, you must write a custom pipeline component and use the component in a custom pipeline for the **BizTalkErrors-SP** port.</span></span> <span data-ttu-id="8a6a2-121">カスタム コンポーネントには、XML アセンブラー コンポーネントが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-121">The custom component replaces the XML assembler component.</span></span> <span data-ttu-id="8a6a2-122">カスタム コンポーネントを配置する必要があります、 **ErrorReport**プロパティをエンベロープ ヘッダーとメッセージをエンベロープの本文に追加します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-122">Your custom component must put the **ErrorReport** properties in the envelope header and add the message to the body of the envelope.</span></span>  
  
 <span data-ttu-id="8a6a2-123">Ops アダプタは、トランザクションの一方向の送信アダプターです。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-123">The Ops adapter is a transactional, one-way send adapter.</span></span> <span data-ttu-id="8a6a2-124">アダプターがメッセージを処理するときが初めて読み込まれる、指定されたアセンブリに必要な場合。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-124">When the adapter processes a message, it first loads the specified assembly, if necessary.</span></span> <span data-ttu-id="8a6a2-125">アダプターは、呼び出しごとにアセンブリを読み込むというオーバーヘッドを回避するためにメモリ内アセンブリをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-125">The adapter caches assemblies in memory to avoid the overhead of loading the assembly for each call.</span></span> <span data-ttu-id="8a6a2-126">指定したクラスのインスタンスを作成し、リフレクションを使用して実装するアセンブリのオブジェクトを取得、 **IOpsAIC**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-126">It then creates an instance of the specified class, and then uses reflection to get the object in the assembly implementing the **IOpsAIC** interface.</span></span> <span data-ttu-id="8a6a2-127">このすべてが成功した場合は、アダプターが呼び出す、**初期化**メソッドに呼び出し、 **Execute**メソッドは、レポートのエラー メッセージを渡すことです。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-127">If all of this is successful, the adapter calls the **Initialize** method and then calls the **Execute** method, passing the error report message.</span></span>  
  
 <span data-ttu-id="8a6a2-128">エラーがある場合を呼び出す**Execute**アダプターがメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-128">If there is an error calling **Execute**, the adapter resubmits the message.</span></span> <span data-ttu-id="8a6a2-129">指定したクラスが実装していない場合、 **IOpsAIC**インターフェイスまたはクラスまたはアセンブリが見つからない場合、アダプターがメッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-129">If the specified class does not implement the **IOpsAIC** interface, or the class or assembly can't be found, the adapter suspends the message.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="8a6a2-130">アダプターは、リフレクションを使用するため、クラスを含むアセンブリがグローバル アセンブリ キャッシュ (GAC) にあります。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-130">Because the adapter uses reflection, the assembly containing the class must be in the Global Assembly Cache (GAC).</span></span>  
  
## <a name="the-iopsaic-interface"></a><span data-ttu-id="8a6a2-131">IOpsAIC インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a6a2-131">The IOpsAIC Interface</span></span>  
 <span data-ttu-id="8a6a2-132">アダプターが実装するオブジェクトが必要です、 **IOpsAIC**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-132">The adapter requires an object that implements the **IOpsAIC** interface.</span></span> <span data-ttu-id="8a6a2-133">インターフェイスは次のようです。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-133">The interface appears as follows:</span></span>  
  
```  
interface IOpsAIC  
{  
    void Initialize(string config);  
    void Execute(byte[] message);  
}  
```  
  
 <span data-ttu-id="8a6a2-134">アダプターでは、元のメッセージを渡しますにバイト配列として、 **Execute**メソッド。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-134">The adapter passes the original message as a byte array to the **Execute** method.</span></span>  
  
## <a name="configuring-the-adapter"></a><span data-ttu-id="8a6a2-135">アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="8a6a2-135">Configuring the Adapter</span></span>  
 <span data-ttu-id="8a6a2-136">その他のアダプターの場合と同じようにアダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-136">You configure the adapter just as you would any other adapter.</span></span> <span data-ttu-id="8a6a2-137">次の表では、アダプターの構成プロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-137">The following table describes the adapter's configuration properties:</span></span>  
  
|<span data-ttu-id="8a6a2-138">表示名</span><span class="sxs-lookup"><span data-stu-id="8a6a2-138">Display Name</span></span>|<span data-ttu-id="8a6a2-139">説明</span><span class="sxs-lookup"><span data-stu-id="8a6a2-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="8a6a2-140">**.NET アセンブリの厳密な名前**</span><span class="sxs-lookup"><span data-stu-id="8a6a2-140">**.NET Assembly Strong Name**</span></span>|<span data-ttu-id="8a6a2-141">アセンブリの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-141">The fully qualified name of the assembly.</span></span>|  
|<span data-ttu-id="8a6a2-142">**OpsAIC クラス名**</span><span class="sxs-lookup"><span data-stu-id="8a6a2-142">**OpsAIC Class Name**</span></span>|<span data-ttu-id="8a6a2-143">実装するアセンブリ内のクラスの名前、 **IOpsAIC**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-143">The name of the class within the assembly that implements the **IOpsAIC** interface.</span></span>|  
|<span data-ttu-id="8a6a2-144">**初期化データ**</span><span class="sxs-lookup"><span data-stu-id="8a6a2-144">**Initialization Data**</span></span>|<span data-ttu-id="8a6a2-145">引数として渡される文字列、**初期化**クラスのメソッド。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-145">A string passed as an argument to the **Initialize** method of the class.</span></span>|  
  
 <span data-ttu-id="8a6a2-146">アダプターが、アセンブリの完全修飾名が必要であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-146">Notice that the adapter requires the fully qualified name of the assembly.</span></span> <span data-ttu-id="8a6a2-147">完全修飾名は、アセンブリを GAC に追加するときに指定された名前です。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-147">The fully qualified name is the name given to an assembly when you add it to the GAC.</span></span> <span data-ttu-id="8a6a2-148">完全修飾名は、アセンブリの名前、バージョン、カルチャ、および公開キー トークンを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-148">The fully qualified name is a string containing the assembly's name, version, culture, and public key token.</span></span> <span data-ttu-id="8a6a2-149">グローバル アセンブリ キャッシュ ツールを使用してアセンブリの完全修飾名を確認できます gacutil.exe します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-149">You can see the fully qualified names of assemblies by using the Global Assembly Cache Tool, gacutil.exe.</span></span>  
  
 <span data-ttu-id="8a6a2-150">完全修飾アセンブリ名の詳細については、.NET Framework 開発者ガイドの「アセンブリ Names」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-150">For more information about fully qualified assembly names, see "Assembly Names" in the .NET Framework Developer's Guide.</span></span> <span data-ttu-id="8a6a2-151">Gacutil.exe の詳細について「グローバル アセンブリ キャッシュ ツール (Gacutil.exe)」を参照してください、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]開発者ガイド。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-151">For more information about gacutil.exe, see "Global Assembly Cache Tool (Gacutil.exe)" in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Developer's Guide.</span></span>  
  
 <span data-ttu-id="8a6a2-152">クラス名では、名前空間を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-152">You must provide the namespace with the class name.</span></span> <span data-ttu-id="8a6a2-153">たとえば、クラスが**OpsHandler**で、 **OperationsHandler**名前空間とクラス名を指定**OperationsHandler.OpsHandler**します。</span><span class="sxs-lookup"><span data-stu-id="8a6a2-153">For example, if the class is **OpsHandler** in the **OperationsHandler** namespace, you would give the class name as **OperationsHandler.OpsHandler**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a6a2-154">参照</span><span class="sxs-lookup"><span data-stu-id="8a6a2-154">See Also</span></span>  
 [<span data-ttu-id="8a6a2-155">Ops アダプター</span><span class="sxs-lookup"><span data-stu-id="8a6a2-155">The Ops Adapter</span></span>](../core/the-ops-adapter.md)