---
title: TIBCO Rendezvous アダプター送信アイテムの作成 |Microsoft Docs
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
ms.openlocfilehash: 6a267b9deac31d729d580cde79c62be96a612b4c
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "24014353"
---
# <a name="create-tibco-rendezvous-send-handlers"></a><span data-ttu-id="84b22-103">TIBCO Rendezvous 送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="84b22-103">Create TIBCO Rendezvous Send Handlers</span></span>
<span data-ttu-id="84b22-104">このセクションでは、スキーマを作成して BizTalk Server のオーケストレーションで TIBCO Rendezvous を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84b22-104">This section explains how to create a schema to use TIBCO Rendezvous in a BizTalk Server orchestration.</span></span>  
  
## <a name="create-a-send-port"></a><span data-ttu-id="84b22-105">送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="84b22-105">Create a send port</span></span>
  
1.  <span data-ttu-id="84b22-106">**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="84b22-106">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="84b22-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="84b22-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="84b22-108">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="84b22-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="84b22-109">たとえば、送信ポートの名前を入力`SendToTIBCORV`します。</span><span class="sxs-lookup"><span data-stu-id="84b22-109">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="84b22-110">**型**ドロップダウン リストで、 **TIBCO Rendezvous**します。</span><span class="sxs-lookup"><span data-stu-id="84b22-110">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="84b22-111">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="84b22-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="84b22-112">送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="84b22-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  <span data-ttu-id="84b22-113">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。</span><span class="sxs-lookup"><span data-stu-id="84b22-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="84b22-114">Microsoft BizTalk Adapter for TIBCO Rendezvous では、送信で XMLTransmit パイプラインと受信の XMLReceive パイプラインを選択することが必要です。</span><span class="sxs-lookup"><span data-stu-id="84b22-114">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you select XMLTransmit pipeline for send, and XMLReceive pipeline for receive.</span></span>
        
    6.  <span data-ttu-id="84b22-115">クリックして**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="84b22-115">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="84b22-116">**TIBCO Rendezvous トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="84b22-116">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="84b22-117">プロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="84b22-117">Enter the properties.</span></span>  
  
         <span data-ttu-id="84b22-118">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="84b22-118">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="84b22-119">一覧で、TIBCO Rendezvous システムを表すように作成した SSO 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="84b22-119">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="84b22-120">**SSO を使用**、**はい**します。</span><span class="sxs-lookup"><span data-stu-id="84b22-120">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="84b22-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84b22-121">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="84b22-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84b22-122">Click **OK**.</span></span>  

## <a name="set-the-transport-properties"></a><span data-ttu-id="84b22-123">トランスポートのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="84b22-123">Set the transport properties</span></span>
<span data-ttu-id="84b22-124">TIBCO Rendezvous トランスポートのプロパティは、実行時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="84b22-124">The TIBCO Rendezvous Transport property is used for run time.</span></span> <span data-ttu-id="84b22-125">**トランスポートのプロパティ**、生成されたメッセージを公開する TIBCO Rendezvous ドメインを識別する接続パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="84b22-125">In the **Transport Properties**, you set the connection parameters that identify the TIBCO Rendezvous domain where you want to publish the generated messages.</span></span>  
  
 
1.  <span data-ttu-id="84b22-126">**TIBCO Rendezvous トランスポートのプロパティ**画面で、展開**証明された送信者プロパティ**し、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="84b22-126">On the **TIBCO Rendezvous Transport Properties** screen, expand **Certified Sender Properties** and enter the following information.</span></span>  
  
     <span data-ttu-id="84b22-127">![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")</span><span class="sxs-lookup"><span data-stu-id="84b22-127">![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")</span></span>  
  
    |<span data-ttu-id="84b22-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="84b22-128">Use this</span></span>|<span data-ttu-id="84b22-129">目的</span><span class="sxs-lookup"><span data-stu-id="84b22-129">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="84b22-130">**元帳の名前**</span><span class="sxs-lookup"><span data-stu-id="84b22-130">**Ledger name**</span></span>|<span data-ttu-id="84b22-131">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="84b22-131">Default value is blank.</span></span> <span data-ttu-id="84b22-132">永続的な認証されたメッセージ配信に使用する台帳ファイル名。</span><span class="sxs-lookup"><span data-stu-id="84b22-132">Ledger file name to use for persistent certified message delivery.</span></span> <span data-ttu-id="84b22-133">ローカル ドライブのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="84b22-133">Use local drives only.</span></span>|  
    |<span data-ttu-id="84b22-134">**再利用可能な名前**</span><span class="sxs-lookup"><span data-stu-id="84b22-134">**Reusable name**</span></span>|<span data-ttu-id="84b22-135">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="84b22-135">Default value is blank.</span></span> <span data-ttu-id="84b22-136">認証されたメッセージ配信に使用する再利用可能な送信者名です。</span><span class="sxs-lookup"><span data-stu-id="84b22-136">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="84b22-137">この名前は、ネットワーク上のすべての認証されたメッセージの送信者名の中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="84b22-137">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
