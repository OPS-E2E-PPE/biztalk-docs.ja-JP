---
title: TIBCO Rendezvous アダプターの送信の成果物を作成 |Microsoft ドキュメント
description: 送信ポートを作成、メッセージを TIBCO Rendezvous を BizTalk から送信するトランスポートのプロパティを構成します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad996c4f-e6ed-4582-a768-0cb1ad25b1d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6d03885423582c2657c9cb624c63f26ce1c6f3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014353"
---
# <a name="create-tibco-rendezvous-send-handlers"></a><span data-ttu-id="9e7d4-103">TIBCO Rendezvous 送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-103">Create TIBCO Rendezvous Send Handlers</span></span>
<span data-ttu-id="9e7d4-104">このセクションでは、スキーマを作成して BizTalk Server のオーケストレーションで TIBCO Rendezvous を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-104">This section explains how to create a schema to use TIBCO Rendezvous in a BizTalk Server orchestration.</span></span>  
  
## <a name="create-a-send-port"></a><span data-ttu-id="9e7d4-105">送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-105">Create a send port</span></span>
  
1.  <span data-ttu-id="9e7d4-106">**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-106">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="9e7d4-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="9e7d4-108">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="9e7d4-109">たとえば、送信ポートの名前を入力`SendToTIBCORV`です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-109">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="9e7d4-110">**型**ドロップダウン リストで、 **TIBCO Rendezvous**です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-110">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="9e7d4-111">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="9e7d4-112">送信パイプラインのドロップダウン リストから選択 **[microsoft.biztalk.defaultpipelines.xmltransmit]** です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  <span data-ttu-id="9e7d4-113">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="9e7d4-114">Microsoft BizTalk Adapter for TIBCO Rendezvous では、送信、XMLTransmit パイプラインと受信の XMLReceive パイプラインを選択することが必要です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-114">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you select XMLTransmit pipeline for send, and XMLReceive pipeline for receive.</span></span>
        
    6.  <span data-ttu-id="9e7d4-115">をクリックして**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-115">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="9e7d4-116">**TIBCO Rendezvous トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-116">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="9e7d4-117">プロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-117">Enter the properties.</span></span>  
  
         <span data-ttu-id="9e7d4-118">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-118">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="9e7d4-119">一覧で、TIBCO Rendezvous システムを表すように作成した SSO 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-119">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="9e7d4-120">**SSO を使用する\*\*\*\*はい**です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-120">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="9e7d4-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-121">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="9e7d4-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-122">Click **OK**.</span></span>  

