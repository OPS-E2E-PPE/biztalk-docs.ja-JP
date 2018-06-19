---
title: HTTP アダプタの構成およびチューニング パラメータ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, parameters
- configuring [HTTP adapters], parameters
- HTTP adapters, tuning
- RequestQueueSize key [HTTP adapters]
- HttpReceiveThreadsPerCpu key [HTTP adapters]
- HttpOutTimeoutInterval key [HTTP adapters]
- HttpOutInflightSize key [HTTP adapters]
- configuring [HTTP adapters], tuning
- DisableChunkEncoding key [HTTP adapters]
- HttpOutCompleteSize key [HTTP adapters]
ms.assetid: c8989a88-722a-40b5-94cf-4b6840add02e
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db4f4dc4403ddfbf677ac2729c00e2b1976db61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257786"
---
# <a name="http-adapter-configuration-and-tuning-parameters"></a><span data-ttu-id="46b19-102">HTTP アダプタの構成およびチューニング パラメータ</span><span class="sxs-lookup"><span data-stu-id="46b19-102">HTTP Adapter Configuration and Tuning Parameters</span></span>
<span data-ttu-id="46b19-103">HTTP アダプタの構成およびチューニング パラメータの一部には、レジストリ キー エントリから、また BizTalk Server インストールのルート ディレクトリにある BTSNTSvc.exe.config 構成ファイルを変更することによってアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="46b19-103">Several configuration and tuning parameters are accessible for the HTTP adapter through registry key entries and through the modification of the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
 <span data-ttu-id="46b19-104">**HTTP アダプタのパフォーマンスに影響するレジストリ設定**</span><span class="sxs-lookup"><span data-stu-id="46b19-104">**Registry Settings That Affect HTTP Adapter Performance**</span></span>  
  
 <span data-ttu-id="46b19-105">次の表は、HTTP アダプタのパフォーマンスに影響するレジストリ設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="46b19-105">The following table describes the registry settings that affect the performance of the HTTP adapter.</span></span> <span data-ttu-id="46b19-106">既定ではレジストリに HTTP アダプタのキーがないため、HTTP アダプタでは既定の設定が使用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="46b19-106">Note that by default there are no HTTP adapter keys in the registry, so the HTTP adapter uses the default settings.</span></span> <span data-ttu-id="46b19-107">既定の設定を変更する必要がある場合は、次に示すようにレジストリ内の場所にレジストリ キーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46b19-107">If it is necessary to change the default settings, you need to create the following registry keys under the following locations in the registry:</span></span>  
  
-   <span data-ttu-id="46b19-108">**DisableChunkEncoding**、 **RequestQueueSize**、および**HttpReceiveThreadsPerCpu**で定義する必要があります**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**です。</span><span class="sxs-lookup"><span data-stu-id="46b19-108">**DisableChunkEncoding**, **RequestQueueSize**, and **HttpReceiveThreadsPerCpu** must be defined in **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**.</span></span>  
  
-   <span data-ttu-id="46b19-109">**HttpOutTimeoutInterval**、 **HttpOutInflightSize**、および**HttpOutCompleteSize**で定義する必要があります**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {GUID}** 場所**GUID** HTTP 送信ハンドラのホストの id を指定します。</span><span class="sxs-lookup"><span data-stu-id="46b19-109">**HttpOutTimeoutInterval**, **HttpOutInflightSize**, and **HttpOutCompleteSize** must be defined in **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{GUID}** where **GUID** is the ID of the host for the HTTP send handler.</span></span>  
  
