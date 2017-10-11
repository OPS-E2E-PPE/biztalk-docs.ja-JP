---
title: "Transactional Adapter (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31a13377-cc89-4763-ad1b-508a16fc9708
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfad3a99d313a8007962cf56f403243c72f6a377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transactional-adapter-biztalk-server-sample"></a><span data-ttu-id="f700f-102">Transactional Adapter (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="f700f-102">Transactional Adapter (BizTalk Server Sample)</span></span>
<span data-ttu-id="f700f-103">Transactional Adapter サンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージの処理中にデータベースに対して明示的な Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションを作成および使用する方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="f700f-103">The Transactional Adapter sample demonstrates how to create and use an explicit Microsoft Distributed Transaction Coordinator (MSDTC) transaction against a database during processing of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="f700f-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="f700f-104">What This Sample Does</span></span>  
 <span data-ttu-id="f700f-105">このサンプルには、MSDTC トランザクションを使用して SQL Server データベースからデータを取得するために、ユーザーが指定した間隔で SQL ステートメントを実行する受信アダプターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f700f-105">This sample contains a receive adapter which runs a SQL statement at a user-specified interval to obtain data from a SQL Server database using an MSDTC transaction.</span></span> <span data-ttu-id="f700f-106">データは同じトランザクションのコンテキストでメッセージ形式で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f700f-106">The data is then submitted to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database in the form of a message under the context of the same transaction.</span></span>  
  
 <span data-ttu-id="f700f-107">対応する送信アダプターは、トランザクションのコンテキストで BizTalk メッセージからの入力を使用してユーザー指定の SQL ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="f700f-107">The corresponding send adapter runs a user-specified SQL stored procedure using input from a BizTalk message in the context of a transaction.</span></span> <span data-ttu-id="f700f-108">そのメッセージからの特定のデータを使用して、同じトランザクションでメッセージ ボックス データベースから対応するメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="f700f-108">It uses specific data from that message to locate and delete the corresponding message from the Message Box database under that same transaction.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="f700f-109">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="f700f-109">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="f700f-110">このサンプルのソリューションには 2 つのプロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f700f-110">This sample has two projects in its solution.</span></span> <span data-ttu-id="f700f-111">1 つ目のプロジェクトは、ユーザーがこのアダプターを使用する受信場所と送信ポートを構成できるようにランタイムの前に使用される管理プロジェクト (Admin) です。</span><span class="sxs-lookup"><span data-stu-id="f700f-111">The first is the administrative project (Admin) which is used prior to runtime to allow a user to configure the receive locations and send ports that use this adapter.</span></span> <span data-ttu-id="f700f-112">2 つ目のプロジェクトは、送信アダプターと受信アダプターの実行中に実行されるランタイム プロジェクト (Runtime) です。</span><span class="sxs-lookup"><span data-stu-id="f700f-112">The second is the runtime project (Runtime) that runs when the send and receive adapters are executing.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="f700f-113">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="f700f-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="f700f-114">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="f700f-114">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="f700f-115">\<*パスのサンプル*> \Samples\AdaptersDevelopment\TransactionalAdapter。</span><span class="sxs-lookup"><span data-stu-id="f700f-115">\<*Samples Path*>\Samples\AdaptersDevelopment\TransactionalAdapter.</span></span> <span data-ttu-id="f700f-116">管理構成プロジェクトは \Admin フォルダーにあり、ランタイム プロジェクトは \Runtime フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="f700f-116">The administrative configuration project is located in the \Admin folder, while the runtime project exists in the \Runtime folder.</span></span>  
  
 <span data-ttu-id="f700f-117">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="f700f-117">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="f700f-118">管理プロジェクトのファイル名</span><span class="sxs-lookup"><span data-stu-id="f700f-118">Admin Project Filename</span></span>|<span data-ttu-id="f700f-119">管理プロジェクト ファイルの説明</span><span class="sxs-lookup"><span data-stu-id="f700f-119">Admin Project File Description</span></span>|  
