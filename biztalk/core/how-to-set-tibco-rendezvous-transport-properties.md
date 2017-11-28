---
title: "TIBCO Rendezvous トランスポートのプロパティを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting transport properties
- transport properties, setting
ms.assetid: db8e8a57-a942-44d7-a651-623aa614c6be
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9ff40d5319daa0a71d67aa3fd132c3d115923e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-tibco-rendezvous-transport-properties"></a><span data-ttu-id="e70b1-102">TIBCO Rendezvous トランスポートのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="e70b1-102">How to Set TIBCO Rendezvous Transport Properties</span></span>
<span data-ttu-id="e70b1-103">TIBCO Rendezvous トランスポートのプロパティは、実行時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e70b1-103">The TIBCO Rendezvous Transport property is used for run time.</span></span> <span data-ttu-id="e70b1-104">**トランスポートのプロパティ** 画面で、生成されたメッセージを公開する TIBCO Rendezvous ドメインを識別する接続パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-104">In the **Transport Properties** screen, you set the connection parameters that identify the TIBCO Rendezvous domain where you want to publish the generated messages.</span></span>  
  
### <a name="to-specify-tibco-rendezvous-transport-properties"></a><span data-ttu-id="e70b1-105">TIBCO Rendezvous トランスポートのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="e70b1-105">To specify TIBCO Rendezvous Transport properties</span></span>  
  