## <a name="set-the-transport-properties"></a><span data-ttu-id="9e7d4-123">トランスポートのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-123">Set the transport properties</span></span>
<span data-ttu-id="9e7d4-124">TIBCO Rendezvous トランスポートのプロパティは、実行時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-124">The TIBCO Rendezvous Transport property is used for run time.</span></span> <span data-ttu-id="9e7d4-125">**トランスポートのプロパティ**、生成されたメッセージを公開する TIBCO Rendezvous ドメインを識別する接続パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-125">In the **Transport Properties**, you set the connection parameters that identify the TIBCO Rendezvous domain where you want to publish the generated messages.</span></span>  
  
 
1.  <span data-ttu-id="9e7d4-126">**TIBCO Rendezvous トランスポートのプロパティ**画面で、展開**証明された送信者プロパティ**し、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-126">On the **TIBCO Rendezvous Transport Properties** screen, expand **Certified Sender Properties** and enter the following information.</span></span>  
  
     ![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")  
  
    |<span data-ttu-id="9e7d4-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e7d4-127">Use this</span></span>|<span data-ttu-id="9e7d4-128">目的</span><span class="sxs-lookup"><span data-stu-id="9e7d4-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e7d4-129">**元帳の名前**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-129">**Ledger name**</span></span>|<span data-ttu-id="9e7d4-130">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-130">Default value is blank.</span></span> <span data-ttu-id="9e7d4-131">永続的な認証されたメッセージ配信に使用する台帳ファイル名。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-131">Ledger file name to use for persistent certified message delivery.</span></span> <span data-ttu-id="9e7d4-132">ローカル ドライブのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-132">Use local drives only.</span></span>|  
    |<span data-ttu-id="9e7d4-133">**再利用可能名**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-133">**Reusable name**</span></span>|<span data-ttu-id="9e7d4-134">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-134">Default value is blank.</span></span> <span data-ttu-id="9e7d4-135">認証されたメッセージ配信に使用する再利用可能な送信者名です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-135">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="9e7d4-136">この名前は、ネットワーク上のすべての認証されたメッセージの送信者名の中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-136">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
2.  <span data-ttu-id="9e7d4-137">展開**資格情報**し、サーバーに接続に関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-137">Expand **Credentials** and enter the following information for connection to the server.</span></span>  
  
    |<span data-ttu-id="9e7d4-138">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e7d4-138">Use this</span></span>|<span data-ttu-id="9e7d4-139">目的</span><span class="sxs-lookup"><span data-stu-id="9e7d4-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e7d4-140">**Password**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-140">**Password**</span></span>|<span data-ttu-id="9e7d4-141">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-141">Default value is blank.</span></span> <span data-ttu-id="9e7d4-142">Tibco Rendezvous デーモンにログインするためのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-142">Password for login to a Tibco Rendezvous daemon.</span></span>|  
    |<span data-ttu-id="9e7d4-143">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-143">**User name**</span></span>|<span data-ttu-id="9e7d4-144">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-144">Default value is blank.</span></span> <span data-ttu-id="9e7d4-145">Tibco Rendezvous デーモンで使用するユーザー名です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-145">User name for Tibco Rendezvous daemon.</span></span>|  
  
3.  <span data-ttu-id="9e7d4-146">展開**全般設定**と TIBCO Rendezvous サーバーに接続に関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-146">Expand **General Settings** and enter the following information for connection to the TIBCO Rendezvous server.</span></span>  
  
    |<span data-ttu-id="9e7d4-147">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e7d4-147">Use this</span></span>|<span data-ttu-id="9e7d4-148">目的</span><span class="sxs-lookup"><span data-stu-id="9e7d4-148">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e7d4-149">**コード ページ番号**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-149">**Code Page Number**</span></span>|<span data-ttu-id="9e7d4-150">既定値は 65001 (UTF-8 エンコーディングのコード ページ) です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-150">Default value is 65001 (code page for UTF-8 encoding).</span></span> <span data-ttu-id="9e7d4-151">これは、TIBCO Rendezvous SDK が文字列のエンコーディングに使用するコード ページです。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-151">This is the code page that the TIBCO Rendezvous SDK uses for String encoding.</span></span>|  
    |<span data-ttu-id="9e7d4-152">**既定のサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-152">**Default Subject Name**</span></span>|<span data-ttu-id="9e7d4-153">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-153">Default is empty.</span></span> <span data-ttu-id="9e7d4-154">サブジェクト名はオーケストレーションで設定されます。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-154">The subject name is set in the orchestration.</span></span> <span data-ttu-id="9e7d4-155">1 つの種類のメッセージに 1 つのポートを使用する場合、既定のサブジェクト名を指定でき、サブジェクト名プロパティを設定する必要をなくしてオーケストレーションを単純化できます。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-155">If a port is used for one message type, you can provide a default subject name, and you can simplify orchestrations by removing the need to set the Subject name property.</span></span>|  
    |<span data-ttu-id="9e7d4-156">**タイム バッチを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-156">**Enable Time Batch**</span></span>|<span data-ttu-id="9e7d4-157">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-157">Default value is False.</span></span> <span data-ttu-id="9e7d4-158">TIBCO Rendezvous のタイム バッチ機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-158">Enable/Disable TIBCO Rendezvous Time Batch feature.</span></span>|  
    |<span data-ttu-id="9e7d4-159">**サポートされていない型を文字列に対応付け**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-159">**Map Unsupported types to string**</span></span>|<span data-ttu-id="9e7d4-160">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-160">Default value is True.</span></span> <span data-ttu-id="9e7d4-161">True の場合、サポートされていない型はすべて文字列型にマップされます。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-161">If true, unsupported types are mapped to string if it is possible.</span></span> <span data-ttu-id="9e7d4-162">False の場合、実行時エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-162">If False, a run-time error is generated.</span></span>|  
    |<span data-ttu-id="9e7d4-163">**TIBCO Rendezvous アセンブリなど、バイナリ ファイルへのパス**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-163">**Path to Binaries, such as TIBCO Rendezvous assemblies**</span></span>|<span data-ttu-id="9e7d4-164">PATH 環境変数でまだ設定されていない場合は、この情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-164">Provide this information if it is not already in the PATH environment variable.</span></span>|  
    |<span data-ttu-id="9e7d4-165">**順序の保持**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-165">**Preserver Order**</span></span>|<span data-ttu-id="9e7d4-166">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-166">Default value is True.</span></span> <span data-ttu-id="9e7d4-167">ロジックで、メッセージを BizTalk Server から受信したときと同じ順序で TIBCO Rendezvous に送信できます。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-167">Enables logic to send messages to TIBCO Rendezvous in the same order they were received from BizTalk Server.</span></span> <span data-ttu-id="9e7d4-168">このパラメーターにより、同じ順序での公開が強制されますが、サブスクライバーが同じ順序で受信するということではありません。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-168">This parameter forces publishing in the same order; it does not mean that subscribers receive them in the same order.</span></span>|  
    |<span data-ttu-id="9e7d4-169">**送信ポートの識別子**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-169">**Send Port Identifier**</span></span>|<span data-ttu-id="9e7d4-170">この識別子は、このポートに関連付けられているログ メッセージに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-170">This identifier appears in log messages associated with this port.</span></span> <span data-ttu-id="9e7d4-171">これは、便宜上指定します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-171">It is provided as a convenience.</span></span>|  
  
4.  <span data-ttu-id="9e7d4-172">展開**Rendezvous トランスポート**TIBCO Rendezvous サーバーへの接続情報を入力し、**適用**、クリックして **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-172">Expand **Rendezvous Transport** and enter the information for connection to the TIBCO Rendezvous server, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="9e7d4-173">Microsoft BizTalk Adapter for TIBCO Rendezvous が TIBCO Rendezvous にアクセスできるようにするために接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-173">You must set connection parameters for Microsoft BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous.</span></span>  
  
    |<span data-ttu-id="9e7d4-174">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e7d4-174">Use this</span></span>|<span data-ttu-id="9e7d4-175">目的</span><span class="sxs-lookup"><span data-stu-id="9e7d4-175">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e7d4-176">**デーモン**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-176">**Daemon**</span></span>|<span data-ttu-id="9e7d4-177">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-177">Default is empty.</span></span><br /><br /> <span data-ttu-id="9e7d4-178">Rendezvous トランスポート デーモン パラメーター。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-178">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="9e7d4-179">**ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-179">**Network**</span></span>|<span data-ttu-id="9e7d4-180">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-180">Default is empty.</span></span><br /><br /> <span data-ttu-id="9e7d4-181">Rendezvous トランスポート ネットワーク パラメーター。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-181">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="9e7d4-182">**サービス**</span><span class="sxs-lookup"><span data-stu-id="9e7d4-182">**Service**</span></span>|<span data-ttu-id="9e7d4-183">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-183">Default is empty.</span></span><br /><br /> <span data-ttu-id="9e7d4-184">Rendezvous トランスポート サービス パラメーター。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-184">Rendezvous Transport Service parameter.</span></span>|  
  
5.  <span data-ttu-id="9e7d4-185">シングル サインオン (SSO) を使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-185">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="9e7d4-186">TIBCO Rendezvous システムにアクセスする方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-186">There are two methods that you can use to access the TIBCO Rendezvous system.</span></span> <span data-ttu-id="9e7d4-187">1 つは資格情報 ([ユーザー名] パラメーターと [パスワード] パラメーター) を使用する方法で、もう 1 つはシングル サインオン (SSO) を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-187">You can use Credentials (User Name and Password parameters) or Single Sign-On.</span></span>  
  
    1.  <span data-ttu-id="9e7d4-188">選択**はい**で、 **SSO を使用する**でのシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-188">Select **Yes** in the **Use SSO** to use Single Sign-On.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9e7d4-189">参照してください[セキュリティ](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)SSO をセットアップする方法についてはします。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-189">See [Security](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) for information about how to set up SSO.</span></span>  
  
    2.  <span data-ttu-id="9e7d4-190">一覧から関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-190">Select an affiliate application from the list.</span></span>  
  
         <span data-ttu-id="9e7d4-191">エンタープライズ シングル サインオン ツールで作成された関連アプリケーションは TIBCO Rendezvous などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-191">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO Rendezvous.</span></span> <span data-ttu-id="9e7d4-192">Microsoft BizTalk Adapter for TIBCO Rendezvous では、アプリケーション ユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-192">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the credentials of an application user.</span></span> <span data-ttu-id="9e7d4-193">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-193">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9e7d4-194">関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications1.md)です。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-194">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
