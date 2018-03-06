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
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5726d5b05c548fd728228fcad39e56ce535fbb5
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="using-ipv6-addressing-with-biztalk-adapters"></a><span data-ttu-id="1d019-102">BizTalk アダプターにおける IPv6 アドレス指定の使用</span><span class="sxs-lookup"><span data-stu-id="1d019-102">Using IPv6 Addressing with BizTalk Adapters</span></span>
<span data-ttu-id="1d019-103">BizTalk Server アダプターでは、IPv6 アドレスの使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1d019-103">BizTalk Server adapters support the use of IPv6 addressing.</span></span> <span data-ttu-id="1d019-104">このトピックでは、UNC パスに対して IPv6 アドレスを指定するために使用される命名規則、リテラル IPv6 アドレスを指定するための命名規則、および HTTP アダプターと SOAP アダプターでの IPv6 スコープ識別子の使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d019-104">This topic describes the nomenclature that should be used to specify an IPv6 address for a UNC path, the nomenclature for specifying a literal IPv6 address, and the use of IPv6 scope identifiers with the HTTP and SOAP adapters.</span></span>  
  
## <a name="ipv6-address-nomenclature-used-for-a-unc-path"></a><span data-ttu-id="1d019-105">UNC パスに対して使用される IPv6 アドレス命名規則</span><span class="sxs-lookup"><span data-stu-id="1d019-105">IPv6 Address Nomenclature Used for a UNC Path</span></span>  
 <span data-ttu-id="1d019-106">UNC パスでリテラル IPv6 アドレスを指定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1d019-106">Follow these steps when specifying a literal IPv6 address in a UNC path:</span></span>  
  
1.  <span data-ttu-id="1d019-107">すべてのコロン文字 ":" をダッシュ文字 "-" で置換します。</span><span class="sxs-lookup"><span data-stu-id="1d019-107">Replace any colon ":" characters with a dash "-" character.</span></span>  
  
2.  <span data-ttu-id="1d019-108">テキストを追加"**.ipv6 という**"IP アドレスにします。</span><span class="sxs-lookup"><span data-stu-id="1d019-108">Append the text "**.ipv6-literal.net**" to the IP address.</span></span>  
  
 <span data-ttu-id="1d019-109">たとえば、2001:DB8:2a:1005:230:48ff:fe73:989d という IPv6 アドレスを使用してコンピューター上のファイル共有を参照する URI は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1d019-109">For example, the nomenclature for a URI that points to a file share on a computer with the IPv6 address 2001:DB8:2a:1005:230:48ff:fe73:989d would be:</span></span>  
  
```  
\\2001-DB8-2a-1005-230-48ff-fe73-989d.ipv6-literal.net\<sharename\>  
```  
  
 <span data-ttu-id="1d019-110">ここで\< *sharename* \>ターゲット コンピューター上のファイル共有の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d019-110">Where \<*sharename*\> is the name of the file share on the target computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d019-111">ファイル送信ハンドラーとファイル受信ハンドラーが実行されているホスト インスタンスのユーザー アカウントが、ファイル共有に対する適切なアクセス許可を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1d019-111">Ensure that the user accounts for the host instances that the File send and receive handlers are running in have appropriate permissions to the file share.</span></span> <span data-ttu-id="1d019-112">ファイル アダプターでファイルを受信するために必要なフォルダーのアクセス許可の詳細については、次を参照してください。[ファイル受信ハンドラーを構成する](../core/configure-the-file-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="1d019-112">For more information about the folder permissions required to receive files with the File adapter see [Configure a File Receive Handler](../core/configure-the-file-adapter.md).</span></span> <span data-ttu-id="1d019-113">ファイル アダプターを持つファイルを送信するときに必要なフォルダーのアクセス許可の詳細については、次を参照してください。[ファイル アダプターに関する既知の問題](../core/known-issues-with-the-file-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="1d019-113">For more information about the folder permissions required when sending files with the File adapter see [Known Issues with the File Adapter](../core/known-issues-with-the-file-adapter.md).</span></span> <span data-ttu-id="1d019-114">ファイル アダプターで使用するためにサポートされているファイル システムについては、次を参照してください。 [http://support.microsoft.com/kb/815070](http://support.microsoft.com/kb/815070)します。</span><span class="sxs-lookup"><span data-stu-id="1d019-114">For information about the file systems that are supported for use with the File adapter, see [http://support.microsoft.com/kb/815070](http://support.microsoft.com/kb/815070).</span></span>  
  