|----------------------------|------------------------------------|  
|<span data-ttu-id="f700f-120">TransactionalAdmin.csproj</span><span class="sxs-lookup"><span data-stu-id="f700f-120">TransactionalAdmin.csproj</span></span>|<span data-ttu-id="f700f-121">ランタイム前の構成に使用されるアダプター管理プロジェクト ファイル</span><span class="sxs-lookup"><span data-stu-id="f700f-121">Adapter administrative project file used for pre-runtime configuration</span></span>|  
|<span data-ttu-id="f700f-122">TransactionalReceiveHandler.xsd</span><span class="sxs-lookup"><span data-stu-id="f700f-122">TransactionalReceiveHandler.xsd</span></span>|<span data-ttu-id="f700f-123">受信ハンドラー プロパティの XSD</span><span class="sxs-lookup"><span data-stu-id="f700f-123">XSD for receive handler properties</span></span>|  
|<span data-ttu-id="f700f-124">TransactionalReceiveLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="f700f-124">TransactionalReceiveLocation.xsd</span></span>|<span data-ttu-id="f700f-125">受信場所プロパティの XSD</span><span class="sxs-lookup"><span data-stu-id="f700f-125">XSD for receive location properties</span></span>|  
|<span data-ttu-id="f700f-126">TransactionalTransmitLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="f700f-126">TransactionalTransmitLocation.xsd</span></span>|<span data-ttu-id="f700f-127">送信場所プロパティの XSD</span><span class="sxs-lookup"><span data-stu-id="f700f-127">XSD for transmit location properties</span></span>|  
|<span data-ttu-id="f700f-128">TransactionalTransmitHandler.xsd</span><span class="sxs-lookup"><span data-stu-id="f700f-128">TransactionalTransmitHandler.xsd</span></span>|<span data-ttu-id="f700f-129">送信ハンドラー プロパティの XSD</span><span class="sxs-lookup"><span data-stu-id="f700f-129">XSD for transmit handler properties</span></span>|  
|<span data-ttu-id="f700f-130">TransactionalAdapterManagement.cs</span><span class="sxs-lookup"><span data-stu-id="f700f-130">TransactionalAdapterManagement.cs</span></span>|<span data-ttu-id="f700f-131">アダプター構成管理。</span><span class="sxs-lookup"><span data-stu-id="f700f-131">Adapter configuration management.</span></span> <span data-ttu-id="f700f-132">サポートされていると考えられる構成の種類 (4 種類) のそれぞれに XSD 構成スキーマを返すために、BizTalk アダプター フレームワークによって呼び出される GetConfigSchema を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="f700f-132">Contains GetConfigSchema which is invoked by the BizTalk Adapter Framework to return an XSD configuration schema for each of the (four) possible configuration types it supports.</span></span>|  
  
|<span data-ttu-id="f700f-133">ランタイム プロジェクトのファイル名</span><span class="sxs-lookup"><span data-stu-id="f700f-133">Runtime Project Filename</span></span>|<span data-ttu-id="f700f-134">ランタイム プロジェクト ファイルの説明</span><span class="sxs-lookup"><span data-stu-id="f700f-134">Runtime Project File Description</span></span>|  
|------------------------------|--------------------------------------|  
|<span data-ttu-id="f700f-135">Transactional.csproj</span><span class="sxs-lookup"><span data-stu-id="f700f-135">Transactional.csproj</span></span>|<span data-ttu-id="f700f-136">アダプター ランタイム プロジェクト ファイル</span><span class="sxs-lookup"><span data-stu-id="f700f-136">Adapter runtime project file</span></span>|  
|<span data-ttu-id="f700f-137">TransactionalAsyncBatch.cs</span><span class="sxs-lookup"><span data-stu-id="f700f-137">TransactionalAsyncBatch.cs</span></span>|<span data-ttu-id="f700f-138">アダプターの送信部分の非同期的な実装</span><span class="sxs-lookup"><span data-stu-id="f700f-138">Asynchronous implementation of the send part of the adapter</span></span>|  
|<span data-ttu-id="f700f-139">TransactionalDeleteBatch.cs</span><span class="sxs-lookup"><span data-stu-id="f700f-139">TransactionalDeleteBatch.cs</span></span>|<span data-ttu-id="f700f-140">メッセージ バッチを削除し、トランザクションをコミットまたは中断するように指定します</span><span class="sxs-lookup"><span data-stu-id="f700f-140">Deletes a batch of messages and votes to commit or abort a transaction</span></span>|  
|<span data-ttu-id="f700f-141">TransactionalProperties.cs</span><span class="sxs-lookup"><span data-stu-id="f700f-141">TransactionalProperties.cs</span></span>|<span data-ttu-id="f700f-142">構成プロパティを抽出および設定します</span><span class="sxs-lookup"><span data-stu-id="f700f-142">Extracts and sets configuration properties</span></span>|  
|<span data-ttu-id="f700f-143">TransactionalReceiver.cs</span><span class="sxs-lookup"><span data-stu-id="f700f-143">TransactionalReceiver.cs</span></span>|<span data-ttu-id="f700f-144">受信エンドポイントを作成および管理します</span><span class="sxs-lookup"><span data-stu-id="f700f-144">Creates and manages receive endpoints</span></span>|  
|<span data-ttu-id="f700f-145">TransactionalReceiverEndpoint.cs</span><span class="sxs-lookup"><span data-stu-id="f700f-145">TransactionalReceiverEndpoint.cs</span></span>|<span data-ttu-id="f700f-146">受信場所ごとの実際の受信待機またはポーリング</span><span class="sxs-lookup"><span data-stu-id="f700f-146">Actual listening or polling for each receive location</span></span>|  
|<span data-ttu-id="f700f-147">TransactionalTransmitter.cs</span><span class="sxs-lookup"><span data-stu-id="f700f-147">TransactionalTransmitter.cs</span></span>|<span data-ttu-id="f700f-148">メッセージ エンジンから送信されるメッセージ バッチを受け取ります</span><span class="sxs-lookup"><span data-stu-id="f700f-148">Accepts a batch of messages from the Messaging Engine to be transmitted</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="f700f-149">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="f700f-149">How to Use This Sample</span></span>  
 <span data-ttu-id="f700f-150">このサンプルは、明示的なトランザクションを使用してカスタムの送信アダプターと受信アダプターを作成するときに使用するフレームワークです。</span><span class="sxs-lookup"><span data-stu-id="f700f-150">This sample is meant as a framework for you to use in creating custom send and receive adapters using explicit transactions.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="f700f-151">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="f700f-151">Building and Initializing This Sample</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f700f-152">BizTalk 環境が 64 ビットである、またはインストール場所が変更されている場合は、それに合わせて OutboundAssemblyPath、InboundAssemblyPath、および AdapterMgmtAssemblyPath を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f700f-152">If the BizTalk installation is 64-bit or the location of installation is modified, OutboundAssemblyPath, InboundAssemblyPath, AdapterMgmtAssemblyPath would need to be changed accordingly.</span></span>  
  
