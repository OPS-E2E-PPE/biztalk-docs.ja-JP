---
title: "BizTalk アダプターに IPv6 のアドレス指定を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93cd2ead-5e87-47ac-8f78-d56b80afd34e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 446125cbe164cfebfe7635975c5fd1825a026081
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="using-ipv6-addressing-with-biztalk-adapters"></a><span data-ttu-id="dc4a1-102">BizTalk アダプターにおける IPv6 アドレス指定の使用</span><span class="sxs-lookup"><span data-stu-id="dc4a1-102">Using IPv6 Addressing with BizTalk Adapters</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="dc4a1-103"> アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] オペレーティング システムにインストールされている場合に、IPv6 アドレス指定の使用がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-103"> adapters support the use of IPv6 addressing when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on the [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] operating systems.</span></span> <span data-ttu-id="dc4a1-104">このトピックでは、UNC パスに対して IPv6 アドレスを指定するために使用される命名規則、リテラル IPv6 アドレスを指定するための命名規則、および HTTP アダプターと SOAP アダプターでの IPv6 スコープ識別子の使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-104">This topic describes the nomenclature that should be used to specify an IPv6 address for a UNC path, the nomenclature for specifying a literal IPv6 address, and the use of IPv6 scope identifiers with the HTTP and SOAP adapters.</span></span>  
  
## <a name="ipv6-address-nomenclature-used-for-a-unc-path"></a><span data-ttu-id="dc4a1-105">UNC パスに対して使用される IPv6 アドレス命名規則</span><span class="sxs-lookup"><span data-stu-id="dc4a1-105">IPv6 Address Nomenclature Used for a UNC Path</span></span>  
 <span data-ttu-id="dc4a1-106">UNC パスでリテラル IPv6 アドレスを指定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-106">Follow these steps when specifying a literal IPv6 address in a UNC path:</span></span>  
  
1.  <span data-ttu-id="dc4a1-107">すべてのコロン文字 ":" をダッシュ文字 "-" で置換します。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-107">Replace any colon ":" characters with a dash "-" character.</span></span>  
  
2.  <span data-ttu-id="dc4a1-108">テキストを追加"**.ipv6 という**"IP アドレスにします。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-108">Append the text "**.ipv6-literal.net**" to the IP address.</span></span>  
  
 <span data-ttu-id="dc4a1-109">たとえば、2001:DB8:2a:1005:230:48ff:fe73:989d という IPv6 アドレスを使用してコンピューター上のファイル共有を参照する URI は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-109">For example, the nomenclature for a URI that points to a file share on a computer with the IPv6 address 2001:DB8:2a:1005:230:48ff:fe73:989d would be:</span></span>  
  
