---
title: "チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用してデータを受信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58e7a739-701d-4085-a840-54f81c55e943
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de436413f10cf4882b5c4e4b21af7bac6a3234c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a><span data-ttu-id="35091-102">チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用したデータの受信</span><span class="sxs-lookup"><span data-stu-id="35091-102">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Receive Data</span></span>
<span data-ttu-id="35091-103">BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システムからデータを受信できます。</span><span class="sxs-lookup"><span data-stu-id="35091-103">You can use the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="35091-104">このチュートリアルでは、これを示す SDK サンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="35091-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="35091-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="35091-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="35091-106">このサンプルをビルドして展開するには、アダプターが実行されている [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="35091-106">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="35091-107">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="35091-107">What This Sample Does</span></span>  
 <span data-ttu-id="35091-108">このサンプルでは、BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システムからデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="35091-108">This sample uses the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="35091-109">オーケストレーションがメッセージを処理し、ファイル アダプターを使用して、指定されたフォルダーにデータを XML ファイルとして書き込みます。</span><span class="sxs-lookup"><span data-stu-id="35091-109">An orchestration processes the message and, using the file adapter, writes the data as an XML file in a specified folder.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="35091-110">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="35091-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="35091-111">このサンプルは、[!INCLUDE[vs2010](../includes/vs2010-md.md)] でデザインされ、BizTalk Adapter for TIBCO Enterprise Message Service を BizTalk オーケストレーションと組み合わせて使用する基本的な機能を紹介する目的で作成されました。</span><span class="sxs-lookup"><span data-stu-id="35091-111">This sample, designed in [!INCLUDE[vs2010](../includes/vs2010-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35091-112">このサンプルでは、処理するアプリケーション用の TIBCO からメッセージを送信する方法を理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="35091-112">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="35091-113">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="35091-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="35091-114">このサンプルの既定の場所は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="35091-114">The default location for the sample is</span></span>  
  
 <span data-ttu-id="35091-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive</span><span class="sxs-lookup"><span data-stu-id="35091-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive</span></span>  
  
 <span data-ttu-id="35091-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="35091-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="35091-117">**ランタイム プロジェクト ファイル名**</span><span class="sxs-lookup"><span data-stu-id="35091-117">**Runtime Project Filename**</span></span>|<span data-ttu-id="35091-118">**ランタイム プロジェクト ファイルの説明**</span><span class="sxs-lookup"><span data-stu-id="35091-118">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="35091-119">OneWayReceive.btproj、</span><span class="sxs-lookup"><span data-stu-id="35091-119">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="35091-120">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="35091-120">OneWayReceive.sln</span></span>|<span data-ttu-id="35091-121">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="35091-121">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="35091-122">PureMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="35091-122">PureMessage.xsd,</span></span>|<span data-ttu-id="35091-123">アプリケーションのスキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="35091-123">Schema file for the application.</span></span>|  
|<span data-ttu-id="35091-124">TIBCORvOWR.odx</span><span class="sxs-lookup"><span data-stu-id="35091-124">TIBCORvOWR.odx</span></span>|<span data-ttu-id="35091-125">アプリケーションが使用するオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="35091-125">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="35091-126">TIBCORv.snk</span><span class="sxs-lookup"><span data-stu-id="35091-126">TIBCORv.snk</span></span>|<span data-ttu-id="35091-127">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="35091-127">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="35091-128">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="35091-128">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="35091-129">BizTalk Adapter for TIBCO Rendezvous の新しいインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="35091-129">Create a new instance of the BizTalk Adapter for TIBCO Rendezvous</span></span>  
  
1.  <span data-ttu-id="35091-130">起動して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="35091-130">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="35091-131">をクリックして**開始**、**すべてのプログラム**、 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="35091-131">Click **Start**, **All Programs**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="35091-132">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**プラットフォームの設定**、クリックして**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="35091-132">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="35091-133">右クリック**アダプター**を指す**新規**、**アダプターしています.**</span><span class="sxs-lookup"><span data-stu-id="35091-133">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="35091-134">表示する、**アダプター プロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="35091-134">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="35091-135">値を入力して、**名前**フィールド、たとえば**TIBCO Rendezvous**です。</span><span class="sxs-lookup"><span data-stu-id="35091-135">Enter a value for the **Name** field, for example **TIBCO Rendezvous**.</span></span>  
  