1.  <span data-ttu-id="e70b1-106">**TIBCO Rendezvous トランスポートのプロパティ**画面で、展開**証明された送信者プロパティ**し、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-106">On the **TIBCO Rendezvous Transport Properties** screen, expand **Certified Sender Properties** and enter the following information.</span></span>  
  
     ![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")  
  
    |<span data-ttu-id="e70b1-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e70b1-107">Use this</span></span>|<span data-ttu-id="e70b1-108">目的</span><span class="sxs-lookup"><span data-stu-id="e70b1-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e70b1-109">**元帳の名前**</span><span class="sxs-lookup"><span data-stu-id="e70b1-109">**Ledger name**</span></span>|<span data-ttu-id="e70b1-110">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-110">Default value is blank.</span></span> <span data-ttu-id="e70b1-111">永続的な認証されたメッセージ配信に使用する台帳ファイル名。</span><span class="sxs-lookup"><span data-stu-id="e70b1-111">Ledger file name to use for persistent certified message delivery.</span></span> <span data-ttu-id="e70b1-112">ローカル ドライブのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-112">Use local drives only.</span></span>|  
    |<span data-ttu-id="e70b1-113">**再利用可能名**</span><span class="sxs-lookup"><span data-stu-id="e70b1-113">**Reusable name**</span></span>|<span data-ttu-id="e70b1-114">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-114">Default value is blank.</span></span> <span data-ttu-id="e70b1-115">認証されたメッセージ配信に使用する再利用可能な送信者名です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-115">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="e70b1-116">この名前は、ネットワーク上のすべての認証されたメッセージの送信者名の中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e70b1-116">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
2.  <span data-ttu-id="e70b1-117">展開**資格情報**し、サーバーに接続に関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-117">Expand **Credentials** and enter the following information for connection to the server.</span></span>  
  
    |<span data-ttu-id="e70b1-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e70b1-118">Use this</span></span>|<span data-ttu-id="e70b1-119">目的</span><span class="sxs-lookup"><span data-stu-id="e70b1-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e70b1-120">**Password**</span><span class="sxs-lookup"><span data-stu-id="e70b1-120">**Password**</span></span>|<span data-ttu-id="e70b1-121">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-121">Default value is blank.</span></span> <span data-ttu-id="e70b1-122">Tibco Rendezvous デーモンにログインするためのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="e70b1-122">Password for login to a Tibco Rendezvous daemon.</span></span>|  
    |<span data-ttu-id="e70b1-123">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="e70b1-123">**User name**</span></span>|<span data-ttu-id="e70b1-124">既定値は空白です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-124">Default value is blank.</span></span> <span data-ttu-id="e70b1-125">Tibco Rendezvous デーモンで使用するユーザー名です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-125">User name for Tibco Rendezvous daemon.</span></span>|  
  
3.  <span data-ttu-id="e70b1-126">展開**全般設定**と TIBCO Rendezvous サーバーに接続に関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-126">Expand **General Settings** and enter the following information for connection to the TIBCO Rendezvous server.</span></span>  
  
    |<span data-ttu-id="e70b1-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e70b1-127">Use this</span></span>|<span data-ttu-id="e70b1-128">目的</span><span class="sxs-lookup"><span data-stu-id="e70b1-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e70b1-129">**コード ページ番号**</span><span class="sxs-lookup"><span data-stu-id="e70b1-129">**Code Page Number**</span></span>|<span data-ttu-id="e70b1-130">既定値は 65001 (UTF-8 エンコーディングのコード ページ) です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-130">Default value is 65001 (code page for UTF-8 encoding).</span></span> <span data-ttu-id="e70b1-131">これは、TIBCO Rendezvous SDK が文字列のエンコーディングに使用するコード ページです。</span><span class="sxs-lookup"><span data-stu-id="e70b1-131">This is the code page that the TIBCO Rendezvous SDK uses for String encoding.</span></span>|  
    |<span data-ttu-id="e70b1-132">**既定のサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="e70b1-132">**Default Subject Name**</span></span>|<span data-ttu-id="e70b1-133">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="e70b1-133">Default is empty.</span></span> <span data-ttu-id="e70b1-134">サブジェクト名はオーケストレーションで設定されます。</span><span class="sxs-lookup"><span data-stu-id="e70b1-134">The subject name is set in the orchestration.</span></span> <span data-ttu-id="e70b1-135">1 つの種類のメッセージに 1 つのポートを使用する場合、既定のサブジェクト名を指定でき、サブジェクト名プロパティを設定する必要をなくしてオーケストレーションを単純化できます。</span><span class="sxs-lookup"><span data-stu-id="e70b1-135">If a port is used for one message type, you can provide a default subject name, and you can simplify orchestrations by removing the need to set the Subject name property.</span></span>|  
    |<span data-ttu-id="e70b1-136">**タイム バッチを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="e70b1-136">**Enable Time Batch**</span></span>|<span data-ttu-id="e70b1-137">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-137">Default value is False.</span></span> <span data-ttu-id="e70b1-138">TIBCO Rendezvous のタイム バッチ機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="e70b1-138">Enable/Disable TIBCO Rendezvous Time Batch feature.</span></span>|  
    |<span data-ttu-id="e70b1-139">**サポートされていない型を文字列に対応付け**</span><span class="sxs-lookup"><span data-stu-id="e70b1-139">**Map Unsupported types to string**</span></span>|<span data-ttu-id="e70b1-140">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-140">Default value is True.</span></span> <span data-ttu-id="e70b1-141">True の場合、サポートされていない型はすべて文字列型にマップされます。</span><span class="sxs-lookup"><span data-stu-id="e70b1-141">If true, unsupported types are mapped to string if it is possible.</span></span> <span data-ttu-id="e70b1-142">False の場合、実行時エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e70b1-142">If False, a run-time error is generated.</span></span>|  
    |<span data-ttu-id="e70b1-143">**TIBCO Rendezvous アセンブリなど、バイナリ ファイルへのパス**</span><span class="sxs-lookup"><span data-stu-id="e70b1-143">**Path to Binaries, such as TIBCO Rendezvous assemblies**</span></span>|<span data-ttu-id="e70b1-144">PATH 環境変数でまだ設定されていない場合は、この情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-144">Provide this information if it is not already in the PATH environment variable.</span></span>|  
    |<span data-ttu-id="e70b1-145">**順序の保持**</span><span class="sxs-lookup"><span data-stu-id="e70b1-145">**Preserver Order**</span></span>|<span data-ttu-id="e70b1-146">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-146">Default value is True.</span></span> <span data-ttu-id="e70b1-147">ロジックで、メッセージを BizTalk Server から受信したときと同じ順序で TIBCO Rendezvous に送信できます。</span><span class="sxs-lookup"><span data-stu-id="e70b1-147">Enables logic to send messages to TIBCO Rendezvous in the same order they were received from BizTalk Server.</span></span> <span data-ttu-id="e70b1-148">このパラメーターにより、同じ順序での公開が強制されますが、サブスクライバーが同じ順序で受信するということではありません。</span><span class="sxs-lookup"><span data-stu-id="e70b1-148">This parameter forces publishing in the same order; it does not mean that subscribers receive them in the same order.</span></span>|  
    |<span data-ttu-id="e70b1-149">**送信ポートの識別子**</span><span class="sxs-lookup"><span data-stu-id="e70b1-149">**Send Port Identifier**</span></span>|<span data-ttu-id="e70b1-150">この識別子は、このポートに関連付けられているログ メッセージに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e70b1-150">This identifier appears in log messages associated with this port.</span></span> <span data-ttu-id="e70b1-151">これは、便宜上指定します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-151">It is provided as a convenience.</span></span>|  
  
4.  <span data-ttu-id="e70b1-152">展開**Rendezvous トランスポート**TIBCO Rendezvous サーバーへの接続情報を入力し、**適用**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-152">Expand **Rendezvous Transport** and enter the information for connection to the TIBCO Rendezvous server, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e70b1-153">Microsoft BizTalk Adapter for TIBCO Rendezvous が TIBCO Rendezvous にアクセスできるようにするために接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e70b1-153">You must set connection parameters for Microsoft BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous.</span></span>  
  
    |<span data-ttu-id="e70b1-154">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e70b1-154">Use this</span></span>|<span data-ttu-id="e70b1-155">目的</span><span class="sxs-lookup"><span data-stu-id="e70b1-155">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e70b1-156">**デーモン**</span><span class="sxs-lookup"><span data-stu-id="e70b1-156">**Daemon**</span></span>|<span data-ttu-id="e70b1-157">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="e70b1-157">Default is empty.</span></span><br /><br /> <span data-ttu-id="e70b1-158">Rendezvous トランスポート デーモン パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e70b1-158">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="e70b1-159">**ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="e70b1-159">**Network**</span></span>|<span data-ttu-id="e70b1-160">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="e70b1-160">Default is empty.</span></span><br /><br /> <span data-ttu-id="e70b1-161">Rendezvous トランスポート ネットワーク パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e70b1-161">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="e70b1-162">**サービス**</span><span class="sxs-lookup"><span data-stu-id="e70b1-162">**Service**</span></span>|<span data-ttu-id="e70b1-163">既定では空になっています。</span><span class="sxs-lookup"><span data-stu-id="e70b1-163">Default is empty.</span></span><br /><br /> <span data-ttu-id="e70b1-164">Rendezvous トランスポート サービス パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e70b1-164">Rendezvous Transport Service parameter.</span></span>|  
  
5.  <span data-ttu-id="e70b1-165">シングル サインオン (SSO) を使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-165">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="e70b1-166">TIBCO Rendezvous システムにアクセスする方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="e70b1-166">There are two methods that you can use to access the TIBCO Rendezvous system.</span></span> <span data-ttu-id="e70b1-167">1 つは資格情報 ([ユーザー名] パラメーターと [パスワード] パラメーター) を使用する方法で、もう 1 つはシングル サインオン (SSO) を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-167">You can use Credentials (User Name and Password parameters) or Single Sign-On.</span></span>  
  
    1.  <span data-ttu-id="e70b1-168">選択**はい**で、 **SSO を使用する**でのシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-168">Select **Yes** in the **Use SSO** to use Single Sign-On.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e70b1-169">参照してください[シングル サインオンを使用して](../core/using-single-sign-on5.md)SSO をセットアップする方法についてはします。</span><span class="sxs-lookup"><span data-stu-id="e70b1-169">See [Using Single Sign-On](../core/using-single-sign-on5.md) for information about how to set up SSO.</span></span>  
  
    2.  <span data-ttu-id="e70b1-170">一覧から関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-170">Select an affiliate application from the list.</span></span>  
  
         <span data-ttu-id="e70b1-171">エンタープライズ シングル サインオン ツールで作成された関連アプリケーションは TIBCO Rendezvous などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-171">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO Rendezvous.</span></span> <span data-ttu-id="e70b1-172">Microsoft BizTalk Adapter for TIBCO Rendezvous では、アプリケーション ユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e70b1-172">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the credentials of an application user.</span></span> <span data-ttu-id="e70b1-173">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="e70b1-173">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e70b1-174">関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications1.md)です。</span><span class="sxs-lookup"><span data-stu-id="e70b1-174">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
6.  <span data-ttu-id="e70b1-175">をクリックして**適用**、クリックして**[ok]**接続情報を受け入れるように必要なすべての情報を提供するとします。</span><span class="sxs-lookup"><span data-stu-id="e70b1-175">Click **Apply**, and then click **OK** after providing all required information to accept the connection information.</span></span>  
  
     <span data-ttu-id="e70b1-176">BizTalk Adapter for TIBCO Rendezvous にアクセスする TIBCO Rendezvous の接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e70b1-176">You must set connection parameters for BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e70b1-177">参照</span><span class="sxs-lookup"><span data-stu-id="e70b1-177">See Also</span></span>  
 [<span data-ttu-id="e70b1-178">TIBCO Rendezvous 送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e70b1-178">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)