|<span data-ttu-id="46b19-110">キー名</span><span class="sxs-lookup"><span data-stu-id="46b19-110">Key name</span></span>|<span data-ttu-id="46b19-111">型</span><span class="sxs-lookup"><span data-stu-id="46b19-111">Type</span></span>|<span data-ttu-id="46b19-112">既定値</span><span class="sxs-lookup"><span data-stu-id="46b19-112">Default</span></span>|<span data-ttu-id="46b19-113">説明</span><span class="sxs-lookup"><span data-stu-id="46b19-113">Explanation</span></span>|  
|--------------|----------|-------------|-----------------|  
|<span data-ttu-id="46b19-114">**DisableChunkEncoding**</span><span class="sxs-lookup"><span data-stu-id="46b19-114">**DisableChunkEncoding**</span></span>|<span data-ttu-id="46b19-115">DWORD</span><span class="sxs-lookup"><span data-stu-id="46b19-115">DWORD</span></span>|<span data-ttu-id="46b19-116">0</span><span class="sxs-lookup"><span data-stu-id="46b19-116">0</span></span>|<span data-ttu-id="46b19-117">クライアントに応答を返すときに、HTTP 受信アダプタでチャンク エンコードを使用するかどうかを規制します。</span><span class="sxs-lookup"><span data-stu-id="46b19-117">Regulates whether or not the HTTP receive adapter uses chunked encoding when sending responses back to the client.</span></span><br /><br /> <span data-ttu-id="46b19-118">HTTP 受信アダプタの応答にチャンク エンコードを使用しない場合、0 以外の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="46b19-118">Set to a nonzero value to turn off chunked encoding for HTTP receive adapter responses.</span></span><br /><br /> <span data-ttu-id="46b19-119">**最小値:** 0</span><span class="sxs-lookup"><span data-stu-id="46b19-119">**Minimum value:** 0</span></span><br /><br /> <span data-ttu-id="46b19-120">**最大値:** 0 以外の値</span><span class="sxs-lookup"><span data-stu-id="46b19-120">**Maximum value:** Any nonzero value</span></span>|  
|<span data-ttu-id="46b19-121">**RequestQueueSize**</span><span class="sxs-lookup"><span data-stu-id="46b19-121">**RequestQueueSize**</span></span>|<span data-ttu-id="46b19-122">DWORD</span><span class="sxs-lookup"><span data-stu-id="46b19-122">DWORD</span></span>|<span data-ttu-id="46b19-123">256</span><span class="sxs-lookup"><span data-stu-id="46b19-123">256</span></span>|<span data-ttu-id="46b19-124">HTTP 受信アダプタで一度に処理される同時実行要求の数を定義します。</span><span class="sxs-lookup"><span data-stu-id="46b19-124">Defines the number of concurrent requests that the HTTP receive adapter processes at one time.</span></span><br /><br /> <span data-ttu-id="46b19-125">**最小値:** 10</span><span class="sxs-lookup"><span data-stu-id="46b19-125">**Minimum value:**  10</span></span><br /><br /> <span data-ttu-id="46b19-126">**最大値:** 2048</span><span class="sxs-lookup"><span data-stu-id="46b19-126">**Maximum value:** 2048</span></span>|  
|<span data-ttu-id="46b19-127">**HttpReceiveThreadsPerCpu**</span><span class="sxs-lookup"><span data-stu-id="46b19-127">**HttpReceiveThreadsPerCpu**</span></span>|<span data-ttu-id="46b19-128">DWORD</span><span class="sxs-lookup"><span data-stu-id="46b19-128">DWORD</span></span>|<span data-ttu-id="46b19-129">2</span><span class="sxs-lookup"><span data-stu-id="46b19-129">2</span></span>|<span data-ttu-id="46b19-130">HTTP 受信アダプタに割り当てられている CPU ごとのスレッドの数を定義します。</span><span class="sxs-lookup"><span data-stu-id="46b19-130">Defines the number of threads per CPU that are allocated to the HTTP receive adapter.</span></span><br /><br /> <span data-ttu-id="46b19-131">**最小値:** 1</span><span class="sxs-lookup"><span data-stu-id="46b19-131">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="46b19-132">**最大値:** 10</span><span class="sxs-lookup"><span data-stu-id="46b19-132">**Maximum value:** 10</span></span>|  
|<span data-ttu-id="46b19-133">**HttpOutTimeoutInterval**</span><span class="sxs-lookup"><span data-stu-id="46b19-133">**HttpOutTimeoutInterval**</span></span>|<span data-ttu-id="46b19-134">DWORD</span><span class="sxs-lookup"><span data-stu-id="46b19-134">DWORD</span></span>|<span data-ttu-id="46b19-135">2000</span><span class="sxs-lookup"><span data-stu-id="46b19-135">2000</span></span>|<span data-ttu-id="46b19-136">タイムアウトする前に、HTTP 送信アダプタが待機する間隔を秒単位で定義します。</span><span class="sxs-lookup"><span data-stu-id="46b19-136">Defines the interval in seconds that the HTTP send adapter will wait before timing out.</span></span><br /><br /> <span data-ttu-id="46b19-137">**最小値:** 500</span><span class="sxs-lookup"><span data-stu-id="46b19-137">**Minimum value:** 500</span></span><br /><br /> <span data-ttu-id="46b19-138">**最大値:** 10000000</span><span class="sxs-lookup"><span data-stu-id="46b19-138">**Maximum value:** 10000000</span></span>|  
|<span data-ttu-id="46b19-139">**HttpOutInflightSize**</span><span class="sxs-lookup"><span data-stu-id="46b19-139">**HttpOutInflightSize**</span></span>|<span data-ttu-id="46b19-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="46b19-140">DWORD</span></span>|<span data-ttu-id="46b19-141">100</span><span class="sxs-lookup"><span data-stu-id="46b19-141">100</span></span>|<span data-ttu-id="46b19-142">BizTalk Server の HTTP 送信アダプタのインスタンスによって処理される、同時実行 HTTP 要求の最大数です。</span><span class="sxs-lookup"><span data-stu-id="46b19-142">This is the maximum number of concurrent HTTP requests that BizTalk Server HTTP send adapter instance will handle.</span></span><br /><br /> <span data-ttu-id="46b19-143">待機時間の推奨値は 3 ~ 5 倍の間、 **maxconnection**構成ファイル エントリを次に説明します。</span><span class="sxs-lookup"><span data-stu-id="46b19-143">The recommended value for latency is between 3 to 5 times that of the **maxconnection** configuration file entry discussed below.</span></span><br /><br /> <span data-ttu-id="46b19-144">**最小値:** 1</span><span class="sxs-lookup"><span data-stu-id="46b19-144">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="46b19-145">**最大値:** 1024</span><span class="sxs-lookup"><span data-stu-id="46b19-145">**Maximum value:** 1024</span></span>|  
|<span data-ttu-id="46b19-146">**HttpOutCompleteSize**</span><span class="sxs-lookup"><span data-stu-id="46b19-146">**HttpOutCompleteSize**</span></span>|<span data-ttu-id="46b19-147">DWORD</span><span class="sxs-lookup"><span data-stu-id="46b19-147">DWORD</span></span>|<span data-ttu-id="46b19-148">5</span><span class="sxs-lookup"><span data-stu-id="46b19-148">5</span></span>|<span data-ttu-id="46b19-149">HTTP 送信アダプターから返されるバッチ メッセージのサイズを制御します。</span><span class="sxs-lookup"><span data-stu-id="46b19-149">Controls the size of the batch of messages that is returned from the HTTP send adapter.</span></span> <span data-ttu-id="46b19-150">バッファーがいっぱいでないと、未処理の応答がある場合、アダプターはバッチをコミットするまで 1 秒間待機します。</span><span class="sxs-lookup"><span data-stu-id="46b19-150">If the buffer is not full and there are outstanding responses then the adapter will wait for 1 second until it commits the batch.</span></span>  <span data-ttu-id="46b19-151">低待機時間シナリオでは、これは処理のメッセージ ボックスにすぐに応答メッセージを送信するアダプターを 1 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46b19-151">For low-latency scenarios this should be set to 1 which will allow the adapter to send response messages immediately to the message box for processing.</span></span><br /><br /> <span data-ttu-id="46b19-152">**最小値:** 1</span><span class="sxs-lookup"><span data-stu-id="46b19-152">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="46b19-153">**最大値:** 1024</span><span class="sxs-lookup"><span data-stu-id="46b19-153">**Maximum value:** 1024</span></span>|  
  
 <span data-ttu-id="46b19-154">**特定の接続先サーバーに、HTTP 送信アダプターによって行われた同時接続数を制御するために構成ファイル エントリ**</span><span class="sxs-lookup"><span data-stu-id="46b19-154">**Configuration File Entry to Govern the Number of Concurrent Connections Made by the HTTP Send Adapter to a Particular Destination Server**</span></span>  
  
 <span data-ttu-id="46b19-155">BizTalk Server インストールのルート ディレクトリにある BTSNTSvc.exe.config ファイルにエントリを作成することで、HTTP アダプタから特定の接続先サーバーに開かれる同時接続の数を構成できます。</span><span class="sxs-lookup"><span data-stu-id="46b19-155">The number of concurrent connections that the HTTP adapter opens for a particular destination server can be configured by making an entry in the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46b19-156">このプロパティは、HTTP アダプタと SOAP アダプタから同じ HTTP サーバーにメッセージを送信する場合に、両方のアダプタに適用されます。</span><span class="sxs-lookup"><span data-stu-id="46b19-156">This property will be applied to both HTTP and SOAP adapters if they send messages to the same destination HTTP server.</span></span> <span data-ttu-id="46b19-157">"Maxconnnection"プロパティの既定値は 2、すべての Uri の"maxconnection"プロパティを設定できる最大値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="46b19-157">The default value for the “maxconnnection” property is 2, the maximum value that can be set for the “maxconnection” property for all URIs is 20.</span></span>  
  
 <span data-ttu-id="46b19-158">"最大接続数" プロパティの構成例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="46b19-158">The following is an example of the configuration for the maximum connections property:</span></span>  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "20" />  
      <add address = "http://www.northwind.com" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46b19-159">参照</span><span class="sxs-lookup"><span data-stu-id="46b19-159">See Also</span></span>  
 [<span data-ttu-id="46b19-160">HTTP アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="46b19-160">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)