5.  <span data-ttu-id="35091-136">選択**TIBCO(r) Rendezvous(r)**で利用可能なアダプターの一覧から、**アダプター**ドロップダウン リスト をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="35091-136">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-port"></a><span data-ttu-id="35091-137">BizTalk 受信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="35091-137">Create a BizTalk Receive Port</span></span>  
  
1.  <span data-ttu-id="35091-138">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="35091-138">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="35091-139">受信ポート フォルダーを右クリックし、をクリックして**新規**、**一方向の受信ポートしています.**を表示する、**受信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="35091-139">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the **Receive Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="35091-140">値を入力、**名前**フィールド、たとえば**TIBCORvOneWayRP**、 をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="35091-140">Enter a value for the **Name** field, for example **TIBCORvOneWayRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-location"></a><span data-ttu-id="35091-141">BizTalk の受信場所を作成する</span><span class="sxs-lookup"><span data-stu-id="35091-141">Create a BizTalk Receive Location</span></span>  
  
1.  <span data-ttu-id="35091-142">右クリックし、新しい受信ポートをクリックし、**新規**、**受信場所の追加.**</span><span class="sxs-lookup"><span data-stu-id="35091-142">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="35091-143">表示する、**受信場所のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="35091-143">to display the **Receive Location Properties** dialog.</span></span>  
  
2.  <span data-ttu-id="35091-144">値を入力して、**名前**フィールド、たとえば**TIBCORvOneWayRL**です。</span><span class="sxs-lookup"><span data-stu-id="35091-144">Enter a value for the **Name** field, for example **TIBCORvOneWayRL**.</span></span>  
  
3.  <span data-ttu-id="35091-145">使用可能なアダプターの一覧から TIBCO Rendezvous アダプターを選択して、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="35091-145">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35091-146">この値は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで TIBCO アダプターを作成したときに指定した名前です。</span><span class="sxs-lookup"><span data-stu-id="35091-146">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="35091-147">値を入力して、 **RendezvousSubjectName**下にある、 **AdapterRequiredProperties**です。</span><span class="sxs-lookup"><span data-stu-id="35091-147">Enter a value for the **RendezvousSubjectName** under the **AdapterRequiredProperties**.</span></span>  
  
5.  <span data-ttu-id="35091-148">値を入力して、**証明されたリスナーのプロパティ**:</span><span class="sxs-lookup"><span data-stu-id="35091-148">Enter values for the **Certified Listener Properties**:</span></span>  
  
    |<span data-ttu-id="35091-149">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="35091-149">**Property**</span></span>|<span data-ttu-id="35091-150">**値**</span><span class="sxs-lookup"><span data-stu-id="35091-150">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="35091-151">台帳ファイル名</span><span class="sxs-lookup"><span data-stu-id="35091-151">Ledger file name</span></span>|<span data-ttu-id="35091-152">永続的な認証されたメッセージ配信に使用する台帳ファイル名。</span><span class="sxs-lookup"><span data-stu-id="35091-152">Ledger file name to use for persistent certified message delivery.</span></span>|  
    |<span data-ttu-id="35091-153">再利用可能な名前</span><span class="sxs-lookup"><span data-stu-id="35091-153">Reusable name</span></span>|<span data-ttu-id="35091-154">認証されたメッセージ配信に使用する再利用可能な送信者名です。</span><span class="sxs-lookup"><span data-stu-id="35091-154">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="35091-155">この名前は、ネットワーク上のすべての認証されたメッセージの送信者名の中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="35091-155">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