## <a name="using-ipv6-scope-identifiers-with-the-http-adapter-and-the-soap-send-adapter"></a><span data-ttu-id="1d019-115">HTTP アダプターおよび SOAP 送信アダプターにおける IPv6 スコープ識別子の使用</span><span class="sxs-lookup"><span data-stu-id="1d019-115">Using IPv6 Scope Identifiers with the HTTP Adapter and the SOAP Send Adapter</span></span>  
 <span data-ttu-id="1d019-116">HTTP 送信アダプターと受信 SOAP 送信アダプタでは、スコープ識別子が IPv6 アドレスで使用されている場合、スコープ識別子必要がありますエスケープすることをエスケープ コードに必要な **%25**します。</span><span class="sxs-lookup"><span data-stu-id="1d019-116">The HTTP send and receive adapter and the SOAP send adapter require that if a scope identifier is used in an IPv6 address, the scope identifier must be escaped with the escape code **%25**.</span></span> <span data-ttu-id="1d019-117">たとえば、 **fe80::550c:489f:e65e:aef3 %8** スコープ識別子 (%8) を含む有効な IPv6 アドレスします。</span><span class="sxs-lookup"><span data-stu-id="1d019-117">For example, **fe80::550c:489f:e65e:aef3%8** is a valid IPv6 address containing a scope identifier (%8).</span></span> <span data-ttu-id="1d019-118">HTTP 送受信アダプターまたは SOAP 送信アダプターと共にこの IPv6 アドレスを使用するには、スコープ識別子を次のようにエスケープさせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d019-118">To use this IPv6 address with the HTTP send and receive adapters or the SOAP send adapter, the scope identifier must be escaped as follows:</span></span>  
  
```  
fe80::550c:489f:e65e:aef3%258  
```  
  
## <a name="adapter-uri-nomenclature-used-for-a-literal-ipv6-address"></a><span data-ttu-id="1d019-119">リテラル IPv6 アドレスで使用されるアダプター URI 命名規則</span><span class="sxs-lookup"><span data-stu-id="1d019-119">Adapter URI Nomenclature Used for a Literal IPv6 Address</span></span>  
  