2.  <span data-ttu-id="84b22-138">展開**資格情報**しサーバーへの接続に関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="84b22-138">Expand **Credentials** and enter the following information for connection to the server.</span></span>  
  
    |<span data-ttu-id="84b22-139">プロパティ</span><span class="sxs-lookup"><span data-stu-id="84b22-139">Use this</span></span>|<span data-ttu-id="84b22-140">目的</span><span class="sxs-lookup"><span data-stu-id="84b22-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="84b22-141">**Password**</span><span class="sxs-lookup"><span data-stu-id="84b22-141">**Password**</span></span>|<span data-ttu-id="84b22-142">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="84b22-142">Default value is blank.</span></span> <span data-ttu-id="84b22-143">Tibco Rendezvous デーモンにログインするためのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="84b22-143">Password for login to a Tibco Rendezvous daemon.</span></span>|  
    |<span data-ttu-id="84b22-144">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="84b22-144">**User name**</span></span>|<span data-ttu-id="84b22-145">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="84b22-145">Default value is blank.</span></span> <span data-ttu-id="84b22-146">Tibco Rendezvous デーモンで使用するユーザー名です。</span><span class="sxs-lookup"><span data-stu-id="84b22-146">User name for Tibco Rendezvous daemon.</span></span>|  
  
3.  <span data-ttu-id="84b22-147">展開**全般設定**し、TIBCO Rendezvous サーバーへの接続に関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="84b22-147">Expand **General Settings** and enter the following information for connection to the TIBCO Rendezvous server.</span></span>  
  
    |<span data-ttu-id="84b22-148">プロパティ</span><span class="sxs-lookup"><span data-stu-id="84b22-148">Use this</span></span>|<span data-ttu-id="84b22-149">目的</span><span class="sxs-lookup"><span data-stu-id="84b22-149">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="84b22-150">**コード ページ番号**</span><span class="sxs-lookup"><span data-stu-id="84b22-150">**Code Page Number**</span></span>|<span data-ttu-id="84b22-151">既定値は 65001 (UTF-8 エンコーディングのコード ページ) です。</span><span class="sxs-lookup"><span data-stu-id="84b22-151">Default value is 65001 (code page for UTF-8 encoding).</span></span> <span data-ttu-id="84b22-152">これは、TIBCO Rendezvous SDK が文字列のエンコーディングに使用するコード ページです。</span><span class="sxs-lookup"><span data-stu-id="84b22-152">This is the code page that the TIBCO Rendezvous SDK uses for String encoding.</span></span>|  
    |<span data-ttu-id="84b22-153">**既定のサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="84b22-153">**Default Subject Name**</span></span>|<span data-ttu-id="84b22-154">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="84b22-154">Default is empty.</span></span> <span data-ttu-id="84b22-155">サブジェクト名はオーケストレーションで設定されます。</span><span class="sxs-lookup"><span data-stu-id="84b22-155">The subject name is set in the orchestration.</span></span> <span data-ttu-id="84b22-156">1 つの種類のメッセージに 1 つのポートを使用する場合、既定のサブジェクト名を指定でき、サブジェクト名プロパティを設定する必要をなくしてオーケストレーションを単純化できます。</span><span class="sxs-lookup"><span data-stu-id="84b22-156">If a port is used for one message type, you can provide a default subject name, and you can simplify orchestrations by removing the need to set the Subject name property.</span></span>|  
    |<span data-ttu-id="84b22-157">**タイム バッチを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="84b22-157">**Enable Time Batch**</span></span>|<span data-ttu-id="84b22-158">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="84b22-158">Default value is False.</span></span> <span data-ttu-id="84b22-159">TIBCO Rendezvous のタイム バッチ機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="84b22-159">Enable/Disable TIBCO Rendezvous Time Batch feature.</span></span>|  
    |<span data-ttu-id="84b22-160">**サポートされていない型を文字列にマップします。**</span><span class="sxs-lookup"><span data-stu-id="84b22-160">**Map Unsupported types to string**</span></span>|<span data-ttu-id="84b22-161">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="84b22-161">Default value is True.</span></span> <span data-ttu-id="84b22-162">True の場合、サポートされていない型はすべて文字列型にマップされます。</span><span class="sxs-lookup"><span data-stu-id="84b22-162">If true, unsupported types are mapped to string if it is possible.</span></span> <span data-ttu-id="84b22-163">False の場合、実行時エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="84b22-163">If False, a run-time error is generated.</span></span>|  
    |<span data-ttu-id="84b22-164">**TIBCO Rendezvous アセンブリなどのバイナリのパス**</span><span class="sxs-lookup"><span data-stu-id="84b22-164">**Path to Binaries, such as TIBCO Rendezvous assemblies**</span></span>|<span data-ttu-id="84b22-165">PATH 環境変数でまだ設定されていない場合は、この情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="84b22-165">Provide this information if it is not already in the PATH environment variable.</span></span>|  
    |<span data-ttu-id="84b22-166">**順序の保持**</span><span class="sxs-lookup"><span data-stu-id="84b22-166">**Preserver Order**</span></span>|<span data-ttu-id="84b22-167">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="84b22-167">Default value is True.</span></span> <span data-ttu-id="84b22-168">ロジックで、メッセージを BizTalk Server から受信したときと同じ順序で TIBCO Rendezvous に送信できます。</span><span class="sxs-lookup"><span data-stu-id="84b22-168">Enables logic to send messages to TIBCO Rendezvous in the same order they were received from BizTalk Server.</span></span> <span data-ttu-id="84b22-169">このパラメーターにより、同じ順序での公開が強制されますが、サブスクライバーが同じ順序で受信するということではありません。</span><span class="sxs-lookup"><span data-stu-id="84b22-169">This parameter forces publishing in the same order; it does not mean that subscribers receive them in the same order.</span></span>|  
    |<span data-ttu-id="84b22-170">**送信ポートの識別子**</span><span class="sxs-lookup"><span data-stu-id="84b22-170">**Send Port Identifier**</span></span>|<span data-ttu-id="84b22-171">この識別子は、このポートに関連付けられているログ メッセージに表示されます。</span><span class="sxs-lookup"><span data-stu-id="84b22-171">This identifier appears in log messages associated with this port.</span></span> <span data-ttu-id="84b22-172">これは、便宜上指定します。</span><span class="sxs-lookup"><span data-stu-id="84b22-172">It is provided as a convenience.</span></span>|  
  