#### <a name="create-a-strong-name-key-for-the-transactional-adapter-sample"></a><span data-ttu-id="f700f-153">Transactional Adapter サンプルの厳密な名前キーの作成します。</span><span class="sxs-lookup"><span data-stu-id="f700f-153">Create a Strong Name Key for the Transactional Adapter sample</span></span>  
  
1.  <span data-ttu-id="f700f-154">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-154">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="f700f-155">コマンド プロンプトで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f700f-155">At the command prompt, type the following and then press enter:</span></span>  
  
    ```  
    cd \Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Runtime  
    ```  
  
3.  <span data-ttu-id="f700f-156">コマンド プロンプトで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f700f-156">At the command prompt, type the following and then press enter:</span></span>  
  
    ```  
    sn –k TransactionalAdapter.snk  
    ```  
  
4.  <span data-ttu-id="f700f-157">コマンド プロンプトで次のように入力します。**終了**、し、enter キーを押し、コマンド プロンプト ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f700f-157">At the command prompt, type **exit**, and then press enter to close the command prompt window.</span></span>  
  
#### <a name="build-the-transactional-adapter-solution"></a><span data-ttu-id="f700f-158">トランザクション アダプター ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="f700f-158">Build the Transactional Adapter Solution</span></span>  
  
1.  <span data-ttu-id="f700f-159">をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**アクセサリ**、順にクリック**Windows エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-159">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="f700f-160">参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter、 をダブルクリック**TransactionalAdapter.sln**を開くにはこのソリューションで[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f700f-160">Browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter, and double-click **TransactionalAdapter.sln** to open this solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="f700f-161">ソリューション エクスプ ローラーで Transactional Adapter プロジェクト (Admin および Runtime) の両方を構築を右クリックして**Solution transactionaladapter**、順にクリック**リビルド**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-161">To build both of the Transactional Adapter projects (Admin and Runtime) in Solution Explorer, right-click **Solution TransactionalAdapter**, and then click **Rebuild**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="f700f-162">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="f700f-162">Running This Sample</span></span>  
  
#### <a name="register-the-transactional-adapter"></a><span data-ttu-id="f700f-163">トランザクション アダプターを登録します。</span><span class="sxs-lookup"><span data-stu-id="f700f-163">Register the Transactional Adapter</span></span>  
  
1.  <span data-ttu-id="f700f-164">Windows エクスプローラーで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Admin に移動します。</span><span class="sxs-lookup"><span data-stu-id="f700f-164">In Windows Explorer, navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Admin.</span></span>  
  