6.  <span data-ttu-id="9e7d4-195">をクリックして**適用**、クリックして **[ok]** 接続情報を受け入れるように必要なすべての情報を提供するとします。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-195">Click **Apply**, and then click **OK** after providing all required information to accept the connection information.</span></span>  
  
     <span data-ttu-id="9e7d4-196">BizTalk Adapter for TIBCO Rendezvous にアクセスする TIBCO Rendezvous の接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e7d4-196">You must set connection parameters for BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous .</span></span>  


## <a name="next-steps"></a><span data-ttu-id="9e7d4-197">次の手順</span><span class="sxs-lookup"><span data-stu-id="9e7d4-197">Next steps</span></span>
  
-   [<span data-ttu-id="9e7d4-198">BizTalk Server からの TIBCO Rendezvous 送信ポートの使用</span><span class="sxs-lookup"><span data-stu-id="9e7d4-198">Using TIBCO Rendezvous Send Ports from BizTalk Server</span></span>](../core/using-tibco-rendezvous-send-ports-from-biztalk-server.md)  
  
-   [<span data-ttu-id="9e7d4-199">TIBCO Rendezvous での送信ハンドラーのデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="9e7d4-199">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)  
  
-   [<span data-ttu-id="9e7d4-200">BizTalk Server のメッセージ コンテキストのプロパティ (送信ハンドラー)</span><span class="sxs-lookup"><span data-stu-id="9e7d4-200">BizTalk Server Message Context Properties (Send Handlers)</span></span>](../core/biztalk-server-message-context-properties-send-handlers.md)