4.  <span data-ttu-id="84b22-173">展開**Rendezvous トランスポート**TIBCO Rendezvous サーバーに接続の情報を入力し、**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="84b22-173">Expand **Rendezvous Transport** and enter the information for connection to the TIBCO Rendezvous server, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="84b22-174">Microsoft BizTalk Adapter for TIBCO Rendezvous が TIBCO Rendezvous にアクセスできるようにするために接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84b22-174">You must set connection parameters for Microsoft BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous.</span></span>  
  
    |<span data-ttu-id="84b22-175">プロパティ</span><span class="sxs-lookup"><span data-stu-id="84b22-175">Use this</span></span>|<span data-ttu-id="84b22-176">目的</span><span class="sxs-lookup"><span data-stu-id="84b22-176">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="84b22-177">**デーモン**</span><span class="sxs-lookup"><span data-stu-id="84b22-177">**Daemon**</span></span>|<span data-ttu-id="84b22-178">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="84b22-178">Default is empty.</span></span><br /><br /> <span data-ttu-id="84b22-179">Rendezvous トランスポート デーモン パラメーター。</span><span class="sxs-lookup"><span data-stu-id="84b22-179">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="84b22-180">**Network**</span><span class="sxs-lookup"><span data-stu-id="84b22-180">**Network**</span></span>|<span data-ttu-id="84b22-181">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="84b22-181">Default is empty.</span></span><br /><br /> <span data-ttu-id="84b22-182">Rendezvous トランスポート ネットワーク パラメーター。</span><span class="sxs-lookup"><span data-stu-id="84b22-182">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="84b22-183">**サービス**</span><span class="sxs-lookup"><span data-stu-id="84b22-183">**Service**</span></span>|<span data-ttu-id="84b22-184">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="84b22-184">Default is empty.</span></span><br /><br /> <span data-ttu-id="84b22-185">Rendezvous トランスポート サービス パラメーター。</span><span class="sxs-lookup"><span data-stu-id="84b22-185">Rendezvous Transport Service parameter.</span></span>|  
  