2.  <span data-ttu-id="f700f-165">トランザクション アダプター データをレジストリに追加するにはダブルクリック**TransactionalAdmin.reg**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-165">To add the transactional adapter data to the registry, double-click **TransactionalAdmin.reg**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f700f-166">**TransactionalAdmin.reg** C:\Program files \microsoft にハードコードされたパスが含まれています[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\\です。</span><span class="sxs-lookup"><span data-stu-id="f700f-166">**TransactionalAdmin.reg** includes hard-coded paths to C:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\\.</span></span> <span data-ttu-id="f700f-167">既定の場所に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしなかった場合や、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストールを以前のバージョンからアップグレードした場合は、TransactionalAdmin.reg ファイルを変更して適切なパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f700f-167">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the default location or if you upgraded your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation from a previous version, you must modify the file TransactionalAdmin.reg with the appropriate paths.</span></span> <span data-ttu-id="f700f-168">"InboundAssemblyPath"、"OutboundAssemblyPath"、および "AdapterMgmtAssemblyPath" の値に関連付けられたパスを、指定されたファイルの正しい場所を指すように更新します。</span><span class="sxs-lookup"><span data-stu-id="f700f-168">Update the paths associated with the "InboundAssemblyPath", "OutboundAssemblyPath", and "AdapterMgmtAssemblyPath" values to point to the correct location of the specified files.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f700f-169">BizTalk を 64 ビット コンピューターにインストールする場合は、hkey_classes_root \clsid\ レジストリ エントリのすべてのインスタンスを hkey_classes_root \wow6432node\clsid\ に変更、 **TransactionalAdmin.reg**レジストリ ファイル。</span><span class="sxs-lookup"><span data-stu-id="f700f-169">If you install BizTalk on a 64 bit machine, change all instances of the HKEY_CLASSES_ROOT\CLSID\ registry entry to HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ in the **TransactionalAdmin.reg** registry file.</span></span>  
  
3.  <span data-ttu-id="f700f-170">**レジストリ エディター**ダイアログ ボックスで、をクリックして**はい**サンプル アダプターをレジストリに追加し、をクリックする**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-170">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="f700f-171">クリックして、Windows エクスプ ローラーを閉じます**ファイル**、クリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-171">To close Windows Explorer, click **File**, and then click **Close**.</span></span>  
  
#### <a name="add-the-transactional-adapter-to-biztalk-server"></a><span data-ttu-id="f700f-172">BizTalk Server へのトランザクション アダプターの追加</span><span class="sxs-lookup"><span data-stu-id="f700f-172">Add the Transactional Adapter to BizTalk Server</span></span>  
  
1.  <span data-ttu-id="f700f-173">クリックして、**開始**メニューの **すべてのプログラム**を選択[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、し、 **BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-173">Click the **Start** menu, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f700f-174">[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開、 **BizTalk Server 管理コンソール**ツリーで、展開、 **BizTalk グループ**ツリーを展開し、展開、**プラットフォームの設定**ツリー。</span><span class="sxs-lookup"><span data-stu-id="f700f-174">In the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the **BizTalk Server Administration** tree, expand the **BizTalk Group** tree, and then expand the **Platform Settings**  tree.</span></span>  
  
3.  <span data-ttu-id="f700f-175">右クリック**アダプター**をクリックして**新規**、順にクリック**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-175">Right-click **Adapters**, click **New**, and then click **Adapter**.</span></span>  
  
4.  <span data-ttu-id="f700f-176">**アダプター プロパティ** ダイアログ ボックスで、次の操作です。</span><span class="sxs-lookup"><span data-stu-id="f700f-176">In the **Adapter Properties** dialog box, do the following.</span></span>  
  
    |<span data-ttu-id="f700f-177">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f700f-177">Use this</span></span>|<span data-ttu-id="f700f-178">目的</span><span class="sxs-lookup"><span data-stu-id="f700f-178">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f700f-179">名前</span><span class="sxs-lookup"><span data-stu-id="f700f-179">Name</span></span>|<span data-ttu-id="f700f-180">型**TransactionalAdapter**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-180">Type **TransactionalAdapter**.</span></span>|  
    |<span data-ttu-id="f700f-181">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="f700f-181">Adapter</span></span>|<span data-ttu-id="f700f-182">選択**Txn**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="f700f-182">Select **Txn** from the drop-down list.</span></span> <span data-ttu-id="f700f-183">実行結果としてこのエントリが表示されます、 **TransactionalAdmin.reg**ファイルの以前です。</span><span class="sxs-lookup"><span data-stu-id="f700f-183">This entry appears as a result of running the **TransactionalAdmin.reg** file previously.</span></span>|  
    |<span data-ttu-id="f700f-184">Description</span><span class="sxs-lookup"><span data-stu-id="f700f-184">Description</span></span>|<span data-ttu-id="f700f-185">型**Transactional Adapter サンプル**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-185">Type **Sample Transactional Adapter**.</span></span>|  
  
5.  <span data-ttu-id="f700f-186">クリックして **OK.**</span><span class="sxs-lookup"><span data-stu-id="f700f-186">Click **OK.**</span></span> <span data-ttu-id="f700f-187">これで、BizTalk 管理コンソールの右ウィンドウにあるアダプターの一覧にアダプターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f700f-187">The adapter now appears in the list of adapters in the right window of the BizTalk Administration console.</span></span>  
  
#### <a name="create-a-receive-port-and-location-that-uses-the-adapter"></a><span data-ttu-id="f700f-188">アダプターを使用する受信ポートと受信場所の作成</span><span class="sxs-lookup"><span data-stu-id="f700f-188">Create a Receive Port and Location that uses the Adapter</span></span>  
  
1.  <span data-ttu-id="f700f-189">展開、 **BizTalk グループ [サーバー名]**内のノード[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**アプリケーション** ノードを展開**BizTalk アプリケーション 1**ノード。</span><span class="sxs-lookup"><span data-stu-id="f700f-189">Expand the **BizTalk Group[server name]** node in [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **Applications** node, expand **BizTalk Application 1** node.</span></span>  
  
2.  <span data-ttu-id="f700f-190">右クリック**受信ポート**、順にクリック**新規****一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="f700f-190">Right-click **Receive Ports**, and then click **New**, select **One-Way Receive Port.**</span></span>  
  
3.  <span data-ttu-id="f700f-191">**名**、入力**TxnReceivePort1**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-191">For **Name**, enter **TxnReceivePort1**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="f700f-192">右クリックし、**受信場所**ノード、をクリックして**新規**、し、**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-192">Right-click the **Receive Locations** node, click **New**, and then select **One-Way Receive Location**.</span></span>  
  
5.  <span data-ttu-id="f700f-193">**受信ポートの選択**ダイアログ ボックスで、 **TxnReceivePort1**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-193">In the**Select a Receive Port** dialog box, select **TxnReceivePort1**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="f700f-194">**受信場所のプロパティ**ダイアログ ボックスで、**全般** タブで、入力**TxnReceiveLocation1**の**名前**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-194">In the **Receive Location Properties** dialog box, under the **General** tab, enter **TxnReceiveLocation1** for **Name**.</span></span> <span data-ttu-id="f700f-195">確認してください、**受信ポート**表示にラベルを付ける**TxnReceivePort1**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-195">Ensure the **Receive Port** label displays **TxnReceivePort1**.</span></span>  
  
7.  <span data-ttu-id="f700f-196">**型**で、ボックスの一覧、**トランスポート**フレームで、 **TransactionalAdapter です。**</span><span class="sxs-lookup"><span data-stu-id="f700f-196">In the**Type** dropdown list box, in the **Transport** frame, select **TransactionalAdapter.**</span></span>  
  
8.  <span data-ttu-id="f700f-197">**受信 * * * パイプライン**ボックスで、確認**PassThruReceive**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="f700f-197">In the **Receive****Pipeline** box, ensure **PassThruReceive** is selected.</span></span> <span data-ttu-id="f700f-198">残りのプロパティは既定の設定のままにします。</span><span class="sxs-lookup"><span data-stu-id="f700f-198">Leave the rest of the properties with their default settings.</span></span>  
  
9. <span data-ttu-id="f700f-199">クリックして、**構成**横に、**型**ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f700f-199">Click the **Configure** button next to the **Type** drop down box.</span></span> <span data-ttu-id="f700f-200">これにより、このアダプターに固有のダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f700f-200">This displays a dialog specific to this adapter.</span></span> <span data-ttu-id="f700f-201">次のように、必要に応じて指定順にクリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-201">Specify the following as you see appropriate, then click **OK**.</span></span>  
  
    |<span data-ttu-id="f700f-202">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f700f-202">Property</span></span>|<span data-ttu-id="f700f-203">設定</span><span class="sxs-lookup"><span data-stu-id="f700f-203">Setting</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="f700f-204">接続文字列</span><span class="sxs-lookup"><span data-stu-id="f700f-204">Connection String</span></span>|<span data-ttu-id="f700f-205">Northwind データベースとの接続と認証に使用される SQL データベース接続文字列。</span><span class="sxs-lookup"><span data-stu-id="f700f-205">The SQL database connection string used to connect and authenticate with the Northwind database.</span></span> <span data-ttu-id="f700f-206">後でこのデータベースを使用する SQL スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f700f-206">We will later run a SQL script that will use this database.</span></span>|  
    |<span data-ttu-id="f700f-207">コマンド テキスト</span><span class="sxs-lookup"><span data-stu-id="f700f-207">Command Text</span></span>|<span data-ttu-id="f700f-208">Northwind データベースのデータを取得して BizTalk メッセージに格納するために、Northwind データベースに対して実行される SQL ステートメント。</span><span class="sxs-lookup"><span data-stu-id="f700f-208">The SQL statements that are executed against the Northwind database to obtain data to put into a BizTalk Message.</span></span>|  
    |<span data-ttu-id="f700f-209">Cookie</span><span class="sxs-lookup"><span data-stu-id="f700f-209">Cookie</span></span>|<span data-ttu-id="f700f-210">URI の一部を構成します。受信場所の名前 (TxnReceiveLocation1 など) のような一意の名前を入力してください。</span><span class="sxs-lookup"><span data-stu-id="f700f-210">Comprises part of the URI so enter a unique value, such as the name of the receive location, for instance: TxnReceiveLocation1.</span></span>|  
    |<span data-ttu-id="f700f-211">[ポーリング間隔の単位]</span><span class="sxs-lookup"><span data-stu-id="f700f-211">Polling Interval Unit</span></span>|<span data-ttu-id="f700f-212">データのポーリング時間の測定単位。</span><span class="sxs-lookup"><span data-stu-id="f700f-212">The number of units of time measure for the polling of the data.</span></span> <span data-ttu-id="f700f-213">"秒" に設定します。</span><span class="sxs-lookup"><span data-stu-id="f700f-213">Set this to seconds.</span></span>|  
    |<span data-ttu-id="f700f-214">ポーリング間隔</span><span class="sxs-lookup"><span data-stu-id="f700f-214">Polling Interval</span></span>|<span data-ttu-id="f700f-215">データのポーリング時間を示す数値。</span><span class="sxs-lookup"><span data-stu-id="f700f-215">The unit of time measure for the polling of the data.</span></span> <span data-ttu-id="f700f-216">15 秒に設定します。</span><span class="sxs-lookup"><span data-stu-id="f700f-216">Set this to 15 seconds.</span></span>|  
  
10. <span data-ttu-id="f700f-217">をクリックして**[ok]**を構成 ダイアログ ボックスを閉じ**OK**を閉じます、**受信場所のプロパティ** ダイアログ ボックスに戻るには、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f700f-217">Click **OK** to close the Configure dialog box, then **OK** again to close the **Receive Location Properties** dialog box to return to the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
#### <a name="create-a-send-port-and-send-handler-that-use-the-adapter"></a><span data-ttu-id="f700f-218">アダプターを使用する送信ポートと送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="f700f-218">Create a Send Port and Send Handler that use the Adapter</span></span>  
  
1.  <span data-ttu-id="f700f-219">**BizTalk アプリケーション 1**ノードが展開を右クリックして**送信ポート**、クリックして**新規**を選択し、**静的の一方向送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="f700f-219">With the **BizTalk Application 1** node still expanded, right-click **Send Ports**, and then click **New**, and select **Static One-Way Send Port**.</span></span>  
  
2.  <span data-ttu-id="f700f-220">**名前**フィールドに「 **TxnSendPort1**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-220">In the **Name** field, enter **TxnSendPort1**.</span></span>  
  
3.  <span data-ttu-id="f700f-221">**トランスポート**フレームの**型**ドロップダウン リストで、**TransactionalAdapter**`.`</span><span class="sxs-lookup"><span data-stu-id="f700f-221">In the **Transport** frame, in the **Type** drop-down list, select**TransactionalAdapter**`.`</span></span>  
  
4.  <span data-ttu-id="f700f-222">**送信パイプライン**ボックスで、確認**PassThruTransmit**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="f700f-222">In the **Send Pipeline** box, ensure **PassThruTransmit** is selected.</span></span>  
  
5.  <span data-ttu-id="f700f-223">クリックして、**構成**横に、**トランスポート**ドロップダウン リスト。表示されるダイアログ ボックスで、適切なように、次を指定し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-223">Click the **Configure** button next to the **transport** drop-down list.In the dialog that appears specify the following as you see appropriate, then click **OK**.</span></span>  
  
    |<span data-ttu-id="f700f-224">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f700f-224">Property</span></span>|<span data-ttu-id="f700f-225">設定</span><span class="sxs-lookup"><span data-stu-id="f700f-225">Setting</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="f700f-226">Cookie</span><span class="sxs-lookup"><span data-stu-id="f700f-226">Cookie</span></span>|<span data-ttu-id="f700f-227">一部を構成 - URI の値を入力して、一意ここで、受信場所の名前などのインスタンス: **TxnSendPort1**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-227">Comprises part of the URI - Enter a unique value here such as the name of the receive location, for instance: **TxnSendPort1**.</span></span>|  
    |<span data-ttu-id="f700f-228">接続文字列</span><span class="sxs-lookup"><span data-stu-id="f700f-228">Connection String</span></span>|<span data-ttu-id="f700f-229">Northwind データベースとの接続と認証に使用される SQL データベース接続文字列。</span><span class="sxs-lookup"><span data-stu-id="f700f-229">The SQL database connection string used to connect and authenticate with the Northwind database.</span></span> <span data-ttu-id="f700f-230">最も高くなります、構成に使用されるものと同じ、 **TxnReceiveLocation1**受信場所。</span><span class="sxs-lookup"><span data-stu-id="f700f-230">It will most likely be the same one used to configure the **TxnReceiveLocation1** receive location.</span></span>|  
    |<span data-ttu-id="f700f-231">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f700f-231">Stored Procedure</span></span>|<span data-ttu-id="f700f-232">ストアド プロシージャの名前のデータベースをポーリングするために実行を取得する**sp_txnProc**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-232">The stored procedure name that gets executed to poll the database - **sp_txnProc**.</span></span> <span data-ttu-id="f700f-233">という名前の文字列パラメーターとしてストアド プロシージャを BizTalk にメッセージを指定の本文@Dataです。</span><span class="sxs-lookup"><span data-stu-id="f700f-233">The body of the BizTalk message is given to that stored procedure as a string parameter called @Data.</span></span> <span data-ttu-id="f700f-234">たとえば、ユーザーはここでは後で構成ストアド プロシージャ、名前を持つ**sp_txnProc**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-234">For example, the user will in this case later configure the stored procedure with the name **sp_txnProc**.</span></span> <span data-ttu-id="f700f-235">アダプターのランタイムはデータベースに対しこの呼び出しと同等のものを実行します。</span><span class="sxs-lookup"><span data-stu-id="f700f-235">The runtime of the adapter would execute the equivalent of this call to the database.</span></span><br /><br /> <span data-ttu-id="f700f-236">exec sp_txnProc @Data 「BizTalk メッセージの内容」を =</span><span class="sxs-lookup"><span data-stu-id="f700f-236">exec sp_txnProc @Data = “the contents of the BizTalk message”</span></span>|  
  
6.  <span data-ttu-id="f700f-237">左側のナビゲーション ウィンドウで **フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-237">In the left navigation pane, click **Filter**.</span></span>  
  
7.  <span data-ttu-id="f700f-238">フィルター式エディターで、次の式を入力してこの送信ポートのサブスクリプションを設定し、TxnReceivePort1 受信ポートから受信されるすべてのメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="f700f-238">In the filter expression editor, enter the following expression to set up a subscription for this send port to receive any messages received by the TxnReceivePort1 receive port.</span></span>  
  
     <span data-ttu-id="f700f-239">これらの値を入力してください:**BTS です。ReceivePortName TxnReceivePort1 を = =**</span><span class="sxs-lookup"><span data-stu-id="f700f-239">Enter these values:**BTS.ReceivePortName== TxnReceivePort1**</span></span>  
  
    1.  <span data-ttu-id="f700f-240">`(property)`  **BTS です。ReceivePortName**</span><span class="sxs-lookup"><span data-stu-id="f700f-240">`(property)`  **BTS.ReceivePortName**</span></span>  
  
    2.  <span data-ttu-id="f700f-241">`(operator)`  **==**</span><span class="sxs-lookup"><span data-stu-id="f700f-241">`(operator)`  **==**</span></span>  
  
    3.  <span data-ttu-id="f700f-242">`(value)`  **TxnReceivePort1**</span><span class="sxs-lookup"><span data-stu-id="f700f-242">`(value)`  **TxnReceivePort1**</span></span>  
  
8.  <span data-ttu-id="f700f-243">アダプターのプロパティの残りの既定値を使用して選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-243">Use the default values for the remainder of the adapter properties and select **OK**.</span></span>  
  
## <a name="run-the-sample"></a><span data-ttu-id="f700f-244">サンプルの実行</span><span class="sxs-lookup"><span data-stu-id="f700f-244">Run the sample</span></span>  
  
1.  <span data-ttu-id="f700f-245">をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**Microsoft SQL Server 2008 R2** **SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="f700f-245">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, select **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="f700f-246">**サーバーへの接続** ダイアログ ボックスで確認**サーバーの種類**に設定されている**データベース エンジン**、データベース サーバーに認証する資格情報を入力し、の選択**接続**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-246">In the **Connect to Server** dialog box, make sure **Server Type** is set to **Database Engine**, and enter credentials to authenticate to the database server, then select **Connect**.</span></span>  
  
3.  <span data-ttu-id="f700f-247">選択、**新しいクエリ**ツールバーのボタンと貼り付け、次の点をテスト テーブル、テスト データ、およびテストを挿入する新しいクエリ ウィンドウをストアド プロシージャを Northwind データベースにします。</span><span class="sxs-lookup"><span data-stu-id="f700f-247">Select the **New Query** toolbar button and paste the following into the new query window to insert a test table, test data, and a test stored procedure into the Northwind database.</span></span> <span data-ttu-id="f700f-248">選択、 **Execute**ツールバー ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f700f-248">Select the **Execute** toolbar button.</span></span>  
  
    ```  
    use [Northwind]  
    GO  
    if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[scratch]') and OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    drop table [dbo].[scratch]  
    GO  
    CREATE TABLE [dbo].[scratch] (  
         [id] [int] IDENTITY (1, 1) NOT NULL ,  
         [msg] [nvarchar] (4000) NOT NULL   
    ) ON [PRIMARY]  
    GO  
    GRANT SELECT , UPDATE , INSERT ON [dbo].[scratch] TO [public]  
    GO  
    if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[sp_txnProc]') and OBJECTPROPERTY(id, N'IsProcedure') = 1)  
    drop procedure [dbo].[sp_txnProc]  
    GO  
    CREATE PROCEDURE [dbo].[sp_txnProc] @Data nvarchar (4000)  
    AS   
    INSERT scratch ( msg ) values ( @Data )  
    GO  
    GRANT EXECUTE ON [dbo].[sp_txnProc] TO [public]  
    GO  
    ```  
  
4.  <span data-ttu-id="f700f-249">[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開、**送信ポート**ノードで、選択、 **TxnSendPort1**送信ポート、および選択**開始**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-249">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the **Send Ports** node, select the **TxnSendPort1** send port, and select **Start**.</span></span>  
  
5.  <span data-ttu-id="f700f-250">[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開、 **ReceiveLocations**ノードで、選択、 **TxnRecieveLocation1**受信場所をクリックし **を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="f700f-250">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the **ReceiveLocations** node, select the **TxnRecieveLocation1** receive location, and then select **Enable**.</span></span>  
  
6.  <span data-ttu-id="f700f-251">受信場所を有効にすると、指定された間隔で自動的にデータベースがポーリングされ、データが変更されているかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="f700f-251">Once the receive location is enabled, it will automatically poll the database at the designated intervals for data.</span></span>  
  
## <a name="classes-or-methods-used-in-the-sample"></a><span data-ttu-id="f700f-252">クラスまたはメソッドが、サンプルで使用します。</span><span class="sxs-lookup"><span data-stu-id="f700f-252">Classes or Methods Used in the sample</span></span>  
* <span data-ttu-id="f700f-253">IBTTransmitterBatch インターフェイス (COM)</span><span class="sxs-lookup"><span data-stu-id="f700f-253">IBTTransmitterBatch Interface (COM)</span></span>
  
* <span data-ttu-id="f700f-254">IBTTransportProxy インターフェイス (COM)</span><span class="sxs-lookup"><span data-stu-id="f700f-254">IBTTransportProxy Interface (COM)</span></span>

<span data-ttu-id="f700f-255">これらの方法が説明されている[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f700f-255">These methods are described [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f700f-256">参照</span><span class="sxs-lookup"><span data-stu-id="f700f-256">See Also</span></span>  
 <span data-ttu-id="f700f-257">[アダプタ サンプル - 開発](../core/adapter-samples-development.md) </span><span class="sxs-lookup"><span data-stu-id="f700f-257">[Adapter Samples - Development](../core/adapter-samples-development.md) </span></span>  
 [<span data-ttu-id="f700f-258">アダプターの登録</span><span class="sxs-lookup"><span data-stu-id="f700f-258">Registering an Adapter</span></span>](../core/registering-an-adapter.md)