-   <span data-ttu-id="1d019-120">アダプターの URI としてリテラル IPv6 アドレスを使用するには、IP アドレスを角かっこ [ と ] で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1d019-120">To use a literal IPv6 address for an adapter URI, enclose the IP address in square brackets "[", "]".</span></span> <span data-ttu-id="1d019-121">たとえば、2001:DB8:2a:1005:230:48ff:fe73:989d という IPv6 アドレスの URI は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1d019-121">For example, the nomenclature for a URI with the IPv6 address 2001:DB8:2a:1005:230:48ff:fe73:989d would be:</span></span>  
  
    ```  
    [2001:DB8:2a:1005:230:48ff:fe73:989d]  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="1d019-122">アダプターの Uri のガイドラインに従うために、リテラルの使用の IPv6 アドレス [RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375)します。</span><span class="sxs-lookup"><span data-stu-id="1d019-122">The use of literal IPv6 addresses for adapter URIs follows the guidelines established in [RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375).</span></span>  
  
-   <span data-ttu-id="1d019-123">リテラル IPv6 アドレスを POP3 受信アダプター、SMTP 送信アダプター、または SQL 送受信アダプターのサーバー名として指定する場合、IPv6 アドレスを角かっこで囲む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1d019-123">When specifying a literal IPv6 address as the server name for the POP3 receive adapter, the SMTP send adapter, or the SQL send and receive adapters, the IPv6 address should not be enclosed in square brackets.</span></span>  
  
## <a name="summary-of-considerations-when-using-literal-ipv6-addressing-with-biztalk-adapters"></a><span data-ttu-id="1d019-124">BizTalk アダプターでリテラル IPv6 アドレス指定を使用する場合の考慮事項のまとめ</span><span class="sxs-lookup"><span data-stu-id="1d019-124">Summary of Considerations When Using Literal IPv6 Addressing with BizTalk Adapters</span></span>  
 <span data-ttu-id="1d019-125">次の表に、リテラル IPv6 アドレスを使用するために IP アドレスを角かっこ [ および ] で囲むことがいつ必要になるか、および IPv6 アドレスで使用されるスコープ識別子をエスケープさせることがいつ必要になるかを示します。</span><span class="sxs-lookup"><span data-stu-id="1d019-125">The table below summarizes when the use of a literal IPv6 address requires that the IP address is enclosed in square brackets "[", "]" and when a scope identifier that is used in an IPv6 address must be escaped:</span></span>  
  
|<span data-ttu-id="1d019-126">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="1d019-126">Adapter</span></span>|<span data-ttu-id="1d019-127">リテラル IPv6 アドレスを角かっこで囲む必要性</span><span class="sxs-lookup"><span data-stu-id="1d019-127">Requires that literal IPv6 address is enclosed in square brackets?</span></span>|<span data-ttu-id="1d019-128">スコープ識別子をエスケープさせる必要性</span><span class="sxs-lookup"><span data-stu-id="1d019-128">Requires that scope identifier is escaped?</span></span>|  
|---|---|---|  
|<span data-ttu-id="1d019-129">POP3 受信</span><span class="sxs-lookup"><span data-stu-id="1d019-129">POP3 receive</span></span>|<span data-ttu-id="1d019-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-130">No</span></span>|<span data-ttu-id="1d019-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-131">No</span></span>|  
|<span data-ttu-id="1d019-132">SMTP 送信</span><span class="sxs-lookup"><span data-stu-id="1d019-132">SMTP send</span></span>|<span data-ttu-id="1d019-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-133">No</span></span>|<span data-ttu-id="1d019-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-134">No</span></span>|  
|<span data-ttu-id="1d019-135">SQL 送受信</span><span class="sxs-lookup"><span data-stu-id="1d019-135">SQL send and receive</span></span>|<span data-ttu-id="1d019-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-136">No</span></span>|<span data-ttu-id="1d019-137">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-137">No</span></span>|  
|<span data-ttu-id="1d019-138">ファイル送受信</span><span class="sxs-lookup"><span data-stu-id="1d019-138">File send and receive</span></span>|<span data-ttu-id="1d019-139">いいえ (セクションを参照して **UNC パスに対して使用される IPv6 アドレス命名規則**)</span><span class="sxs-lookup"><span data-stu-id="1d019-139">No (see section **IPv6 Address Nomenclature Used for a UNC Path**)</span></span>|<span data-ttu-id="1d019-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-140">No</span></span>|  
|<span data-ttu-id="1d019-141">HTTP 送受信</span><span class="sxs-lookup"><span data-stu-id="1d019-141">HTTP send and receive</span></span>|<span data-ttu-id="1d019-142">可</span><span class="sxs-lookup"><span data-stu-id="1d019-142">Yes</span></span>|<span data-ttu-id="1d019-143">はい</span><span class="sxs-lookup"><span data-stu-id="1d019-143">Yes</span></span>|  
|<span data-ttu-id="1d019-144">MQSeries 送受信</span><span class="sxs-lookup"><span data-stu-id="1d019-144">MQSeries send and receive</span></span>|<span data-ttu-id="1d019-145">はい</span><span class="sxs-lookup"><span data-stu-id="1d019-145">Yes</span></span>|<span data-ttu-id="1d019-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-146">No</span></span>|  
|<span data-ttu-id="1d019-147">MSMQ 送受信</span><span class="sxs-lookup"><span data-stu-id="1d019-147">MSMQ send and receive</span></span>|<span data-ttu-id="1d019-148">可</span><span class="sxs-lookup"><span data-stu-id="1d019-148">Yes</span></span>|<span data-ttu-id="1d019-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-149">No</span></span>|  
|<span data-ttu-id="1d019-150">SOAP 送信</span><span class="sxs-lookup"><span data-stu-id="1d019-150">SOAP send</span></span>|<span data-ttu-id="1d019-151">はい</span><span class="sxs-lookup"><span data-stu-id="1d019-151">Yes</span></span>|<span data-ttu-id="1d019-152">可</span><span class="sxs-lookup"><span data-stu-id="1d019-152">Yes</span></span>|  
|<span data-ttu-id="1d019-153">SOAP 受信</span><span class="sxs-lookup"><span data-stu-id="1d019-153">SOAP receive</span></span>|<span data-ttu-id="1d019-154">はい</span><span class="sxs-lookup"><span data-stu-id="1d019-154">Yes</span></span>|<span data-ttu-id="1d019-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-155">No</span></span>|  
|<span data-ttu-id="1d019-156">WCF 送受信</span><span class="sxs-lookup"><span data-stu-id="1d019-156">WCF send and receive</span></span>|<span data-ttu-id="1d019-157">はい</span><span class="sxs-lookup"><span data-stu-id="1d019-157">Yes</span></span>|<span data-ttu-id="1d019-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="1d019-158">No</span></span>|