6.  <span data-ttu-id="35091-156">値を入力して、**資格情報**:</span><span class="sxs-lookup"><span data-stu-id="35091-156">Enter values for the **Credentials**:</span></span>  
  
    |<span data-ttu-id="35091-157">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="35091-157">**Property**</span></span>|<span data-ttu-id="35091-158">**値**</span><span class="sxs-lookup"><span data-stu-id="35091-158">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="35091-159">Password</span><span class="sxs-lookup"><span data-stu-id="35091-159">Password</span></span>|<span data-ttu-id="35091-160">TIBCO Rendezvous サーバーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="35091-160">The password for the TIBCO Rendezvous server.</span></span>|  
    |<span data-ttu-id="35091-161">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="35091-161">User name</span></span>|<span data-ttu-id="35091-162">TIBCO Rendezvous サーバーのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="35091-162">The user name for the TIBCO Rendezvous server.</span></span>|  
  
7.  <span data-ttu-id="35091-163">値を入力して、 **RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="35091-163">Enter values for the **RendezvousTransport**:</span></span>  
  
    |<span data-ttu-id="35091-164">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="35091-164">**Property**</span></span>|<span data-ttu-id="35091-165">**値**</span><span class="sxs-lookup"><span data-stu-id="35091-165">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="35091-166">デーモン</span><span class="sxs-lookup"><span data-stu-id="35091-166">Daemon</span></span>|<span data-ttu-id="35091-167">Rendezvous トランスポート デーモン パラメーター。</span><span class="sxs-lookup"><span data-stu-id="35091-167">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="35091-168">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="35091-168">Network</span></span>|<span data-ttu-id="35091-169">Rendezvous トランスポート ネットワーク パラメーター。</span><span class="sxs-lookup"><span data-stu-id="35091-169">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="35091-170">サービス</span><span class="sxs-lookup"><span data-stu-id="35091-170">Service</span></span>|<span data-ttu-id="35091-171">Rendezvous トランスポート サービス パラメーター。</span><span class="sxs-lookup"><span data-stu-id="35091-171">Rendezvous Transport Service parameter.</span></span>|  
  
     <span data-ttu-id="35091-172">プロパティの詳細については、次を参照してください。[設定 TIBCO Rendezvous 受信トランスポートのプロパティ](../core/setting-tibco-rendezvous-receive-transport-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="35091-172">For more information about the properties, see [Setting TIBCO Rendezvous Receive Transport Properties](../core/setting-tibco-rendezvous-receive-transport-properties.md).</span></span>  
  
8.  <span data-ttu-id="35091-173">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35091-173">Click **OK**.</span></span>  
  
9. <span data-ttu-id="35091-174">選択**[xmlreceive]**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン リスト ボックスし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="35091-174">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
10. <span data-ttu-id="35091-175">受信場所を右クリックし、をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="35091-175">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="create-a-one-way-file-send-port"></a><span data-ttu-id="35091-176">一方向 FILE 送信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="35091-176">Create a one-way file send port</span></span>  
  
1.  <span data-ttu-id="35091-177">送信ポートが使用する送信先フォルダー (たとえば、C:\FilesOut) を作成します。</span><span class="sxs-lookup"><span data-stu-id="35091-177">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  
  
2.  <span data-ttu-id="35091-178">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="35091-178">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="35091-179">右クリック**送信ポート**を指す**新規**、**静的な一方向送信ポートしています.**</span><span class="sxs-lookup"><span data-stu-id="35091-179">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="35091-180">表示する、**送信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="35091-180">to display the **Send Port Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="35091-181">値を入力して、**名前**フィールド、たとえば**TIBCORvOneWayFileSP**です。</span><span class="sxs-lookup"><span data-stu-id="35091-181">Enter a value for the **Name** field, for example **TIBCORvOneWayFileSP**.</span></span>  
  
5.  <span data-ttu-id="35091-182">選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="35091-182">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
6.  <span data-ttu-id="35091-183">**コピー先フォルダー**プロパティ、先ほど作成したフォルダーの場所を入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="35091-183">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  
  
7.  <span data-ttu-id="35091-184">選択、 **xmltransmit**パイプラインで使用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン リスト をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="35091-184">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
8.  <span data-ttu-id="35091-185">送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="35091-185">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="35091-186">プロジェクトのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="35091-186">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="35091-187">ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="35091-187">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="35091-188">クリックして、**展開**タブです。</span><span class="sxs-lookup"><span data-stu-id="35091-188">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="35091-189">適切な値を入力、**サーバー**プロパティおよび**構成データベース**プロパティの  **BizTalk グループ**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="35091-189">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  
  
4.  <span data-ttu-id="35091-190">ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**展開**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。</span><span class="sxs-lookup"><span data-stu-id="35091-190">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="35091-191">オーケストレーションをバインドして参加させる</span><span class="sxs-lookup"><span data-stu-id="35091-191">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="35091-192">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="35091-192">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="35091-193">をクリックして、**更新**ボタンをクリックして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール ツールバーまたはキーを押して、 **f5 キーを押して**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。</span><span class="sxs-lookup"><span data-stu-id="35091-193">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="35091-194">表示するオーケストレーションをダブルクリック、**オーケストレーションのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="35091-194">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="35091-195">をクリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左ペインでします。</span><span class="sxs-lookup"><span data-stu-id="35091-195">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="35091-196">バインド オプションに適切な値を指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="35091-196">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="35091-197">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="35091-197">**Parameter**</span></span>|<span data-ttu-id="35091-198">**値**</span><span class="sxs-lookup"><span data-stu-id="35091-198">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="35091-199">Host</span><span class="sxs-lookup"><span data-stu-id="35091-199">Host</span></span>|<span data-ttu-id="35091-200">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="35091-200">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="35091-201">SendPort</span><span class="sxs-lookup"><span data-stu-id="35091-201">SendPort</span></span>|<span data-ttu-id="35091-202">TIBCORvOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="35091-202">TIBCORvOneWayFileSP</span></span>|  
    |<span data-ttu-id="35091-203">ReceivePort</span><span class="sxs-lookup"><span data-stu-id="35091-203">ReceivePort</span></span>|<span data-ttu-id="35091-204">TIBCORvOneWayRP</span><span class="sxs-lookup"><span data-stu-id="35091-204">TIBCORvOneWayRP</span></span>|  
  
6.  <span data-ttu-id="35091-205">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35091-205">Click **OK**.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="35091-206">オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="35091-206">Start the orchestration</span></span>  
  
-   <span data-ttu-id="35091-207">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、オーケストレーションを右クリックし、をクリックして**開始**を参加させて、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="35091-207">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="verify-that-the-application-receives-a-message"></a><span data-ttu-id="35091-208">アプリケーションがメッセージを受信することの確認</span><span class="sxs-lookup"><span data-stu-id="35091-208">Verify that the application receives a message</span></span>  
  
-   <span data-ttu-id="35091-209">ファイル送信ポートの送信先として構成されているフォルダーを開いて、出力ドキュメントが生成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="35091-209">Open the folder that the file send port is configured to send to and verify that an output document was generated.</span></span>  
  
 <span data-ttu-id="35091-210">ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="35091-210">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="35091-211">TIBCO Rendezvous アダプターが TIBCO システムからメッセージを取得し、BizTalk メッセージとしてメッセージ ボックスに公開します。</span><span class="sxs-lookup"><span data-stu-id="35091-211">The TIBCO Rendezvous adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="35091-212">オーケストレーションがこの公開されたメッセージをサブスクライブします。これにより、BizTalk メッセージング エンジンがオーケストレーションのインスタンスをアクティブ化し、オーケストレーション インスタンスにメッセージを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="35091-212">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="35091-213">オーケストレーション インスタンスがメッセージ ボックスにメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="35091-213">The orchestration instance publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="35091-214">ファイル送信ポートがこのメッセージをサブスクライブし、BizTalk がメッセージをファイル アダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="35091-214">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  
  
5.  <span data-ttu-id="35091-215">ファイル アダプターが、結果セットを含むメッセージを指定の出力フォルダーに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="35091-215">The File adapter writes the message containing the result set to the designated output folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35091-216">参照</span><span class="sxs-lookup"><span data-stu-id="35091-216">See Also</span></span>  
 <span data-ttu-id="35091-217">[チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用してデータを送信するには](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="35091-217">[Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span></span>  
 <span data-ttu-id="35091-218">[チュートリアル: Microsoft BizTalk Adapter を使用して TIBCO Rendezvous の](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="35091-218">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="35091-219">作業の開始</span><span class="sxs-lookup"><span data-stu-id="35091-219">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)