5.  <span data-ttu-id="84b22-186">シングル サインオン (SSO) を使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="84b22-186">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="84b22-187">TIBCO Rendezvous システムにアクセスする方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="84b22-187">There are two methods that you can use to access the TIBCO Rendezvous system.</span></span> <span data-ttu-id="84b22-188">1 つは資格情報 ([ユーザー名] パラメーターと [パスワード] パラメーター) を使用する方法で、もう 1 つはシングル サインオン (SSO) を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="84b22-188">You can use Credentials (User Name and Password parameters) or Single Sign-On.</span></span>  
  
    1.  <span data-ttu-id="84b22-189">選択**はい**で、**を使用して SSO**でシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="84b22-189">Select **Yes** in the **Use SSO** to use Single Sign-On.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="84b22-190">参照してください[セキュリティ](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)SSO を設定する方法についてはします。</span><span class="sxs-lookup"><span data-stu-id="84b22-190">See [Security](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) for information about how to set up SSO.</span></span>  
  
    2.  <span data-ttu-id="84b22-191">一覧から関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="84b22-191">Select an affiliate application from the list.</span></span>  
  
         <span data-ttu-id="84b22-192">エンタープライズ シングル サインオン ツールで作成された関連アプリケーションは TIBCO Rendezvous などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="84b22-192">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO Rendezvous.</span></span> <span data-ttu-id="84b22-193">Microsoft BizTalk Adapter for TIBCO Rendezvous では、アプリケーション ユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="84b22-193">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the credentials of an application user.</span></span> <span data-ttu-id="84b22-194">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="84b22-194">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="84b22-195">関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications1.md)します。</span><span class="sxs-lookup"><span data-stu-id="84b22-195">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
6.  <span data-ttu-id="84b22-196">クリックして**適用**、順にクリックします**OK**接続情報を受け入れるように必要なすべての情報を入力したら。</span><span class="sxs-lookup"><span data-stu-id="84b22-196">Click **Apply**, and then click **OK** after providing all required information to accept the connection information.</span></span>  
  
     <span data-ttu-id="84b22-197">BizTalk Adapter for TIBCO Rendezvous にアクセスする TIBCO Rendezvous の接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84b22-197">You must set connection parameters for BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous .</span></span>  


## <a name="next-steps"></a><span data-ttu-id="84b22-198">次の手順</span><span class="sxs-lookup"><span data-stu-id="84b22-198">Next steps</span></span>
  
-   [<span data-ttu-id="84b22-199">BizTalk Server からの TIBCO Rendezvous 送信ポートの使用</span><span class="sxs-lookup"><span data-stu-id="84b22-199">Using TIBCO Rendezvous Send Ports from BizTalk Server</span></span>](../core/using-tibco-rendezvous-send-ports-from-biztalk-server.md)  
  
-   [<span data-ttu-id="84b22-200">TIBCO Rendezvous での送信ハンドラーのデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="84b22-200">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)  
  
-   [<span data-ttu-id="84b22-201">BizTalk Server のメッセージ コンテキストのプロパティ (送信ハンドラー)</span><span class="sxs-lookup"><span data-stu-id="84b22-201">BizTalk Server Message Context Properties (Send Handlers)</span></span>](../core/biztalk-server-message-context-properties-send-handlers.md)