```  
\\2001-DB8-2a-1005-230-48ff-fe73-989d.ipv6-literal.net\<sharename\>  
```  
  
 <span data-ttu-id="dc4a1-110">ここで\< *sharename* \>ターゲット コンピューター上のファイル共有の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-110">Where \<*sharename*\> is the name of the file share on the target computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc4a1-111">ファイル送信ハンドラーとファイル受信ハンドラーが実行されているホスト インスタンスのユーザー アカウントが、ファイル共有に対する適切なアクセス許可を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-111">Ensure that the user accounts for the host instances that the File send and receive handlers are running in have appropriate permissions to the file share.</span></span> <span data-ttu-id="dc4a1-112">ファイル アダプターでファイルを受信するために必要なフォルダーのアクセス許可の詳細については、次を参照してください。[ファイル受信ハンドラーを構成する方法](http://msdn.microsoft.com/library/68333bb6-d79b-4a82-9742-230f62d535c4)です。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-112">For more information about the folder permissions required to receive files with the File adapter see [How to Configure a File Receive Handler](http://msdn.microsoft.com/library/68333bb6-d79b-4a82-9742-230f62d535c4).</span></span> <span data-ttu-id="dc4a1-113">ファイル アダプターを持つファイルを送信するときに必要なフォルダーのアクセス許可の詳細については、次を参照してください。[ファイル アダプターに関する既知の問題](../core/known-issues-with-the-file-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-113">For more information about the folder permissions required when sending files with the File adapter see [Known Issues with the File Adapter](../core/known-issues-with-the-file-adapter.md).</span></span> <span data-ttu-id="dc4a1-114">ファイル アダプターで使用するためにサポートされているファイル システムについては、次を参照してください。 [http://support.microsoft.com/kb/815070](http://support.microsoft.com/kb/815070)です。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-114">For information about the file systems that are supported for use with the File adapter, see [http://support.microsoft.com/kb/815070](http://support.microsoft.com/kb/815070).</span></span>  
  
## <a name="using-ipv6-scope-identifiers-with-the-http-adapter-and-the-soap-send-adapter"></a><span data-ttu-id="dc4a1-115">HTTP アダプターおよび SOAP 送信アダプターにおける IPv6 スコープ識別子の使用</span><span class="sxs-lookup"><span data-stu-id="dc4a1-115">Using IPv6 Scope Identifiers with the HTTP Adapter and the SOAP Send Adapter</span></span>  
 <span data-ttu-id="dc4a1-116">HTTP 送信アダプターと受信 SOAP 送信アダプタは、IPv6 アドレスで、スコープ識別子を使用する場合、スコープ識別子必要がありますエスケープすることをエスケープ コードを必要と**%25**です。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-116">The HTTP send and receive adapter and the SOAP send adapter require that if a scope identifier is used in an IPv6 address, the scope identifier must be escaped with the escape code **%25**.</span></span> <span data-ttu-id="dc4a1-117">たとえば、 **fe80::550c:489f:e65e:aef3 %8**スコープ識別子 (%8) を含む有効な IPv6 アドレスします。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-117">For example, **fe80::550c:489f:e65e:aef3%8** is a valid IPv6 address containing a scope identifier (%8).</span></span> <span data-ttu-id="dc4a1-118">HTTP 送受信アダプターまたは SOAP 送信アダプターと共にこの IPv6 アドレスを使用するには、スコープ識別子を次のようにエスケープさせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-118">To use this IPv6 address with the HTTP send and receive adapters or the SOAP send adapter, the scope identifier must be escaped as follows:</span></span>  
  
```  
fe80::550c:489f:e65e:aef3%258  
```  
  
## <a name="adapter-uri-nomenclature-used-for-a-literal-ipv6-address"></a><span data-ttu-id="dc4a1-119">リテラル IPv6 アドレスで使用されるアダプター URI 命名規則</span><span class="sxs-lookup"><span data-stu-id="dc4a1-119">Adapter URI Nomenclature Used for a Literal IPv6 Address</span></span>  
  
-   <span data-ttu-id="dc4a1-120">アダプターの URI としてリテラル IPv6 アドレスを使用するには、IP アドレスを角かっこ [ と ] で囲みます。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-120">To use a literal IPv6 address for an adapter URI, enclose the IP address in square brackets "[", "]".</span></span> <span data-ttu-id="dc4a1-121">たとえば、2001:DB8:2a:1005:230:48ff:fe73:989d という IPv6 アドレスの URI は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-121">For example, the nomenclature for a URI with the IPv6 address 2001:DB8:2a:1005:230:48ff:fe73:989d would be:</span></span>  
  
    ```  
    [2001:DB8:2a:1005:230:48ff:fe73:989d]  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="dc4a1-122">リテラルの使用する IPv6 アドレスで確立されているガイドラインに従うアダプター Uri の[RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375)です。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-122">The use of literal IPv6 addresses for adapter URIs follows the guidelines established in [RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375).</span></span>  
  
-   <span data-ttu-id="dc4a1-123">リテラル IPv6 アドレスを POP3 受信アダプター、SMTP 送信アダプター、または SQL 送受信アダプターのサーバー名として指定する場合、IPv6 アドレスを角かっこで囲む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-123">When specifying a literal IPv6 address as the server name for the POP3 receive adapter, the SMTP send adapter, or the SQL send and receive adapters, the IPv6 address should not be enclosed in square brackets.</span></span>  
  
## <a name="summary-of-considerations-when-using-literal-ipv6-addressing-with-biztalk-adapters"></a><span data-ttu-id="dc4a1-124">BizTalk アダプターでリテラル IPv6 アドレス指定を使用する場合の考慮事項のまとめ</span><span class="sxs-lookup"><span data-stu-id="dc4a1-124">Summary of Considerations When Using Literal IPv6 Addressing with BizTalk Adapters</span></span>  
 <span data-ttu-id="dc4a1-125">次の表に、リテラル IPv6 アドレスを使用するために IP アドレスを角かっこ [ および ] で囲むことがいつ必要になるか、および IPv6 アドレスで使用されるスコープ識別子をエスケープさせることがいつ必要になるかを示します。</span><span class="sxs-lookup"><span data-stu-id="dc4a1-125">The table below summarizes when the use of a literal IPv6 address requires that the IP address is enclosed in square brackets "[", "]" and when a scope identifier that is used in an IPv6 address must be escaped:</span></span>  
  
|<span data-ttu-id="dc4a1-126">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="dc4a1-126">Adapter</span></span>|<span data-ttu-id="dc4a1-127">リテラル IPv6 アドレスを角かっこで囲む必要性</span><span class="sxs-lookup"><span data-stu-id="dc4a1-127">Requires that literal IPv6 address is enclosed in square brackets?</span></span>|<span data-ttu-id="dc4a1-128">スコープ識別子をエスケープさせる必要性</span><span class="sxs-lookup"><span data-stu-id="dc4a1-128">Requires that scope identifier is escaped?</span></span>|  
|-------------|------------------------------------------------------------------------|------------------------------------------------|  
|<span data-ttu-id="dc4a1-129">POP3 受信</span><span class="sxs-lookup"><span data-stu-id="dc4a1-129">POP3 receive</span></span>|<span data-ttu-id="dc4a1-130">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-130">No</span></span>|<span data-ttu-id="dc4a1-131">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-131">No</span></span>|  
|<span data-ttu-id="dc4a1-132">SMTP 送信</span><span class="sxs-lookup"><span data-stu-id="dc4a1-132">SMTP send</span></span>|<span data-ttu-id="dc4a1-133">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-133">No</span></span>|<span data-ttu-id="dc4a1-134">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-134">No</span></span>|  
|<span data-ttu-id="dc4a1-135">SQL 送受信</span><span class="sxs-lookup"><span data-stu-id="dc4a1-135">SQL send and receive</span></span>|<span data-ttu-id="dc4a1-136">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-136">No</span></span>|<span data-ttu-id="dc4a1-137">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-137">No</span></span>|  
|<span data-ttu-id="dc4a1-138">ファイル送受信</span><span class="sxs-lookup"><span data-stu-id="dc4a1-138">File send and receive</span></span>|<span data-ttu-id="dc4a1-139">いいえ (セクションを参照して**UNC パスに対して使用される IPv6 アドレス命名規則**)</span><span class="sxs-lookup"><span data-stu-id="dc4a1-139">No (see section **IPv6 Address Nomenclature Used for a UNC Path**)</span></span>|<span data-ttu-id="dc4a1-140">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-140">No</span></span>|  
|<span data-ttu-id="dc4a1-141">HTTP 送受信</span><span class="sxs-lookup"><span data-stu-id="dc4a1-141">HTTP send and receive</span></span>|<span data-ttu-id="dc4a1-142">可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-142">Yes</span></span>|<span data-ttu-id="dc4a1-143">可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-143">Yes</span></span>|  
|<span data-ttu-id="dc4a1-144">MQSeries 送受信</span><span class="sxs-lookup"><span data-stu-id="dc4a1-144">MQSeries send and receive</span></span>|<span data-ttu-id="dc4a1-145">可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-145">Yes</span></span>|<span data-ttu-id="dc4a1-146">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-146">No</span></span>|  
|<span data-ttu-id="dc4a1-147">MSMQ 送受信</span><span class="sxs-lookup"><span data-stu-id="dc4a1-147">MSMQ send and receive</span></span>|<span data-ttu-id="dc4a1-148">可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-148">Yes</span></span>|<span data-ttu-id="dc4a1-149">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-149">No</span></span>|  
|<span data-ttu-id="dc4a1-150">SOAP 送信</span><span class="sxs-lookup"><span data-stu-id="dc4a1-150">SOAP send</span></span>|<span data-ttu-id="dc4a1-151">可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-151">Yes</span></span>|<span data-ttu-id="dc4a1-152">可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-152">Yes</span></span>|  
|<span data-ttu-id="dc4a1-153">SOAP 受信</span><span class="sxs-lookup"><span data-stu-id="dc4a1-153">SOAP receive</span></span>|<span data-ttu-id="dc4a1-154">可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-154">Yes</span></span>|<span data-ttu-id="dc4a1-155">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-155">No</span></span>|  
|<span data-ttu-id="dc4a1-156">WCF 送受信</span><span class="sxs-lookup"><span data-stu-id="dc4a1-156">WCF send and receive</span></span>|<span data-ttu-id="dc4a1-157">可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-157">Yes</span></span>|<span data-ttu-id="dc4a1-158">不可</span><span class="sxs-lookup"><span data-stu-id="dc4a1-158">No</span></span>|